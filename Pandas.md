# Cheat Sheet
- [Great TDS article](https://towardsdatascience.com/data-science-coding-mistakes-and-best-practices-part-1-f7511cf573f7)
- Day of week (0=monday): `df.index.weekday()` 
- Index a single day: `df.loc['2021-1-1']` not `df['2021-1-1']`
- Daylight savings time:
  ```python
  df = df.tz_localize('US/Mountain', ambiguous='infer')
  df = df.tz_convert('Etc/GMT+7')
  df = df.tz_localize(None)
  ```
- Cant import numbers ("null data")
  ```python
  df['x'] = pd.to_numeric(df['x'], errors='coerce')
  ```
- Correlate: `df.corr(method='pearson')`
- See index interval and gaps: `df.index.to_series().diff().describe()`
- Downsample: `df.Feature1.resample('1h').mean()`
- Upsample: `df.Feature1.resample('1min').interpolate()`
- Fill gaps in index:
  ```python
  df.index = df.index.floor('1min') # remove seconds (if needed)
  df['dt'] = df.index.to_series().diff()
  print(df[df['dt'] > df['dt'].iloc[1]].to_string())
  start, end = df.index[0], df.index[-1]
  idx = pd.date_range(start=start, end=end, freq='1min') # or '1h' etc
  df2 = pd.DataFrame(np.nan, index=idx, columns=['Feature1'])
  df2.loc[df.index, 'Load (kW)'] = df['Load (kW)'].values
  ```
- Show NaNs: `df[df.isna().values]`
- Plot: `df.plot()`
- Plotly default: `pd.options.plotting.backend = 'plotly'`

# Mistakes/Warnings
## `SettingWithCopy`
- Don't do: `df['col']['row'] = values`
- Not clear if value is being put into a view or copy of df (speed implication)
- Instead do: `df.loc[row, col] = values`


Why?
- `df['2020':'2022']` returns a data frame
- `df['label']` returns a data series
- `df[['label']]` returns a data frame
- So `df['2020':'2022']['label']` return a data series

  
