# Queries

## Load data into your Amazon Redshift Serverless Instance

```
CREATE TABLE public.machine_data (
    machine_timestamp timestamp without time zone,
    machine_manufacturer_id character varying(256),
    line character varying(256),
    line_description character varying(256),
    operator_name character varying(256),
    operator_perno character varying(256),
    machine character varying(256),
    machine_description character varying(256),
    units_target integer,
    wire_tension double precision,
    power_unit integer,
    error_code character varying(256),
    bit_speed double precision,
    temperature double precision,
    units double precision,
    oee double precision,
    defective_count double precision
) DISTSTYLE AUTO;


```



### create a view to be used in QuickSight as a datasource

```
CREATE MATERIALIZED VIEW full_machine_data
AS
select machine_timestamp,
machine_manufacturer_id,
line,
line_description,
operator_name,
operator_perno,
machine,
machine_description,
units_target,
wire_tension,
power_unit,
error_code,
bit_speed,
temperature,
units, 
oee,       
defective_count from machine_data;

```
```
select * from full_machine_data;

```

## Ranges for Quicksight Dashboard

```
select min(machine_timestamp),
max(machine_timestamp)
from full_machine_data

```


### Join Streaming Data with Redshift Data.


```
DROP MATERIALIZED VIEW full_machine_data;
CREATE MATERIALIZED VIEW full_machine_data
AS
    select machine_timestamp,
    machine_manufacturer_id,
    line,
    line_description,
    operator_name,
    operator_perno,
    machine,
    machine_description,
    units_target,
    bit_speed,
    temperature,
    wire_tension,
    power_unit,
    error_code,
    units, 
    oee,       
    defective_count    
    from ext_cleaned_stream.cleaned_stream
UNION
    select machine_timestamp,
    machine_manufacturer_id,
    line,
    line_description,
    operator_name,
    operator_perno,
    machine,
    machine_description,
    units_target,
    bit_speed,
    temperature,
    wire_tension,
    power_unit,
    error_code,
    units, 
    oee,       
    defective_count
from machine_data;

```

```

SELECT * FROM full_machine_data
WHERE operator_name = 'engineering_maintenance'

```