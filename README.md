# jeffnieves-dba120-exam1

INSERT INTO terms
    (terms_id, terms_description, terms_due_days)
VALUES
    (6, 'Net due 120 days', 120)

ex 1 adds new record to the term id, term description, terms due date to the values of '6', 'Net due 120 days', '120'
![ch5_ex1_results](https://user-images.githubusercontent.com/122382857/217451230-a6756b94-23f7-4cab-a08f-0dbfeee40f61.png)


UPDATE terms
SET terms_description = 'Net due 125 days',
    terms_due_days = 125
WHERE terms_id = 6

ex 2 updates the term discriptionand term due dates
![ch5_ex2_results](https://user-images.githubusercontent.com/122382857/217451451-88f6030e-5ba4-47dc-a24f-157eb15d9982.png)


DELETE FROM terms
WHERE terms_id = 6

ex 3 deletes the record of the term id of the value 6 
![ch5_ex3_results](https://user-images.githubusercontent.com/122382857/217451468-81f9a536-d3c3-4f0e-927f-0033487b8fff.png)


INSERT INTO invoices
VALUES (DEFAULT, 32, 'AX-014-027', '2018-08-01', 434.58, 0, 0,
        2, '2018-08-31', NULL)

ex 4 insert a new record to the invoice the values of (NULL, 32, 'AX-014-027', '2018-08-01', 434.58, 0.00, 0.00,2, '2018-08-31', null)
![ch5_ex4_results](https://user-images.githubusercontent.com/122382857/217451474-2933376c-9c4c-43f4-b274-0729d1d3c53d.png)


INSERT INTO invoice_line_items VALUES
    (115, 1, 160, 180.23, 'Hard drive'),
    (115, 2, 527, 254.35, 'Exchange Server update')

ex 5 inserts a new record to the invoice line item values of (1, 160, 180.23, 'Hard drive') and (2, 527, 254.35, 'Exchange Server update'), and selecting invoce id from the invoice
![ch5_ex5_results](https://user-images.githubusercontent.com/122382857/217451477-d67c4b2f-5831-4099-8980-225435999a5a.png)


UPDATE invoices
SET credit_total = invoice_total * .1,
    payment_total = invoice_total - credit_total
WHERE invoice_id = 115

ex 6 this update the table by calculation
![ch5_ex6_results](https://user-images.githubusercontent.com/122382857/217451486-b2d37c56-1eaa-44ef-9aef-8f41aa7405c6.png)


UPDATE vendors
SET default_account_number = 403
WHERE vendor_id = 44

ex 7 update the vendors table of vendor id 44
![ch5_ex7_results](https://user-images.githubusercontent.com/122382857/217451505-f8f41447-4c38-4346-b9ed-d33c8678728c.png)


UPDATE invoices
SET terms_id = 2
WHERE vendor_id IN
    (SELECT vendor_id
     FROM vendors
     WHERE default_terms_id = 2)

ex 8 updates the invoice from the vendors table
![ch5_ex8_results](https://user-images.githubusercontent.com/122382857/217451516-1b2050e8-5a39-407b-bf5e-f38a2028724c.png)


DELETE FROM invoice_line_items
WHERE invoice_id = 115;

DELETE FROM invoices
WHERE invoice_id = 115;

ex 9 deletes record from invoice table and deletes invoice id 115
![ch5_ex9_results](https://user-images.githubusercontent.com/122382857/217451524-7214fa50-f4e6-4a62-b60a-59862b0e0b23.png)
