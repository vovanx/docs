# Inconsistent aggregation among operands

`ERR.DS_API.VALIDATION.AGG.INCONSISTENT`

This occurs when a single function (or a single operator)

Examples:

- `[Sales] / SUM([Sales])`
- `[Total Sales] - [Profit]`. Where the `Total Sales` field is an aggregated expression (measure),

Another error might occur when the window function in the `WITHIN` section has fields that are neither an aggregation nor a dimension in the chart.
