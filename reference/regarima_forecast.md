# Forecasts with RegARIMA

Forecasts with RegARIMA

## Usage

``` r
regarima_forecast(
  ts,
  spec = c("rg4", "rg0", "rg1", "rg2c", "rg3", "rg5c"),
  context = NULL,
  nf = -1
)
```

## Arguments

- ts:

  an univariate time series.

- spec:

  the model specification. Can be either the name of a predefined
  specification or a user-defined specification.

- context:

  list of external regressors (calendar or other) to be used for
  estimation

- nf:

  the forecasting horizon (`numeric`). The forecast length is in periods
  (positive values) or years (negative values). By default, the program
  generates a one-year forecast (`nf = -1`).

## Value

a `mts` object with 4 variables:

- `forecast` the forecast of the actual data at the end of the series.

- `error` standard deviation of the forecast.

- `fraw` the forecast of the transformed series.

- `efraw` the standard deviation of the forecast of the transformed
  series.

## Examples

``` r

regarima_forecast(rjd3toolkit::ABS$X0.2.09.10.M)
#>          forecast     error     fraw      efraw
#> Sep 2017 1382.275  55.05177 7.231486 0.03977970
#> Oct 2017 1506.471  59.98476 7.317525 0.03977085
#> Nov 2017 1697.550  67.92869 7.436941 0.03996781
#> Dec 2017 2806.607 116.84905 7.939732 0.04157961
#> Jan 2018 1466.174  61.88205 7.290412 0.04215028
#> Feb 2018 1089.633  46.95460 7.002485 0.04265254
#> Mar 2018 1422.643  62.31816 7.260272 0.04374167
#> Apr 2018 1432.825  63.74423 7.267403 0.04442271
#> May 2018 1449.609  64.90768 7.279049 0.04470893
#> Jun 2018 1537.062  69.89411 7.337628 0.04540230
#> Jul 2018 1468.704  67.66441 7.292136 0.04599777
#> Aug 2018 1304.531  60.91195 7.173599 0.04661655
```
