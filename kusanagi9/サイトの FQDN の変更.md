# KUSANAGI9 ~ サイトの FQDN の変更

## 全手順

1. nslookup でドメインネームの浸透状況を確認
1. プロビジョン名を確認
1. 現在の FQDN 名を確認
1. FQDN を変更
1. SSL を変更


## 1. nslookup でドメインの浸透状況を確認

```
nslookup new-domain.com
```

上記コマンドを 10 回程度連続で実行し、OK かどうか確認する。

ドメインがきちんと浸透していないにに作業を継続すると、コマンドの実行に失敗し余計な手間がかかることがあるので、浸透状況をしっかり確認する必要がある。


## 2. プロビジョン名を確認

```
kusanagi list
```

で、プロビジョンの一覧が表示される。
その中から対象のプロビジョン名を確認する。

以下の例では対象のプロビジョン名を `your-provision` とする。


## 3. 現在の FQDN 名を確認

```
kusanagi status your-provision
```

プロビジョン名を間違ってしまったりするとやっかいなので、現在の FQDN を確認する。


## 4. FQDN を変更

```
kusanagi configure --fqdn new-domain.com your-provision
```


## 5. SSL を変更

```
kusanagi ssl --email your-email.jp your-provision
```

以上で、サイトの FQDN の変更が完了です。


## メモ

* FQDN の変更によりサイトの URL が変わるので、WP 上での設定変更も必要なはずであるが、特に行わなくても大丈夫なようである。
  
  UpdraftPlus の有償版にサイト URL の変更機能があるが、そのためだけにお金を払うほどのものでもない可能性が高そう。
