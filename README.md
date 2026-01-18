# 『図解Amazon Bedrock徹底解説』
<br>

Amazon Bedrockは、AWS（Amazon Web Services）が提供する、**生成AIアプリケーションを構築・運用するためのフルマネージド型プラットフォーム（実行基盤）** です。
<br>


<img src="images/amazon_bedrock_technical_guide.png" width="400" alt="図解Amazon Bedrock徹底解説">


本サイト『**図解 Aamzon Bedrock徹底解説**』は、筆者が Amazon Bedrock を学習・検証する過程で記録してきたメモをもとに構成しています。

Amazon Bedrockによる**AIエージェント開発**に取り組む方々にとって、本サイトが少しでも参考になれば幸いです。

なお、掲載内容には筆者の主観による要約や再構成が含まれており、サンプルコードや解説のご利用にあたっては、ご自身の判断と責任にてお願いいたします。

また、本サイトの内容は今後も適宜、更新・修正される可能性があります。あらかじめご了承ください。
<br>

2026年1月15日
<br>

**主よ、私が声をあげて叫ぶとき、聞いてください。私をあわれみ、私に答えてください。 **<br>
（『新改訳聖書』詩編27:7）
<br>

### 著者プロフィール
---
#### 李 昌桓（LEE CHANFUAN）

- 『<a href="https://www.creationline.com" target="_blank" rel="noopener noreferrer">クリエーションライン株式会社</a>』 に在籍
- 現代的なデータ基盤構築を専門とするソリューションアーキテクト、リードエンジニアとして活動中
- 代表的なプロジェクト:
	- 大手通信キャリアにおけるDWH基盤の設計・構築
	- Donso Factory IoT、ヨドバシカメラ、モノタロウなどにおけるデータモダナイゼーションを推進

#### 著書

