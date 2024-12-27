# KUSANAGI9 ~ NGINX のリロード

※ 公開ドキュメントです。個人情報や秘密情報を記載しないこと


## NGINX conf ファイルのテスト

```
kusanagi nginx --test
```


## NGINX のリロード

```
kusanagi nginx --reload
```

なお、`--reload` は、セッションを切断しないという意味なので、SSL 更新時のようにセッションを切断すべき場合は
`--reload` を付けずに実行すること。
