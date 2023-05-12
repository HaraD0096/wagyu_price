# Git Lesson

## リモートリポジトリとローカルリポジトリとはそれぞれ何でしょうか？
- リモートリポジトリとは、クラウド上で保存されるリポジトリのこと。ローカルリポジトリとは、各デバイスごとに保存されるリポジトリのこと。リポジトリとは、フォルダーに似た、データをまとめて保存しておく箱のようなもの。


## プッシュとマージの違いは何でしょうか？
- プッシュはローカルリポジトリ上にある現在のブランチのデータを、リモートリポジトリ上にある指定したブランチへデータを同期させること。マージはローカルリポジトリ上のブランチのデータを、現在チェックアウト中のブランチへ同期させること。大きな違いとしては、プッシュはマージと違い、ローカルリポジトリ上でデータをリモートリポジトリへ同期することができるため、ローカルリポジトリ上で行った作業をインターネットを介して他人と共有することが可能である。


## コミットとプッシュの違い
- コミットとは、ローカルリポジトリ上で変更を行ったデータのセーブ地点を作ること。このセーブ地点はログという形で保存されている。プッシュとの大きな違いとしては、プッシュで同期するデータはコミットのログを参照しているので、コミットしていない状態でプッシュをしてもエラーが出たり、リモートリポジトリの方で変更したデータの同期がされていなかったりしてしまう点である。


## コミットのメッセージはどのように書いてあげるのが最適でしょうか？
- コミットのメッセージはprefixを用いながら、データの何を変更・実装したのか明確に簡潔に書いてあげるのが適切である。
- prefixには以下のような種類がある。
  - feat: 新機能の追加
  - fix: バグ修正
  - refactor: リファクタリング
  - docs: ドキュメントの修正
  - test: テストの追加や修正
- 具体的には以下のようにコミットのメッセージを残すのが適切である。
  - feat: ユーザー登録機能を追加
  - fix: ログイン画面でのエラーハンドリング修正
  - docs: APIドキュメントを更新
  - style: インデントをタブからスペースに変更
  - refactor: 複雑な処理を単純化
  - test: ユーザー登録の結合テストを追加
  - chore: 開発環境の設定ファイルを更新

## ローカルでマージするフローと、プルリクエストでマージするフローの違いは何でしょうか？
- ローカルでマージすると、ローカルリポジトリで変更されたデータをローカルリポジトリのブランチに同期することができる。プルリクエストでマージすると、リモートリポジトリに保存されているデータを、リモートリポジトリのブランチに同期することができる。プルリクエストでマージを行うことで、リモートリポジトリに保存してある他人のデータを同期することが可能となる。
  - ローカルでマージする場合
    - メリット
      - 小規模な修正や急ぎの修正など、すぐに反映させたい変更を簡単にマージできる。
      - 開発者の権限でマージできる。
    - デメリット…
      - コードレビューがないため、品質管理やバグの検出が難しくなる。
      - 他の開発者とのコミュニケーションや議論が制限されるため、チームの協力による品質向上が難しくなる。
  - プルリクエストでマージする場合
    - メリット
      - プルリクエストを通じて他の開発者にコードのレビューを依頼できる。品質向上やバグの検出がしやすくなる。
      - プルリクエストには変更内容や関連する情報が記録されるため、将来の参照や文書化に役立つ。
    - デメリット
      - プルリクエストの作成や承認、マージには追加の手順と時間が必要。
      - プルリクエストが承認を待つ間、マージが遅れる場合がある。
      
## コンフリクトを起こしてしまった場合、どう対処すべきですか？
- コンフリクトを起こしてしまった場合、以下の3通りの方法で変更を取り込む。
  1. 先にマージされた変更内容を取り込む。
  2. 後にマージしようとしている変更内容を取り込む。
  3. どちらの変更内容も取り込む。
- どの方法を取ればいいかわからない、または少しでも意図が読み取れない処理とぶつかってしまった場合は、そのソースコードを書いた人と相談しながら対処する。