- Amazon Cloudテクニカルガイド ― EC2/S3からVPCまで徹底解析、インプレスジャパン、2010
- Amazon Elastic MapReduceテクニカルガイド ― クラウド型Hadoopで実現する大規模分散処理、インプレスジャパン、2012
- Cypherクエリー言語の事例で学ぶ グラフデータベース Neo4j、インプレスR&D、2015
- Neo4jを使うグラフ型データベース入門（共著）、リックテレコム、2016
- RDB技術者のためのNoSQLガイド（共著）、秀和システム新社、2016
- [図解 Strandsエージェント徹底解説](https://github.com/awk256/strandsagents)、2026（Web公開※）  
- [図解 Amazon Bedrock徹底解説](https://github.com/awk256/amazon-bedrock)、2026（Web公開※）  
 ※本書は紙での出版予定はありません。

 <br>

### 掲載内容について
---
**『図解 Amazon Bedrock』** は、基本的に Strands エージェントおよび AWS の公式ドキュメント、ならびに GitHub 上のサンプルコードをベースに構成しています。  
掲載しているサンプルコードの中には、筆者の創意工夫によって独自に作成したものも含まれており、その場合はタイトルの末尾に「＋」を付けて区別しています。

- [Strands User Guide/](https://strandsagents.com/latest/documentation/docs/)
- [Strands Githubs](https://github.com/strands-agents/)
- [Strands Samples](https://github.com/strands-agents/samples)
- [ Strands Python API](https://strandsagents.com/latest/documentation/docs/api-reference/python/agent/agent/)
- [Amazon Bedrock Documention](https://docs.aws.amazon.com/ja_jp/bedrock/?icmpid=docs_homepage_ml)
- [Amazon Bedrock AgentCore Developer Guide](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/what-is-bedrock-agentcore.html)
- [Amazon Bedrock AgentCore Samples](https://github.com/awslabs/amazon-bedrock-agentcore-samples)
<br>

### 著作権・ライセンス
---
本サイトの著作権は著者に帰属します。

 - AI学習・研究目的: 出典を明記の上、自由にご利用いただけます。
 - 営利・二次利用: 無断転載や有償イベントでの利用は禁止します。
 - 改変: 自由ですが、すべて自己責任となります。

 詳細は [LICENSE](LICENSE.md) ファイルをご確認ください。
　<br>

### 章立てについて
---
#### 📌構成
-  [メジャー番号]-[マイナ番号]-[リビジョン番号]
-   [章]-[節]-[項]の構成、又は[章]-[項]の構成
<br>

### 目次 
---
#### 010.AmazonBedrock
- [010-000-000.Amazon Bedrockとは](010.AmazonBedrock/010-000-000.Amazon%20Bedrockとは.md)
　
#### 020.BedrockAgentCore
- [020-000-000.AgentCoreとは](020.BedrockAgentCore/020-000-000.AgentCoreとは.md)
- [020-010-010.ゲートウェイ](020.BedrockAgentCore/020-010-010.ゲートウェイ.md)  
- [020-010-012.ターゲット](020.BedrockAgentCore/020-010-012.ターゲット.md)  
- [020-010-020.ポリシー](020.BedrockAgentCore/020-010-020.ポリシー.md)  
- [020-010-030.メモリ(記憶)](020.BedrockAgentCore/020-010-030.メモリ(記憶).md)  
- [020-010-031.短期記憶](020.BedrockAgentCore/020-010-031.短期記憶.md)  
- [020-010-032.長期記憶(オプション)](020.BedrockAgentCore/020-010-032.長期記憶(オプション).md)  
- [020-010-040.アイデンティティ](020.BedrockAgentCore/020-010-040.アイデンティティ.md)  
- [020-010-050.ブラウザー](020.BedrockAgentCore/020-010-050.ブラウザー.md)  
- [020-010-060.コードインタープリター](020.BedrockAgentCore/020-010-060.コードインタープリター.md)  
- [020-020-010.ラインタイム](020.BedrockAgentCore/020-020-010.ランタイム.md) 
- [020-030-010.可観測性](020.BedrockAgentCore/020-030-010.可観測性.md)  
- [020-030-020.評価](020.BedrockAgentCore/020-030-020.評価.md) 

#### 030.Bedrockナレッジベース　
- [030-000-000.Bedrockナレッジベースとは](030.Bedrockナレッジベース/030-000-000.Bedrockナレッジベースとは.md)
- [030-010-010.AmazonTextract](030.Bedrockナレッジベース/030-010-010.AmazonTextract.md)

#### 040.Bedrockエージェント
- [040-000-000.Bedrockエージェントとは](040.Bedrockエージェント/040-000-000.Bedrockエージェントとは.md)
- [040-010-010.マルチエージェントコラボレーションとは](040.Bedrockエージェント/040-010-010.マルチエージェントコラボレーションとは.md)
- [040-010-011.凄く煩雑だ！この先、どこに向かっているのか](040.Bedrockエージェント/040-010-011.凄く煩雑だ！この先、どこに向かっているのか.md)

#### 050.Bedrockプロンプトマネージメント
- [050-000-000.Bedrockプロンプトマネジメントとは](050.Bedrockプロンプトマネージメント/050-000-000.Bedrockプロンプトマネジメントとは.md)
- [050-010-010.プロンプトビルダーによるプロンプト開発](050.Bedrockプロンプトマネージメント/050-010-010.プロンプトビルダーによるプロンプト開発.md)

#### 060.Bedrockガードレール
- [060-000-000.Bedrockガードレールとは](060.Bedrockガードレール/060-000-000.Bedrockガードレールとは.md)
- [060-010-010.Bedrockガードレールの設定・テスト](060.Bedrockガードレール/060-010-010.Bedrockガードレールの設定・テスト.md)
- [060-010-020.Bedrockエージェントにおけるガードレールの設定](060.Bedrockガードレール/060-010-020.Bedrockエージェントにおけるガードレールの設定.md)

#### 070.Bedrockフロー
- [070-000-000.Bedrockフローとは](070.Bedrockフロー/070-000-000.Bedrockフローとは.md)

#### 080.Berock自動推論
- [080-000-000.Bedrock自動推論とは](080.Berock自動推論/080-000-000.Bedrock自動推論とは.md)

#### 090.Bedrockデータオートメーション
- [090-000-000.Bedrockデータオートメーションとは](090.Bedrockデータオートメーション/090-000-000.Bedrockデータオートメーションとは.md)

#### 100.実行環境
- [800-000-000.事前準備](800.実行環境/800-000-000.事前準備.md)

#### 900.サンプルコード
- [900-010-010.朝まで生テレビーAgentCore版＋](900.サンプルコード/900-010-010.朝まで生テレビーAgentCore版＋.md)
- [900-010-011.AgentCore版のプロビジョニング＋](900.サンプルコード/900-010-011.AgentCore版のプロビジョニング＋.md)
- [900-020-010.朝まで生テレビー短期記憶版＋](900.サンプルコード/900-020-010.朝まで生テレビー短期記憶版＋.md)
- [900-020-011.短期記憶の検索＋](900.サンプルコード/900-020-011.短期記憶の検索＋.md)
- [900-020-020.朝まで生テレビー長期記憶版＋](900.サンプルコード/900-020-020.朝まで生テレビー長期記憶版＋.md)
- [900-020-021.長期記憶の検索＋](900.サンプルコード/900-020-021.長期記憶の検索＋.md)
- [900-030-010.疑似粗大ごみ判定システムの概要＋](900.サンプルコード/900-030-010.疑似粗大ごみ判定システムの概要＋.md)
- [900-030-012.画像から粗大ごみ判定ーナレッジベースの実装&テスト＋](900.サンプルコード/900-030-012.画像から粗大ごみ判定ーナレッジベースの実装&テスト＋.md)
- [900-030-011.画像から粗大ごみ判定ーベーシンク版＋](900.サンプルコード/900-030-011.画像から粗大ごみ判定ーベーシンク版＋.md)
- [900-040-010.朝まで生テレビーBedrockエージェント版＋](900.サンプルコード/900-040-010.朝まで生テレビーBedrockエージェント版＋.md)
- [900-040-011.朝まで生テレビーBedrockエージェントによる開発手順＋](900.サンプルコード/900-040-011.朝まで生テレビーBedrockエージェントによる開発手順＋.md)

