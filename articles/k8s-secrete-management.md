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
* Kubernetes External Secrets (Deprecated)
* External Secrets Operator
* Secret Storage CSI
* Vault by HashiCorp

参考記事
[Kubernetes External Secrets が非推奨になるので External Secrets Operator と Secret Storage CSI を比較する](https://mixi-developers.mixi.co.jp/compare-eso-with-secret-csi-846ed8b1c9b)
