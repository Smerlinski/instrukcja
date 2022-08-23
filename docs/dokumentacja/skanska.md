# Skanska

## Zmiana nazwy pomiarów z Node-RED

```
INSERT INTO field_values(definition_id, item_id, field_id, type, value)
SELECT 'IXExEWg', item_id, 'Q5A2PP6', 'STRING', item_id
FROM items
WHERE definition_id = 'IXExEWg'
ON CONFLICT DO NOTHING;
```