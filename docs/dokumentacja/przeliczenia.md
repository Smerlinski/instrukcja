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