#### SELECT Script

```SQL
SELECT * FROM customer

-- SELECT DISTINCT
SELECT DISTINCT * FROM customer WHERE segment = 'Corporate'

-- SELECT WITH LOGICAL OPERATORS
SELECT * FROM customer WHERE segment = 'Corporate' OR segment = 'Consumer'
```

#### CREATE Script

```SQL
CREATE TABLE public.customer
(
    customer_id character varying(255) COLLATE pg_catalog."default" NOT NULL,
    customer_name character varying(255) COLLATE pg_catalog."default",
    segment character varying(255) COLLATE pg_catalog."default",
    age integer,
    country character varying(255) COLLATE pg_catalog."default",
    city character varying(255) COLLATE pg_catalog."default",
    state character varying(255) COLLATE pg_catalog."default",
    postal_code bigint,
    region character varying(255) COLLATE pg_catalog."default",
    CONSTRAINT "Customer_pkey" PRIMARY KEY (customer_id)
)
```

##### INSERT Script

```SQL
INSERT INTO customer (customer_id,customer_name,segment,age, country, city, state, postal_code, region) 
VALUE ('JD-202010', 'John Doe', 'Customer', 35, 'EUROPE', 'PARIS', 'FRANCE', 75000,'ILE-DE-FRANCE');
```

##### UPDATE Script

```SQL
UPDATE customer SET customer_name = 'John DOE' WHERE customer_id = 'JD-202010'
```
##### DELETE Script

```SQL
DELETE FROM  customer WHERE customer_name = 'John DOE'
```
##### ALTER Script

```SQL
-- ADD statement
ALTER TABLE customer ADD test varchar(255)

-- DROP statement
ALTER TABLE customer DROP test 
```
