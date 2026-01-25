---
title: "SC-200試験 - 無料の実際のQ&A、7ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/7/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#61 トピック1

Microsoft 365 サブスクリプションをご利用で、Microsoft Defender XDR を使用しています。Microsoft  
  
Defender for Endpoint が、よく使用される実行ファイルに対してアラートを生成すると、アラート疲れが発生することがわかりました。  
  
アラートを調整する必要があります。  
  
アラート調整ルールでアラートに対して実行できるアクションは、次の 2 つのうちどれですか。正解はそれぞれ完全な解決策を示しています。  
  
注: 正解は 1 点です。

- A. 削除
- B. 隠す
- C. 解決する
- D. マージ
- E. 割り当てる

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)

**正解:** BC [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)  

**解説:**
Microsoft Defender for Endpointのアラート調整（チューニング）ルールで作成できるアクションは以下の2つです。

1. **解決する (Resolve/Auto-resolve)**: 条件に一致するアラートを自動的に「解決済み」ステータスにします。
2. **隠す (Hide)**: 条件に一致するアラートをビューから隠します（ユーザーには表示されなくなりますが、データとしては存在します）。
これらは「抑制ルール (Suppression rule)」の設定項目として選択できます。

*コミュニティ投票の配分*

紀元前（100％）

質問#62 トピック1

注: このセクションには、同じシナリオおよび問題に関する 1 つ以上の質問セットが含まれています。各質問は、問題に対する固有の解決策を提示します。解決策が定められた目標を満たしているかどうかを判断する必要があります。セット内の複数の解決策が問題を解決できる可能性があります。また、セット内のどの解決策も問題を解決できない可能性もあります。  
  
このセクションの質問に回答した後は、戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Microsoft  
  
365 サブスクリプションを所有しています。  
  
サードパーティ製のウイルス対策製品がインストールされ、Microsoft Defender ウイルス対策がパッシブ モードになっている Windows デバイスが 1,000 台あります。  
  
サードパーティ製のウイルス対策製品では検出されなかった悪意のあるアーティファクトからデバイスが保護されていることを確認する必要があります。  
  
解決策: エンドポイントの検出と対応 (EDR) をブロック モードで構成します。  
  
これは目標を満たしていますか?

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)  

**解説:**
サードパーティ製アンチウイルスを使用している環境（Defenderウイルス対策がパッシブモード）で、サードパーティ製品が見逃した悪意のあるアーティファクトを検出し、ブロックするには、**「ブロックモードでのEDR (EDR in block mode)」** を有効にします。
これにより、Defender for Endpointはパッシブモードであっても、EDR機能によって検出された脅威を積極的にブロック・修復することができます。これは追加の防御層として機能します。

*コミュニティ投票の配分*

A（86％）

14%

質問#63 トピック1

注: このセクションには、同じシナリオおよび問題に関する 1 つ以上の質問セットが含まれています。各質問は、問題に対する固有の解決策を提示します。解決策が定められた目標を満たしているかどうかを判断する必要があります。セット内の複数の解決策が問題を解決できる可能性があります。また、セット内のどの解決策も問題を解決できない可能性もあります。  
  
このセクションの質問に回答した後は、戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Microsoft  
  
365 サブスクリプションを所有しています。  
  
サードパーティ製のウイルス対策製品がインストールされ、Microsoft Defender ウイルス対策がパッシブ モードになっている Windows デバイスが 1,000 台あります。  
  
サードパーティ製のウイルス対策製品では検出されなかった悪意のあるアーティファクトからデバイスを保護する必要があります。  
  
解決策: コントロールされたフォルダー アクセスを構成します。  
  
これは目標を満たしていますか?

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)  

**解説:**
**「コントロールされたフォルダーアクセス (Controlled folder access)」** は、ランサムウェア対策機能であり、信頼されていないアプリによる保護されたフォルダー内のファイル変更をブロックします。
これは特定の種類の攻撃（ランサムウェア等）には有効ですが、質問にある「サードパーティ製品で検出されなかった一般的な悪意のあるアーティファクト」すべてからデバイスを保護するための広範なソリューションではありません。この目的にはEDRのブロックモードが適切です。

*コミュニティ投票の配分*

B（100％）

質問#64 トピック1

注: このセクションには、同じシナリオおよび問題に関する 1 つ以上の質問セットが含まれています。各質問は、問題に対する固有の解決策を提示します。解決策が定められた目標を満たしているかどうかを判断する必要があります。セット内の複数の解決策が問題を解決できる可能性があります。また、セット内のどの解決策も問題を解決できない可能性もあります。  
  
