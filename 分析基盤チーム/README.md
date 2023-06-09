# 分析基盤システムチームにおける仕事方法

## 概要

分析基盤を作るチームはどのような仕事がありますか？

1. データエンジニアリング: データ収集、統合、変換、クレンジング、保存を行うプロセスを担当します。データウェアハウスやデータレイクの構築も含まれます。
2. データアーキテクチャ: データの流れやデータモデルを設計し、データの整合性や拡張性を保つ役割を担います。
3. データパイプライン開発: ETL（Extract, Transform, Load）やELT（Extract, Load, Transform）プロセスを実装し、データの移動や加工を効率化します。
4. データインフラストラクチャ管理: 分析基盤に関するハードウェアやソフトウェアリソースを管理し、パフォーマンスやセキュリティを最適化します。
5. データ品質管理: データの正確性、一貫性、信頼性を保つためのポリシーやプロセスを策定・実施します。
6. データガバナンス: データの利用やアクセス制御に関するルールやポリシーを策定し、データ利用の適切性やコンプライアンスを確保します。
7. データセキュリティ: データの機密性、完全性、可用性を保つためのセキュリティ対策を実施します。
8. データ分析やビジュアライゼーションツールの提供: 分析基盤上で働くデータアナリストやビジネスユーザーに対し、データ分析や可視化のためのツールやサービスを提供します。
9. チーム間のコラボレーション: 他のチームや部門と連携し、データの活用を促進し、ビジネス上の課題や目標に対応します。
10. 教育とトレーニング: チームメンバーや他部門のメンバーに対し、分析基盤やデータに関する知識やスキルを教える役割を担います。

## 名称定義

- xxxxx

## データ保存先

### RDS

### スプレッドシート

- web上の表システム
- 一時的なデータを保存するのにベスト

### BigQuery

- ビッグデータ用のデータベース
- クエリ量課金
- GCS, スプレッドシート, CloudSQLを直接クエリで読みにいくことが可能

### CloudStorage

- ストレージサービス

### Redis

- インメモリデータベース

### Memcached

- インメモリデータベース

### Elasticsearch

- テキスト検索用データベース

### MongoDB

- JSON型NoSQL

### CloudDataStore

- ワイドカラム型NoSQL

### BigTable

### DynamoDB

- ワイドカラム型NoSQL
- パフォーマンスに対して課金(ということができる)

### S3

- ストレージサービス

### Athena

- S3をデータベースとしたクエリサービス
- クエリ量課金

## 通常タスクパターン一覧

### 基本的パターン実行

1. 現状の状況認識、情報整理を行う ⇒ ここもパターン化できればベスト
2. 適合するパターンの確認
3. 制約条件の確認
4. 必要があれば上司の承認 ⇒ いつ上司に承認を得るか？
5. パターン実行
6. 実行結果の確認 ⇒ ここもパターン化できればベスト
7. 反省 ⇒ どうすればもっと早く実行できたか？何を用意すればよかったか？システムの機能追加で賄えるか？パターン統合できないか？(実際にこれらの反省した内容をやるかどうかは他との優先順位の兼ね合い)、パターンを改善するべきか？

### パターン実行の管理方法

1. 長期に渡る場合(1ヶ月以上)や複雑な場合はドキュメントで管理する。短期的である場合にはタスク管理ツールで管理する。
2. パターンの1ステップをスキップする場合には、理由をドキュメント or タスク管理ツールに書いた上でスキップを行う。お金がかかる場合、既存システムに過度な影響がある場合は、上司にレビューをもらう

### 情報整理の観点

- 場合分け
- 何があるか？(関係者は誰か？関連するデータは何があるか？)
- スタートとゴールの設定

### 仕事においてどうすればいいか分からなくなった時の対処法

