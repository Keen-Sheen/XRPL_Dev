---
html: trust-lines-and-issuing.html
parent: tokens.html
blurb: トラストラインの特性と根本原理について説明します。
labels:
  - トークン
---
# トラストラインと発行

XRP Ledgerの[発行済み通貨](issued-currencies.html)は、XRP Ledger外部で _ゲートウェイ_ が保有する価値をしばしば表します。ユーザーがXRP Ledgerの残高をイシュアーに返却して清算するときには、XRP Ledger内でこれらの資金を発行するアドレスが、XRP Ledger外部で残高を払い戻すことが期待されます。

コンピュータープログラムは外界で約束を守ることを誰にも強制できないため、トラストラインは、イシュアーがあなたの代わりに保有する価値の量として、あなたが信頼できる量を設定する手段となります。信用のある大手金融機関は、お金のないルームメートに比べれば返済能力は高いため、トラストラインごとに異なる限度を設定して、XRP Ledgerでイシュアーがあなたから「借用」できる上限額を指定できます。イシュアーが債務不履行になった場合や、倒産した場合には、XRP Ledgerでの保有残高をその他の等価の資産と交換できなくなるため、設定した上限額まで失う可能性があります。（XRP Ledgerで引き続き発行済み通貨を保持または取引できますが、発行済み通貨に価値があると見なされる理由がなくなる可能性があります。）

次の2つの場合、残高が限度額を _超過_ しても、トラストラインにその残高を保有できます。[取引](decentralized-exchange.html)によりその通貨をさらに積み増しする場合と、トラストラインの限度を引き下げる場合。

トラストラインはレジャーのスペースを使用するため、[トラストラインにより、アカウントの準備金として保有する必要のあるXRPが増加します](reserves.html)。これは、信頼を受けているアカウントではなく、信頼を拡大しているアカウントに適用されます。

各トラストラインは、特定の[通貨コード][]に固有です。2つのアカウント間に作成できる各種通貨コードのトラストラインの数に制限はありませんが、どの通貨コードについても、作成できるトラストラインは1方向に1つだけです。

## トラストラインの設定

トラストラインは、レジャーの状態データでは[RippleStateオブジェクト](ripplestate.html)として表されます。1つのRippleStateオブジェクトは、一方向または両方向のトラストラインの可能性を表します。このオブジェクトにはトラストラインのそれぞれのサイドに対する制限やその他の設定が含まれていますが、両サイドは1つの正味残高を共有しています。

トラストラインの設定がデフォルトの状態である場合、トラストラインがないのと同等です。

[NoRippleフラグ](rippling.html)（デフォルトの設定はDefaultRippleフラグの設定に応じて異なる）を除き、トラストラインフラグのすべてのフラグは、デフォルトでオフになっています。

<!--{# common link defs #}-->
{% include '_snippets/rippled-api-links.md' %}
{% include '_snippets/tx-type-links.md' %}
{% include '_snippets/rippled_versions.md' %}
