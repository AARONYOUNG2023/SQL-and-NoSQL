



#### Exercise 1

SELECT DISTINCT vendor_name
FROM vendors
WHERE vendor_id IN (SELECT vendor_id FROM invoices)
ORDER BY vendor_name;

#### Exercise 2

SELECT invoice_number, invoice_total
FROM invoices
WHERE payment_total > (
SELECT AVG(payment_total)
FROM invoices
WHERE payment_total > 0
)
ORDER BY invoice_total DESC;

#### Exercise 3

SELECT account_number, account_description

FROM general_ledger_accounts

WHERE 