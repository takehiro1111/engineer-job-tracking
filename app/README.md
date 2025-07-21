```
npm install
npm run dev
```

```
open http://localhost:3000
```

# アプリケーションの概要
- エンジニアの転職活動(正社員、業務委託等の雇用形態問わず)における活動時の進捗管理アプリ

# REST APIの設計
- 画面表示するためだけのGETメソッドは省略して記載しております。
## 必須機能
### 認証
- 認証機能
  - ユーザー情報の作成
    - /auth/register
      - POST
        - パスワードのハッシュ化
  - ログイン
    - /auth/login
      - POST
  - ログアウト
    - /auth/logout
      - POST

- ログイン後の進捗一覧ページ
  - /processes
    - GET

### 進捗管理(メイン機能)
- 進捗の新規作成
  - /processes
    - POST
      - 簡易的なステータスや優先順位の変更はプルダウンで一覧画面から変更できるようにする。

- 優先順位、ステータス変更の簡易的な一覧画面での変更
  - /processes/:id
    - PATCH

- 進捗の削除(主に企業単位を想定)
  - /processes/:id
    - DELETE

- 企業ごとの詳細取得
  - /processes/:id
    - GET
      - 企業ごとのメリットデメリット等、細かい情報を見れる。

- 既存の情報を修正
  - /processes/:id
    - PUT

### ユーザー情報の管理
- ユーザー情報の取得
  - /user
    - GET

- ユーザー情報の更新(ログインに必要ない情報の入力含む)
  - /user
    - PUT

- ユーザー情報の削除
  - /user
    - DELETE


# テーブル設計

