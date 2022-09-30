# Przeliczenia liczników

```
SELECT instap_interpolate_hour(
    'definition_id',
    'item_id',
    'field_id 1',
    'field_id 2');

SELECT instap_interpolate_day(
    'definition_id',
    'item_id',
    'field_id 1',
    'field_id 2');

SELECT instap_interpolate_week(
    'definition_id',
    'item_id',
    'field_id 1',
    'field_id 2');

SELECT instap_interpolate_month(
    'definition_id',
    'item_id',
    'field_id 1',
    'field_id 2');

SELECT instap_interpolate_year(
    'definition_id',
    'item_id',
    'field_id 1',
    'field_id 2');

```
definition_id - id definicji, w której znajduję się licznik
item_id - id licznika
field_id 1 - id pola z którego mają być pobrane dane
field_id 2 - id pola do którego mają być przypisane dane 

## Przeliczenia zatrzasków na zmiennej

```
SELECT time_bucket('1 hour', minute) as hour, d, i, f, sum(w::int) as minutes from
(
    SELECT
        time_bucket_gapfill('1 minute', timestamp, now() - interval '1 year', now()) AS minute,
        definition_id as d,
        item_id as i,
        field_id as f,
        max(value::int) AS value,
        locf(max(value)) as w
    FROM field_value_changes
    WHERE field_value_changes.timestamp > now() - interval '1 year' and definition_id='Klimatyzacja' and item_id='L02_1_01' and field_id='EffecOccupancy'
    GROUP BY minute, field_id, definition_id, item_id
    ORDER BY minute desc
) as minutes
group by hour, d, i, f
order by hour desc;
```