1. 一度立ち止まって整理する(情報を整理すれば問題は解決する)
問題や状況を整理し、具体的な目標や進めるべき方向性を明確にすることが大切です。必要であれば、リストや図を使って視覚的に整理することも効果的です。また2番を行うための整理も必要です。
2. 情報収集・リサーチを行う
どうすればいいか分からない場合、情報不足が原因であることがよくあります。適切な情報を得るために、インターネットや書籍、専門家、ステークホルダーなどを活用しましょう。
3. 上司や同僚に相談する
悩みや問題を共有することで、他の人の意見やアドバイスをもらえることがあります。また、自分だけでは気づかない新たな視点や解決策が見つかることもあります。
4. 優先順位を見直す
どのタスクから取り組むべきか、重要度や緊急度に基づいて優先順位をつけ直しましょう。これにより、焦りやストレスを軽減できる場合があります。
5. スキルや知識を向上させる
スキルや知識が不足していることが問題解決の妨げになる場合があります。適切なトレーニングや研修を受けることで、問題に対処できる力を身につけましょう。
6. タイムマネジメントを見直す
時間の使い方を見直し、効率的なスケジュールを立てることで、問題解決に役立つことがあります。タスクを分割し、適切な休憩時間を設けることも重要です。
7. 小さな成果を積み重ねる
大きな問題に対処する際には、小さな成果を積み重ねることが大切です。一度にすべてを解決しようとせず、一つひとつのタスクをこなしていくことが効果的です。

### チャットにおけるコミュニケーション

1. 情報共有: チームメンバーや関係者と情報を共有するために行われるやりとりです。これには、プロジェクトの進捗状況、アイデア、資料、リンクなどが含まれます。
2. 質問と回答: 仕事に関連する質問を投げかけ、回答を得るためのコミュニケーションです。これには、仕事の内容、手続き、予定、方針などに関する質問が含まれます。
3. 意思決定: チームメンバーや関係者と協力して決定事項を議論し、合意を得るためのコミュニケーションです。これには、プロジェクトの方向性、タスクの優先順位、リソースの割り当てなどが含まれます。
4. 進捗報告: 個人やチームのタスクやプロジェクトの進捗状況を報告するためのコミュニケーションです。
5. 打ち合わせ: 定期的に開催されるミーティングや、特定の議題について話し合うためのコミュニケーションです。
6. フィードバックと評価: 他のメンバーの作業に対する意見やアドバイスを提供するためのコミュニケーションです。これには、添削、指摘、改善提案などが含まれます。
7. 社交的なコミュニケーション: チームメンバーや関係者との関係を築くためのコミュニケーションです。これには、挨拶、お祝い、雑談などが含まれます。

### 要件定義の手順

1. プロジェクトの目的と範囲を明確化する:
プロジェクトの目的、期待される成果、対象となるユーザーやシステムの範囲を明確にしましょう。
2. ステークホルダーを特定する:
プロジェクトに関与するすべてのステークホルダーを特定し、彼らのニーズや期待について理解しましょう。
3. ユーザーストーリーやユースケースを作成する:
システムの機能やユーザーの役割を明確にするために、ユーザーストーリーやユースケースを作成します。これにより、要件が具体的で理解しやすくなります。
4. 機能要件を定義する:
システムが実現すべき具体的な機能をリストアップし、それぞれの機能に関連する詳細な情報を記述します。例えば、データ入力フォームや検索機能などです。
5. 非機能要件を定義する:
システムが満たすべき品質や性能などの非機能要件を定義します。例えば、パフォーマンス、セキュリティ、拡張性、利用可能性などです。
6. 要件の優先順位を決定する:
すべての要件を実現することができない場合、要件の優先順位を決定して、重要なものから開発を進めるようにします。
7. 要件定義ドキュメントを作成する:
要件定義の結果をまとめたドキュメントを作成し、ステークホルダーと共有します。このドキュメントは、開発チームがシステムを設計・開発する際の基本資料となります。
8. レビューと承認を得る:
要件定義ドキュメントをステークホルダーにレビューしてもらい、意見や修正点を取り入れた上で、最終的な承認を得ます。
9. 要件の変更管理を行う:
プロジェクトが進行する中で、要件が変更されることがあります。変更要求があった場合は、適切な変更管理プロセスを通じて、影響分析を行い、必要に応じて要件定義ドキュメントを更新しましょう。変更管理はプロジェクトの進行に影響を与えるため、適切に管理することが重要です。
10. 要件の追跡と検証を行う:
開発が進行する中で、定義された要件が実装されているか確認するために、要件追跡と検証を行います。これにより、要件が適切に実装されていることを確認し、品質の高いシステムを開発することができます。

