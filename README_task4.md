# Music Store SQL Queries

This document contains example SQL queries for the `musicstore` database.

## 1. Select albums by a specific artist using WHERE, ORDER BY, and GROUP BY
```sql
SELECT * FROM album;
SELECT AlbumId, Title, ArtistId
FROM album
WHERE Title LIKE '%Black%'
ORDER BY Title ASC;
```

## 2. Count albums per artist
```sql
SELECT artistid, COUNT(albumid) AS total_albums
FROM album
GROUP BY artistid
ORDER BY total_albums DESC;
```

## 3. INNER JOIN: Albums with Artist names
```sql
SELECT a.AlbumId, a.Title, ar.Name AS artist_name
FROM album a
INNER JOIN artist ar ON a.ArtistId = ar.ArtistId
ORDER BY artist_name;
```

## 4. LEFT JOIN: Customers with their invoices
```sql
SELECT c.customerid, c.firstname, c.lastname, i.invoiceid, i.total
FROM customer c
LEFT JOIN invoice i ON c.customerid = i.customerid
ORDER BY c.lastname;
```

## 5. RIGHT JOIN: Employees and their managers
```sql
SELECT e.FirstName AS employee_firstname, e.LastName AS employee_lastname,
       m.firstname AS manager_firstname, m.lastname AS manager_lastname
FROM employee e
RIGHT JOIN employee m ON e.reportsto = m.employeeid;
```

## 6. Customers who spent more than the average total amount
```sql
SELECT CustomerId, FirstName, LastName, total_spent
FROM (
    SELECT c.CustomerId, c.FirstName, c.LastName, SUM(i.Total) AS total_spent
    FROM customer c
    JOIN invoice i ON c.CustomerId = i.CustomerId
    GROUP BY c.CustomerId
) AS customer_totals
WHERE total_spent > (
    SELECT AVG(total_spent)
    FROM (
        SELECT SUM(total) AS total_spent
        FROM invoice
        GROUP BY customerId
    ) AS avg_table
);
```

## 7. Average track length per genre
```sql
SELECT g.Name AS genre_name, ROUND(AVG(t.milliseconds) / 60000, 2) AS avg_length_minutes
FROM track t
JOIN genre g ON t.GenreId = g.GenreId
GROUP BY g.name
ORDER BY avg_length_minutes DESC;
```

## 8. Total revenue per country
```sql
SELECT BillingCountry, SUM(Total) AS total_revenue
FROM invoice
GROUP BY BillingCountry
ORDER BY total_revenue DESC;
```

## 9. Top 5 selling tracks by revenue (View)
```sql
CREATE VIEW top_tracks AS
SELECT t.TrackId, t.Name AS track_name, SUM(il.UnitPrice * il.Quantity) AS total_revenue
FROM invoiceline il
JOIN track t ON il.TrackId = t.TrackId
GROUP BY t.TrackId, t.Name
ORDER BY total_revenue DESC
LIMIT 5;

SELECT * FROM top_tracks;
```

## 10. Index on track name for faster searches
```sql
CREATE INDEX idx_track_name ON track(Name);
```
