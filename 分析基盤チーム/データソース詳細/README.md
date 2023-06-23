# 問題例

## 設定1

- データモデルXとYが存在する
- YはXに従属する
- XとYには日付型、created_atカラムが存在する

## 設定2(データ取得)

- データモデルXは100万レコード存在する
- データモデルYは5億レコード存在する
- 1日毎に、データモデルX1レコードにつき、1データモデルYを10レコード取得する
- 1レコードにつき1000Byteで計算する

## 設定3(データフロント)

- データモデルXとYそれぞれ一覧画面が存在する
- 直近1年について取得時間1秒
- それ以降について取得時間5秒
- 読み取り回数は限りなく低いものとする

# データソース

## S3



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

# 案

設定1, 2, 3についての案

## 案1

データレイクにS3
データウェアハウスにRDS-Auroraを利用

S3標準クラスの料金は 
ストレージが0.025 USD/GB
書き込み 0.0047USD/ 1000リクエスト
読み込み 0.0037USD/ 1000リクエスト


### 料金計算
ストレージ
1レコードのByte数 * レコード数 / GBに変換 * 料金 * ドル円レート
= 1000 * 500000000 / 1000/ 1000 / 1000 * 0.025 * 140
= 1750円

書き込み(X毎に書き込む想定)
書き込みリクエスト回数 = 1日の書き込み回数 * 30
= 1000000 * 30
= 30000000

料金 = 書き込みリクエスト回数 * 書き込み料金 / 1000 * ドル円レート
= 30000000 * 0.0047 / 1000 * 140
= 19740円

読み込み(X毎に読み込む想定)
読み込みリクエスト回数 = 1日の読み込み回数 * 30
= 1000000 * 30
= 30000000

料金 = 読み込みリクエスト回数 * 読み込み料金 * 30
= 30000000 * 0.0037 / 1000 * 140
= 15540円





Auroraの料金は
- インスタンス料金
- ストレージ料金
- IO料金
の3つ