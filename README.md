# 発展プログラミングの課題制作の成果物  
これは2025年発展プログラミングの課題制作の成果物になります。  

## 使用した技術  
- HTML
- CSS
- JavaScript
- Google API
- Java
- Spring Boot
- Docker（コンテナ実行対応）

## 機能  
- 大阪の天気予報(API)
- ペイント機能
- パズル
- 福笑い
- 電卓
- Googleによるログイン機能
- 星占い
- 名前診断
- タイピング練習
- 月の位置取得
- 時計
- 今日の記念日

# 実行方法  

## 1. Googleログイン用設定
- `src/main/resources/application.properties` にGoogleの `client-id` と `client-secret` を記載してください。
- セキュリティを重視する場合は、環境変数から値を読み込むことも可能です。
  例：
  ```properties
  spring.security.oauth2.client.registration.google.client-id=${GOOGLE_CLIENT_ID}
  spring.security.oauth2.client.registration.google.client-secret=${GOOGLE_CLIENT_SECRET}
  ```
- Docker Composeで環境変数を渡す場合は `compose.yml` の `environment` セクションに追加してください。

## 2. Dockerでの起動
1. プロジェクトルートで下記コマンドを実行します。
   ```zsh
   cd java-windows3.1-springboot-main/demo
   docker compose up -d --build
   ```
2. ブラウザで [http://localhost:8080](http://localhost:8080) にアクセスしてください。

## 3. サービスの停止
```zsh
docker compose down
```

## 4. ローカル実行（従来通り）
- `DemoApplication.java` を直接起動、または
- `./mvnw spring-boot:run` で起動できます。

## 注意事項
- Googleログインを利用する場合、Google Cloud ConsoleでリダイレクトURI（例: `http://localhost:8080/login/oauth2/code/google`）を登録してください。
- `application.properties` の設定値は本番運用時は環境変数や `.env` で管理することを推奨します。

# 工夫した点、学んだこと  
- APIを使って天気、記念日を取得したこと。またそれらをする技術を学んだこと。
- Spring Boot FrameWorkを使うことによるMVCモデルについていろいろ考えることができた。
- Google APIによるOAuth2のログイン認証を導入することによる、学びを得た。
- Spring Securityによる、CSRF対策によってトークン付与をしないとセキュリティの観念からサーバにエラーをきたすことが分かった。
- 工夫としてindex.htmlにはVue.jsによるフロントエンドにUIの見やすさを大幅に向上させれた。
- Themeleafとjsonについて深く学びを得たこと。
- 初めての動的webだったのでエラーが多発したが共同開発のおかげで何とか解決したこと。

# 最後に  
- こんなにいろいろなOSSを出してくださった皆さんに感謝を。
- 爆速で依存関係を解決してくださったVScodeには頭が上がりません。
- 夜な夜な、開発に付き合ってくれた友達にも感謝してます。
- このread meを読んでくださったあなたにも感謝です。

以上YAMAでした。
