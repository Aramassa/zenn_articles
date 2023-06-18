---
title: "Vector DB の比較"
emoji: "😸"
type: "tech"
topics: ["ChatGPT", "Generative AI", "OpenAI", "Vectorstore"]
published: false
---

# 概要

最近はやりの生成AIが提供する API を活用するためには、ベクトル化されたデータが必要になります。
LangChain などでも重要な役割を果たしているベクトル化されたデータですが、どのようなものがあるのか、どのような特徴があるのかをまとめてみました。

# どのようなものがあるか？

* Elasticsearch
* Qdrant
* Pinecone

の３つを比較してみました。

## それぞれの特徴

| 名称 | 提供形態 |
|---|---|
| Elasticsearch | オンプレミス、クラウド |
| Qdrant | オンプレミス、クラウド |
| Pinecone | クラウド |

## 比較項目

* 性能面
* 機能面
* 運用/その他

## 性能面での比較項目

* ベンダーが推奨する用途
* スループット上限（理論上）
* スケーラビリティ

## 機能面での比較項目

[Qdrant Benchmark] によると、シングルノードでの性能はQdrant は Elasticsearch よりもだいぶ性能が高い

Pinecone は [Integration の面](https://docs.pinecone.io/docs/elastic)で Qdrant よりも優れていそう

## 運用/その他での比較項目

* 利用者数
* セキュリティ
* ベンダーが推奨する用途


# 参考リンク

- [Qdrant]
  - [Qdrand Benchmark]
- [Pincone]
- [Elasticsearch]


# 参考記事

みんな結構気になっているようだが、まだまだ比較となると記事が少ない

[Not All Vector Databases Are Made Equal(https://towardsdatascience.com/milvus-pinecone-vespa-weaviate-vald-gsi-what-unites-these-buzz-words-and-what-makes-each-9c65a3bd0696)

[Qdrant]: https://qdrant.tech/
[Qdrand Benchmark]: https://qdrant.tech/benchmarks/
[Open AI api]: https://openai.com/blog/openai-api/
[Pinecone]: https://www.pinecone.io/
[Elasticsearch]: https://www.elastic.co/jp/elasticsearch/

* What is a Vector Database
  * https://www.pinecone.io/learn/vector-database/
* Rust製のベクトルデータベースQdrantを試してみる
  * https://dev.classmethod.jp/articles/qdrant-first-step/
    * アーキテクチャなども書かれている

---

* VectorDB の `dimentions` とは?
* pinecone の namespace とは？