このセクションの質問に回答した後は、戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Microsoft  
  
365 サブスクリプションを所有しています。  
  
サードパーティ製のウイルス対策製品がインストールされ、Microsoft Defender ウイルス対策がパッシブ モードで稼働している Windows デバイスが 1,000 台あります。  
  
サードパーティ製のウイルス対策製品では検出されなかった悪意のあるアーティファクトからデバイスを保護する必要があります。  
  
解決策: 自動調査および対応 (AIR) を有効にします。  
  
これは目標を満たしていますか?

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)  

**解説:**
**「自動調査および対応 (AIR)」** は、アラートが発生した後に自動的に調査を行い、脅威を修復する機能です。
これは事後対応のプロセスを自動化するものであり、サードパーティ製AVが見逃した脅威を「検出してブロックする（保護する）」という予防的なレイヤー（特に実行時のブロック）としては、EDRのブロックモードの方が直接的な解決策となります。AIRはパッシブモードのデバイスでも動作しますが、主な目的はアラート疲れの軽減と修復の自動化です。

*コミュニティ投票の配分*

B（100％）

質問#65 トピック1

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションをお持ちです。  
  
デセプションルールを実装する必要があります。ソリューションでは、ルールの適用範囲を限定できる必要があります。  
  
まず何を作成すればよいでしょうか？

- A. デバイスグループ
- B. デバイスタグ
- C. ハニートークンエンティティタグ
- D. センシティブエンティティタグ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)  

**解説:**
Microsoft Defender XDRのデセプション（欺瞞）機能のルール適用範囲を特定のデバイスに限定するには、**「デバイスタグ (Device tag)」** を使用します。
デセプションルールの設定画面では、対象となるデバイスをフィルタリングするためにデバイスタグを指定することができます。ハニートークンエンティティタグ（C）は、特定のユーザーやデバイスを「ハニートークン（囮）」としてマークするためのもので、ルールの適用範囲（どのデバイスにデコイを展開するか）を制御するものではありません。

*コミュニティ投票の配分*

B（87％）

13%

質問#66 トピック1

注: このセクションには、同じシナリオおよび問題に関する 1 つ以上の質問セットが含まれています。各質問は、問題に対する固有の解決策を提示します。解決策が定められた目標を満たしているかどうかを判断する必要があります。セット内の複数の解決策が問題を解決できる可能性があります。また、セット内のどの解決策も問題を解決できない可能性もあります。  
  
このセクションの質問に回答した後は、戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Microsoft  
  
365 サブスクリプションがあります。  
  
サードパーティ製のウイルス対策製品がインストールされ、Microsoft Defender ウイルス対策がパッシブ モードになっている Windows デバイスが 1,000 台あります。  
  
すべての Windows デバイスは、Microsoft Defender for Endpoint にオンボードされています。サードパーティ製のウイルス  
  
対策製品では検出されなかった悪意のあるアーティファクトからデバイスが保護されていることを確認する必要があります。  
  
解決策: Live Response を有効にします。  
  
これは目標を満たしていますか?

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)  

**解説:**
**「Live Response」** は、セキュリティ管理者がリモートデバイスに接続して調査や修復アクション（ファイルの収集、プロセスの終了など）を行うための機能です。
これは手動による調査・対応ツールであり、自動的に悪意のあるアーティファクトを検出してブロックする常時保護機能ではありません。したがって、目標を満たしません。

*コミュニティ投票の配分*

B（100％）

## トピック2 - 質問セット2

質問1 トピック2

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。一部の質問セットには複数の正解がある場合もあれば、正解がない場合もあります。  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Azure  
Security Center を使用しています。Security  
Center でセキュリティ アラートを受信しました。Security  
Center でアラートを解決するための推奨事項を確認する必要があります。  
解決策: \[セキュリティ アラート\] からアラートを選択し、\[アクションの実行\] を選択して、\[将来の攻撃を防ぐ\] セクションを展開します。  
これで目標は達成されましたか?  

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)   [議論   28](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)  

**解説:**
Azure Security Center（現 Defender for Cloud）で「アラートを解決するための推奨事項」を確認する場合、通常はアラートページからではなく、**「推奨事項 (Recommendations)」** ブレードを直接確認します。
アラートの詳細ページには「将来の攻撃を防ぐ (Prevent future attacks)」というセクションが表示されることもありますが、これはアラートに関連する推奨事項へのリンクを提供するものであり、推奨事項の全体像を確認して包括的に対処するには、推奨事項ダッシュボードを使用するのが標準的な手順です。また、「アクションの実行」メニューの構成もバージョンによって異なるため、この手順が常に最適とは限りません。（※コミュニティ投票もBが多数です。）