### 機能要件のパターン

webシステムよりの話だと思うので、分析基盤チームであれば関係ない部分も出てくるかもしれない。

1. ユーザー管理機能:
システム内のユーザーを管理する機能です。アカウント作成、ログイン・ログアウト、パスワード変更、ユーザープロフィールの編集、権限管理などが含まれます。
2. データ入力・編集機能:
ユーザーがシステム内でデータを入力、編集、削除できる機能です。フォームを使ったデータ入力、一括データインポート・エクスポート、データのバリデーションなどが含まれます。
3. 検索・フィルタリング機能:
ユーザーがシステム内のデータを検索、フィルタリングできる機能です。キーワード検索、条件指定によるフィルタリング、ソート機能などが含まれます。
4. レポート・分析機能:
システム内のデータを集計、分析し、レポートとして表示する機能です。グラフやチャートを用いた可視化、期間指定やカテゴリ別の分析、ダウンロード可能なレポート形式などが含まれます。
5. 通知・アラート機能:
システム内で特定のイベントが発生した際に、ユーザーに通知やアラートを送る機能です。メール通知、SMS通知、アプリ内通知などが含まれます。
6. インテグレーション機能:
他のシステムやアプリケーションと連携する機能です。API連携、データ連携、サードパーティサービスの利用などが含まれます。
7. セキュリティ機能:
システムの安全性を確保する機能です。データ暗号化、アクセス制御、不正アクセス対策、セキュリティ監査などが含まれます。

### 非機能要件のパターン

1. パフォーマンス要件:
システムが持つべき応答時間、処理能力、スループットなどの性能特性を定義します。
2. 可用性要件:
システムの稼働率やダウンタイムの許容範囲、冗長化、フェイルオーバーなどの要件を示します。
3. スケーラビリティ要件:
システムが成長や拡大に対応できるように、水平拡張や垂直拡張の可能性を考慮します。
4. 拡張性要件:
システムが将来的な変更や機能追加に対応できるよう、モジュール性や互換性などの要素を明確にします。
5. セキュリティ要件:
システムのデータ保護、アクセス制御、認証・認可、脆弱性対策などのセキュリティ対策を定義します。
6. ユーザビリティ要件:
システムが利用者にとって使いやすく、直感的であることを示す要件です。ユーザーエクスペリエンスやアクセシビリティなどが考慮されます。
7. 互換性要件:
システムが異なるデバイス、ブラウザ、オペレーティングシステムなどと互換性があることを示す要件です。
8. 運用性要件:
システムの運用・保守に関する要件で、監視、バックアップ、復元、デプロイメント、アップデートなどの機能が含まれます。
9. 法規制およびコンプライアンス要件:
システムが満たすべき法律や規制、業界標準、ポリシーなどに関する要件です。
10. 信頼性要件:
システムのエラー耐性、障害復旧能力、安定性などを示す要件です。

### 思考・論理の可視化

- マインドマップを使う ⇒ mermaidでも可
- 議論の際はマインドマップを利用
- plantumlでマインドマップ作成可能 ⇒ リスト形式

### システムの不備調査パターン

1. 依頼者となるべく同環境を作ることを目指す

### システムの不備確認の観点のパターン

- 自分が再現できるか？
- 他の人が再現できるか？
- ブラウザは何を使ってるか
- PCは何を使ってるか

## 分析基盤チーム固有パターン一覧

- 後で分類

### memo

- データの品質管理、抽出依頼などの際は、確認用クエリを設ける
- データの品質管理の定型タスクは設けるべきである

### Cloud上データソースアクセスに不備がある

1. Cloud上データソースのメトリクスを確認する
2. アプリケーションログを確認する
3. Cloud上データソースのCPU使用率などで高ければ再起動を行う
4. アプリケーションログとgithubのログを照らし合わせ不審な点があればコードの問題解決
5. 4番で解決に時間がかかる場合は、revertなどを利用してコード自体を戻す

### 一時的な依頼データベースからのデータ抽出依頼対応

