# 問題例

## 設定1

- データモデルXとYが存在する
- YはXに従属する
- XとYには日付型、created_atカラムが存在する

## 設定2(データ取得)

- データモデルXは100万レコード存在する
- データモデルYは5億レコード存在する
- 1日毎に、データモデルX1レコードにつき、1データモデルYを10レコード取得する

## 設定3(データフロント)

- データモデルXとYそれぞれ一覧画面が存在する
- 直近1年について取得時間1秒
- それ以降について取得時間5秒

# データソース

## RDS-Aurora

- [料金](https://aws.amazon.com/jp/rds/aurora/pricing/)
- [制限](https://docs.aws.amazon.com/ja_jp/AmazonRDS/latest/AuroraUserGuide/AuroraMySQL.Managing.Performance.html)
- [概要](https://docs.aws.amazon.com/ja_jp/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.html)

## DynamoDB

- [料金](https://aws.amazon.com/jp/dynamodb/pricing/provisioned/)
- [概要](https://docs.aws.amazon.com/ja_jp/amazondynamodb/latest/developerguide/Introduction.html)

## Redshift

- [料金](https://aws.amazon.com/jp/redshift/pricing/)

## Elasticache

- [料金](https://aws.amazon.com/jp/elasticache/pricing/)

## Redis

## Memcached

## BigQuery

- [料金](https://cloud.google.com/bigtable/pricing?hl=ja)
- [パフォーマンス](https://cloud.google.com/bigtable/docs/performance?hl=ja)

## CloudDataStore

- [料金](https://cloud.google.com/datastore/pricing?hl=ja)
- [制限](https://cloud.google.com/datastore/docs/concepts/limits?hl=ja)

## CloudStorage

## BigTable

- [料金](https://cloud.google.com/bigtable/pricing?hl=ja)
- [パフォーマンス](https://cloud.google.com/bigtable/docs/performance?hl=ja)