*コミュニティ投票の配分*

B（74％）

A（26％）

質問2 トピック2

Azure Defender for Key Vault からアラートを受信しました。  
アラートは複数の不審な IP アドレスから生成されていることがわかりました。  
問題を調査する間、Key Vault のシークレットが漏洩する可能性を低減する必要があります。解決策はできるだけ早く実装し、正当なユーザーへの影響を最小限に抑える必要があります。  
まず何をすべきでしょうか？  

- A. キー コンテナーのアクセス制御設定を変更します。
- B. Key Vault ファイアウォールを有効にします。
- C. アプリケーション セキュリティ グループを作成します。
- D. キー コンテナーのアクセス ポリシーを変更します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)   [議論   16](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)  

**解説:**
Key Vaultへの不審なIPアドレスからのアクセスを検知した場合、調査中のシークレット漏洩リスクを最小限に抑えるための最良の初期対応は、**「Key Vaultファイアウォールを有効にする (Enable Key Vault Firewall)」** ことです。
ファイアウォールを有効にし、信頼できるネットワークや特定のIPアドレスのみにアクセスを制限することで、外部の攻撃者や不審なIPからのアクセスを即座に遮断できます。これにより、正当なユーザー（許可されたネットワークからのアクセス）への影響を抑えつつ、防御を固めることができます。

*コミュニティ投票の配分*

B（100％）

質問3 トピック2

ホットスポット -  
サポートされているすべてのリソースタイプに対してAzure Defenderが有効になっているAzureサブスクリプションがあります。LA1  
というAzureロジックアプリを作成します。LA1  
を使用して、Azure Security Centerで検出されたセキュリティリスクを自動的に修復する予定です。Security  
CenterでLA1をテストする必要があります。  
どうすればよいでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
注：正しい選択ごとに1ポイントが加算されます。  
ホットエリア：  
![](https://www.examtopics.com/assets/media/exam-media/04261/0005600001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)   [議論   37](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)

**正解:** ![](https://img.examtopics.com/sc-200/image415.png)

**解説:**
Azure Security Center（Defender for Cloud）のアラートや推奨事項に基づいてLogic Appを自動実行する場合、Logic App側では適切なトリガーを設定する必要があります。
**「Defender for Cloudのアラートが作成またはトリガーされたとき (When a Defender for Cloud Alert is created or triggered)」**: このトリガーを使用することで、セキュリティアラートが発生した際に自動的にLogic Appワークフローを開始し、修復アクションなどを実行できます。（推奨事項に対するトリガーもありますが、設問の「リスクを自動的に修復する」という文脈ではアラートトリガーが一般的です。）

質問4 トピック2

Azure Defender を使用する Microsoft 365 サブスクリプションを所有しています。RG1  
というリソースグループに 100 台の仮想マシンがあります。SecAdmin1  
という新しいユーザーにセキュリティ管理者ロールを割り当てます。SecAdmin1  
が Azure Defender を使用して仮想マシンにクイックフィックスを適用できるようにする必要があります。このソリューションでは、最小権限の原則を適用する必要があります。SecAdmin1  
にはどのロールを割り当てるべきでしょうか。  

- A. サブスクリプションのセキュリティリーダーロール
- B. 購読の寄付者
- C. RG1の貢献者の役割
- D. RG1のオーナー役割

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)   [議論   13](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/7/#)  

**解説:**
Azure Defender (Defender for Cloud) の「クイックフィックス (Quick Fix)」機能を使用して脆弱性を修復する場合、対象のリソース（この場合は仮想マシン）に対して変更を加える権限が必要です。

1. **セキュリティ閲覧者 (Security Reader)**: 読み取り専用であり、変更はできません。
2. **サブスクリプションの投稿者 (Subscription Contributor)**: 権限は十分ですが、RG1のみという要件に対して範囲が広すぎ、最小権限の原則に反します。
3. **RG1の投稿者 (Contributor on RG1)**: リソースグループRG1内のリソースに対して変更を加える権限があり、クイックフィックスの適用に必要な権限を満たしつつ、スコープも適切です。
4. **RG1の所有者 (Owner on RG1)**: 投稿者の権限に加え、アクセス権の管理も可能ですが、クイックフィックスの適用には不要な強すぎる権限です。
よって、**C. RG1の貢献者 (Contributor)** が最適です。

*Community vote distribution*

C (100%)

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/6/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 7 ページ目を表示しています。

410問 中**61 - 70** 問を表示
