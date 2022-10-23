---
title: "Kubernetes のシークレット管理"
emoji: "😸"
type: "tech"
topics: ["kubernetes"]
published: false
---

# Kubernetes のシークレット管理

* k8s 標準の secret は kubectl から丸見えになってしまうため、git などでコード管理できない（ただのbase64）

# 選択肢

* Sealed Secret
* [Kubernetes External Secrets (Deprecated)](https://github.com/external-secrets/kubernetes-external-secrets)
* [External Secrets Operator](https://external-secrets.io/v0.6.0/)
* Secret Storage CSI
* Vault by HashiCorp

## 参考記事
[Kubernetes External Secrets が非推奨になるので External Secrets Operator と Secret Storage CSI を比較する](https://mixi-developers.mixi.co.jp/compare-eso-with-secret-csi-846ed8b1c9b)

こちらの記事によると、 Secret Storage CSI は ArgoCD など、サードパーティ製アプリの Secret　管理と相性が悪そうなので、External Secrets Operator が選択肢としては良さそう （2022/10時点）。


## External Secrets が非推奨

https://github.com/external-secrets/kubernetes-external-secrets

>> This project has been deprecated. Please take a look at ESO (External Secrets Operator) instead https://github.com/external-secrets/external-secrets
> このプロジェクトは非推奨です。 代わりにESOを検討してください。

とのこと。

## External Secret Operator 導入の流れ

* GCP側
  * Project を作成
  * Secret Manager に Secret を作成
  * SAを作成し、SecretManager アクセスの権限を追加する
  * 作成したSA の Credential JSON を取得する(k8s設定用)
* k8s側
  * Helm Chart で Cluster にインストールする
  * GCP の SA アクセス用の [Secret を追加する]
  * [SecretStore を追加する]
  * [ExternalSecretを追加する]

[Secret を追加する]: https://external-secrets.io/v0.6.0/provider/google-secrets-manager/#gcp-service-account-authentication
[SecretStore を追加する]: https://external-secrets.io/v0.6.0/provider/google-secrets-manager/#update-secret-store
[ExternalSecretを追加する]: https://external-secrets.io/v0.6.0/provider/google-secrets-manager/#creating-external-secret
