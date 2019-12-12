# po3rinの開発合宿感想

## 作業

### 1日目

Goの```strings.Index```の内部実装のコードリーディング
[Rabin-karp](https://ja.wikipedia.org/wiki/%E3%83%A9%E3%83%93%E3%83%B3-%E3%82%AB%E3%83%BC%E3%83%97%E6%96%87%E5%AD%97%E5%88%97%E6%A4%9C%E7%B4%A2%E3%82%A2%E3%83%AB%E3%82%B4%E3%83%AA%E3%82%BA%E3%83%A0) アルゴリズムの調査

### 2日目

[Bloom filter](https://en.wikipedia.org/wiki/Bloom_filter) の調査とGoによる実装
Rolling hash を使った Bloom filter のGo実装

## アウトプット

rolling hash を使った Bloom filter のGo実装
https://github.com/po3rin/go_playground/tree/master/bloomfilter

Goによる Rabin-karp アルゴリズムの実装の解説記事
https://qiita.com/po3rin/items/07d51249629390a6201a

## 言語化したレビュー

### 画像処理コードの変数
* 画像処理においては変数名を画像の属性別に```src```や```dist```、```mask```などと統一するとGoの画像パッケージと書き方が統一できて読み手にも易しい(Pythonでも同じような感じらしい？)

### インターフェースをどのようにコンパクトにするか
* インターフェースとしてなるべく定義するメソッドは減らす
* 個人的にはGetter、Setterより１つ上の粗さの振る舞いで粒を揃えたい
* Getter、Setterを振る舞いとして定義してしまうと内部でデータを持つものがインターフェースを実装することが確定してしまい、インターフェースを実装できるものの抽象度が下がる。

この辺も記事にしたい

## 感想
* 個人的にGoというよりかはアルゴリズムの勉強に寄ってしまった気がする
* GitHub上のレビューより、言葉でのレビューの方がレビューの広がりが生まれるなと
* 定期的に進捗共有をしていたのでだらだらとしなくて良い
