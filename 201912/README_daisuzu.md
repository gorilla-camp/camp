# ゴリラの開発合宿感想

## やったこと

### 2019/12/07

リモートで[gopls](https://godoc.org/golang.org/x/tools/gopls)のコードリーディング。

- 目的: `gopls` で [workispace/symbol](https://microsoft.github.io/language-server-protocol/specifications/specification-3-14/#workspace_symbol) を使えるようにする。
    - サーバ側のcapabilitiesで `workispace/symbol` に対応していることを返すようにする必要がある
        - クライアントからの `initialize` リクエストを受け取った時にやるものというところまで調べた
    - 該当のメソッドはダミー実装になっている
        - `notImplemented` エラーを返すだけになっている

### 2019/12/08

`gopls` の改修。

#### 10:00〜12:00

- 決め打ちのデータで `workispace/symbol` を動かすところまで実装

#### 13:00〜19:00

- `ast.Inspect` などを使って `workispace/symbol` をそれっぽく動かすところまで実装

#### 自由時間

- @skanehira さんと
    - [http.Hijacker](https://golang.org/pkg/net/http/#Hijacker)を試す
    - [http.ListenAndServe](https://golang.org/pkg/net/http/#ListenAndServe)のコードリーディング

- `workispace/symbol` のレスポンスの順序/重複を改善
    - https://github.com/daisuzu/tools/blob/exp/workspace_symbol/internal/lsp/workspace_symbol.go

## まとめ
- みんなでワイワイしながらGoに触れることができてとても楽しかった