1. 依頼をもらう
2. 依頼者のデータ定義確認
3. 抽出方法の決定
4. データの抽出
5. 必要があればデータの加工を行う
6. データ抽出、加工の方法をどこかしらに保存(タスク管理ツールとか)
7. データの確認
8. 依頼者に渡す
9. 次に同じ依頼が来たときにどうすればもっと早く実行できるか考える。(システム作って仕組み化するにせよ)

### 依頼者にデータ確認

- XデータベースのYというテーブルにおける、Zというカラムのデータがおかしいということで合っているか再度確認する。この時、場合によってはYテーブルのデータの範囲も絞る必要があるのでそこも確認する。
- データベース、テーブルという単語が通じない場合があるため、その時は利用システムのどういった時に抽出したデータか尋ねる。

### 抽出方法

- APIから取得
    - システムを使う
    - curlを使う
    - 拡張機能を使う
- データベースから取得
- APIExploreなどの利用

### GCPの権限管理

1. 新規発行についてはシステムチームであればそのまま発行。それ以外は直属上司とインフラチーム、場合によっては情シスに確認する
2. BigQueryに関しては、データセットごと、テーブルごとに権限管理可能なので、細かく権限管理を行う ⇒ あまりにも細かくすると管理が面倒なので、データセット程度で留めておくか、システム化、そもそも別プロジェクトにするなどの択を考えるべきである。
3. サービスアカウント発行は乱発しない。システム and 環境ごとに行う
4. サービスアカウント、IAM発行したらチャットツールで報告。メンションはつけなくてよい。

### 同チーム内での質問 ⇒ システムエラー発生パターン

1. 急ぎであればすぐに質問。急ぎでなければ、1日置く。(自分の勘違いの可能性もあるので)
2. 実験のための最小コードを作り、実行できるか試す。システムに複雑に紐づいてる場合などはこのステップはスキップする。
3. エラーが出た場合エラーメッセージをそのままチャットツールに貼る。貼る際は、コードブロック化を忘れずに。
4. エラーが起こった際の状況を共有。時系列順に起こった事象をそのまま書く。
5. 最小コードの共有。または実行箇所の共有。

### データ可視化のデータ

1. BIツールによってはデータをBIツール側で保存できることもある。ただし、JOINやデータが多いなどでパフォーマンス劣化のおそれがあるので、簡単にできない場合だったり自分の分析に使う場合はデータに直接アクセスして分析した方がいい。

### SQLの書き方

- SELECT, INSERT, WHERE, ORDER BY, GROUP BYなどのSQLクエリの句は大文字
- テーブル名、カラム名は小文字
- SQLクエリの句の次の行は1つインデントあける。SQLクエリの句の中身の記述が終われば元に戻す。

### 分析パターン

分析とは比較である

- 比較
    - 時間軸の比較
        - 前後の比較
        - 前月、前年の比較
    - 地理的な比較
    - グルーピングによる比較
    - 全体と個の比較
- グルーピング
    - 階層分類
    - カテゴリ分類
    - クラスタ分析
    - 条件分類
- 特異点抽出
    - 特定の数値が急激に上がる
    - 特定の数値が急激に下がる

### 調査パターン

分析に必要なデータを調査するパターン

Aはxであるが、Bはxではない

Aはxではないが、Bはxである

- 比較
    - 時間軸の比較
    - 地理的な比較

### 仮説パターン

仮説のインパクトの大きさ ⇒ 情報の鮮度？

- A, Bは独立した集団である。Aはxであるが、Bはxではない
- A, Bは独立した集団である。Aはxではないが、Bはxである
- 

### データベースのデータ不備の調査

### バッチ作成

- CloudFunction + CloudPubsub + CloudScheduler
- CloudRunJobs ⇒ プレビュー
- CloudRun + CloudScheduler + Pubsub ⇒ セキュリティを担保できるか？
- ECS
- (通常インスタンスに載せた上で)Digdag ⇒ サーバーレスにすることは可能か？
- (通常インスタンスに載せた上で)Airflow ⇒ サーバーレスにすることは可能か？

### データ提供パターン

分析などを外部に委託する時に、データを提供する場合がある。

この時、委託先の人を自前の環境に招待するか使えるようにする必要がある。

外部に提供するツールのパターンとして以下のようなものがある。

- GCPプロジェクトBigQueryのAnalytics hub
- snow flakeのmarket place

