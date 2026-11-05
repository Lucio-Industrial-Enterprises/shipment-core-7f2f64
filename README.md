# Warehouse tools

Small Python utilities for warehouse order and shipping workflows.

Run the tests with `python3 -m unittest discover -s tests -v`.

## Shipping

`shipping_quote(weight_kg, zone, service="standard")` returns a delivery quote
in USD. Zones are `local` and `regional`; weights must be positive.

Services:
- `standard` — base rate ($5 local / $8 regional) plus $1.50 per kg
- `express` — same as standard plus a flat $7.00 surcharge

Unknown zones or services raise `ValueError`.

The command-line entry point prints a quote for an order:

```
python -m warehouse.cli 2 local
python -m warehouse.cli 2 local --service express
```
