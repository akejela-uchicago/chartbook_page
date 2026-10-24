# Dataframe: `hw2:fed_funds_futures` - 30-Day Fed Funds Futures (ZQ) Daily Bars

Daily ohlcv-1d bars for all listed ZQ contracts, pulled from the Databento GLBX.MDP3 dataset with parent symbology (ZQ.FUT) by src/pull_fed_funds_futures.py. Columns: date (tz-naive trading date), symbol, open, high, low, close, volume. A ZQ contract settles at 100 minus the calendar-day average of the daily effective fed funds rate over its contract month, so the implied average rate is 100 - price. The symbol column includes calendar spreads (e.g. ZQU6-ZQZ6) alongside the outright monthly contracts (e.g. ZQU6); keep only outrights with fedwatch.filter_outright_contracts before computing implied rates. Thinly traded far months may have no bar on a given trading day, so use each contract's last available close as of the date of interest.


## DataFrame Glimpse

```
Rows: 11818
Columns: 7
$ date   <datetime[ns]> 2026-10-22 00:00:00
$ symbol          <str> 'ZQN7-ZQX7'
$ open            <f64> 5.0
$ high            <f64> 5.0
$ low             <f64> 5.0
$ close           <f64> 5.0
$ volume          <u64> 6


```

## Dataframe Manifest

| Dataframe Name                 | 30-Day Fed Funds Futures (ZQ) Daily Bars                                                          |
|--------------------------------|--------------------------------------------------------------------------------------|
| Dataframe ID                   | [fed_funds_futures](../dataframes/hw2/fed_funds_futures.md)                                       |
| Sources                        | CME Globex                                          |
| Providers                      | Databento                                        |
| Provider Links                 | https://databento.com/                                   |
| Tags                           | Monetary Policy, Futures, Fedwatch                                             |
| Access Types                   |                                       |
| How is data pulled?            | Databento Historical API via Python                                                   |
| Data available up to (min)     | 2026-10-22 00:00:00                                                             |
| Data available up to (max)     | 2026-10-22 00:00:00                                                             |
| Dataframe Path                 | /Users/ammankejela/Desktop/Dev/pipelines/hw2/hw2-akejela-uchicago/_data/fed_funds_futures.parquet                                             |


**Linked Charts:**


- [hw2:fedwatch_latest_forecast](../../charts/hw2.fedwatch_latest_forecast.md)



## Pipeline Manifest

| Pipeline Name                   | HW 2: The Yield Curve and the Policy Path                       |
|---------------------------------|--------------------------------------------------------|
| Pipeline ID                     | [hw2](../../../index.md)              |
| Maintainer                      | Jeremiah Bejarano               |
| Contributors                    | Jeremiah Bejarano |
| Repository                     | https://github.com/hw-finm-32800/hw2                  |
| Pipeline Web Page               | <a href="file:///Users/ammankejela/Desktop/Dev/pipelines/hw2/hw2-akejela-uchicago/docs/index.html">Pipeline Web Page      |
| Date of Last Code Update        | 2026-10-23 20:45:08           |
| OS Compatibility                | Windows, Linux, macOS |
| Linked Dataframes               |  [hw2:crsp_treasury_consolidated](../../dataframes/hw2/crsp_treasury_consolidated.md)<br>  [hw2:fed_yield_curve](../../dataframes/hw2/fed_yield_curve.md)<br>  [hw2:fed_funds_futures](../../dataframes/hw2/fed_funds_futures.md)<br>  |


**Build Commands:**
```
doit

```

