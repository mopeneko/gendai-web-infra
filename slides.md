# 現代のWebインフラ

> 1/15 さわだLT

> Twitter @_m_vt

---

# 基本

- 「アプリケーションサーバ」というのは基本的に置かない
- アクセスがあった際に一定のリソースが割り当てられ、その上でプログラムが走る
- この実行モデルを**サーバレス**と呼ぶ
- 高負荷時のスケーリングも自動で行うことができる

---

# Amazon Web Services(AWS) におけるサーバレス

- AWS Lambda
  - **関数**を実行するためのサービス
  - 関数を記述するための独自のライブラリを用いる必要がある
- AWS Lambda@Edge
  - Cloudfront(AWSのCDN)のエッジサーバ上で動作するAWS Lambda
  - 詳細は後述
- AWS Fargate + AWS ECS
  - Fargate: コンテナを呼び出すサービス
  - ECS: コンテナを動かすサービス

---

# Google Cloud Platform(GCP)におけるサーバレス

- Google Cloud Functions
  - 関数を実行するためのサービス
  - AWS Lambda とは異なり、通常通り関数を定義してコマンドによってデプロイすれば良い
- Google Cloud Run
  - HTTPリクエストによってコンテナを実行するサービス
  - AWS とは異なり、複数のサービスを組み合わせる必要が無い
- Google App Engine
  - HTTPリクエストによってプログラムを実行するためのサービス
  - Dockerfile などの記述が不要なため、開発に集中できる

---

# これからのサーバレス

## エッジコンピューティングを利用したサービスが増えてくる

- デバイスと物理的に近い場所にある「エッジサーバ」上でプログラムを実行する
- より短い応答時間を実現できる

### サービス

- AWS Lambda@Edge
- Akamai EdgeWorkers
- Cloudflare Workers