招待する場合は以下に気をつける必要がある。

- 付与権限
    - GCPの場合はBigQuery閲覧者とジョブユーザーをベースに、データセットに対して編集権限をつけるのがいいだろう。
- 上記の提供に合わせてだが、AWSにせよGCPにせよ支払いアカウントとプロジェクトは別管理となっているので、支払いアカウント自体を別にするのもあり。

## 管理システム

### memo

- oauth認証できるデータベース(BigQueryなど)はアクセス用をシステム化した方がいい
- 理由としては以下の通りである
    - gitとの連携
    - 実行の再現性
    - ドキュメント作成
    - カラムの統一的な定義(あるいは、どうしようもない理由で差分が発生した場合に差分を知るため)

### reminder

- 雑務が多い

### SQL管理テンプレート

- 似たようなSQLが頻出するので、管理できればベスト
- テンプレートからSQLを作る

### BIツールとsql管理フォルダの連携

- xxxxx

### 汎用的データ管理ツール

- データ分析において、データを入れるということは重要なことである。
- BigQueryはUI的にも結構いいが、さすがに一般人的には難しそう
- システム候補
    - スプレッドシート
    - デスクトップアプリ

### 依頼管理ツール

- 依頼の方向性を管理する

### アラート

- 分析用のアラート
- データ欠損のアラート
- システムアラート

## クエリ

### 重複削除

1. DISTINCT句の利用
2. GROUP BY句の利用
3.  ROW_NUMBER関数の利用

- DISTINCTは重複を削除する句である。
- ROW_NUMBER関数は順番付けの関数である。
    - 例えば、同様のデータがあって最新に入れたもののみほしいという場合はROW_NUMBER関数で順番をつけて1番目のものを取得という風にすると良い。

### n日後

xを販売日

yをデータ集計日とする

販売からn日後までの累計は y - x ≤ nである。

例えば商品の売上を比較したい時、同じ時間単位に揃えて知りたいといった時がある。

そういった場合、発売からn日後のnをパーティションとするとよい。

### 条件集計(縦横展開集計)

col1が真偽値

col2が数値型とする

```markdown
SELECT
	SUM(IF(col1, col2, 0)) AS col2
FROM
	tbl
```

のように条件をつけた集計が可能である。

こうすることにより、集計可能なデータを縦持ちから横に展開することができる。

### 横縦展開

```sql
SELECT col1, col2 AS colx FROM tbl
UNION ALL
SELECT col1, col3 AS colx FROM tbl
UNION ALL
SELECT col1, col4 AS colx FROM tbl
UNION ALL
SELECT col1, col5 AS colx FROM tbl
```

### 圧縮集計

現在の累計を出す時の節約手法である。

例えば、商品販売データに対して累計を出したい。ただし、保存しているのは日毎のデータとする。

この時、毎回一気に取得してもいいがデータが大きくかつクエリごとの従量課金だとお金がものすごいかかる可能性がある。

簡易的圧縮集計は予め月毎に集計しておき、累計を出したい時にその月毎のデータを取得する。

## ドキュメント

### データベースのドキュメント

- カラム名、説明のテーブル
- 定義クエリ(あれば)

### やってはいけないこと制約条件のドキュメント

## tips

### BigQuery

- schema_jsonがほしい時は、テーブルをクリックし、スキーマ欄からカラムを全てクリックしてコピー ⇒ JSON形式でコピーをすると手に入れることができる。

### SQL保存

- githubで保存する
- schema_jsonはテーブル作成情報を持ったjson
- createはテーブルのcreate文
- inquiryは調査や問い合わせを受けたとき
- batchは定期バッチ(アプリケーション外の時やアプリケーション調査でのメモ用)
- フォルダ構造は下記の通り
    - db
        - {db名1}
            - schema_json
            - create
            - inquiry
            - batch
        - {db名2}
            - schema_json
            - create
            - inquiry
            - batch
    - bi
        - {bi名1}
            - datasource
        - {bi名2}
            - datasource
    - dependency
    - README.md

### データベースにおけるドキュメント

```markdown
# domain1

## テーブル

|column名|概要|
| --- | --- |
|カラム名1|内容1|
|カラム名2|内容2|

```