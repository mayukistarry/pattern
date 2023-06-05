# 参考URL

- [BigQueryとは](https://cloud.google.com/bigquery/docs/introduction?hl=ja)
- [リファレンス](https://cloud.google.com/bigquery/docs/reference/libraries-overview?hl=ja)

# 関数作成

## time_parsing

0埋めしない時間の文字列をパースする。
ex. X:YY:ZZ => 0X:YY:ZZ
ex. YY:ZZ => 00:YY:ZZ

```sql
CREATE TEMP FUNCTION time_parsing(time_str STRING) RETURNS TIME AS (IF(LENGTH(time_str) > 5, PARSE_TIME('%H:%M:%S', time_str), PARSE_TIME('%M:%S', time_str)));
```

## parse_second

Time型データを秒換算する

```sql
CREATE TEMP FUNCTION parse_second(time_data TIME) RETURNS INT64 AS (EXTRACT(HOUR FROM time_data) * 3600 + EXTRACT(MINUTE FROM time_data) * 60 + EXTRACT(SECOND FROM time_data));
```

## round_divide

桁数を指定
エラーが起きた場合は0を返す

```sql
CREATE TEMP FUNCTION round_divide(x FLOAT64, y FLOAT64, digit INT64) RETURNS FLOAT64 AS (ROUND(IFNULL(SAFE_DIVIDE(x, y), 0), digit));
```


