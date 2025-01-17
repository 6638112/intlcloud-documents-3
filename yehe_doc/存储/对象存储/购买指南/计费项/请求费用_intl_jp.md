リクエスト回数には、**ユーザーリクエスト回数**、ユーザーの機能設定後に発生する**バックエンドリクエスト回数**が含まれます。リクエスト料金はCloud Object Storage（COS）に送信されたリクエストコマンド回数に基づいて計算されます。

- ユーザーリクエスト回数：ユーザーがAPI、SDKまたはコンソールなどを使用してデータのアップロード、ダウンロード、照会、削除などの操作を行う際、これらの操作は実際にはTencent Cloud COSにリクエストコマンドを送信することで実現されます。
- バックエンドリクエスト回数：ライフサイクル移行、アーカイブのリトリーブが期限切れとなった後の標準ストレージレプリカの削除リクエスト、地域間コピーの読み取りおよび書き込みリクエスト、インベントリレポート送信などのリクエスト回数を指します。

ストレージタイプおよびユースケースの違いによって、読み取り/書き込みリクエスト料金、INTELLIGENT_TIERINGオブジェクト監視料金、ディープアーカイブ取得リクエスト料金に区分されています。このうち、次の料金はユーザーの実際の利用状況に応じて課金されます。
- INTELLIGENT_TIERINGオブジェクト監視料金：バケットのINTELLIGENT_TIERINGストレージ設定をアクティブ化している状態で、INTELLIGENT_TIERINGストレージタイプのデータをそのバケットにアップロードした場合、この料金が発生します。この料金は、64KB以上のオブジェクトの数によって計算します。
- ディープアーカイブ取得リクエスト料金：ユーザーがディープアーカイブストレージタイプのデータを復元（または解凍）した場合、取得リクエスト回数が発生し、これによりディープアーカイブ取得リクエスト料金が課金されます。


>?ストレージタイプに関するその他の説明は、[ストレージタイプの概要](https://intl.cloud.tencent.com/document/product/436/30925)をご参照ください。
> 

## 読み取り/書き込みリクエスト料金

<table>
<thead>
<tr><th style="width: 65%;">課金項目の説明</th><th style="width: 16%;">適用されるストレージタイプ</th><th style="width: 19%;">適用される課金方式</th></tr>
</thead>
<tbody>
<tr>
<td>読み取り/書き込みリクエスト回数とは、リクエストコマンドの送信回数のことです。その料金は毎日の総リクエスト回数に基づいて計算します。<ul  style="margin: 0;"><li>リクエスト数はリクエストの成否にかかわらず課金されます。</li><li>リクエスト料金は1万回を最小計数単位とします。</li><ul style="margin: 0;"><li>当日のリクエスト回数が1万回未満の場合は、実際のリクエスト回数に応じて計算します。</li><li>当日のリクエスト回数の料金が最低引き落とし額に満たなかった場合、リクエスト料金の請求金額は0元となります。詳細については、<a href="https://intl.cloud.tencent.com/document/product/436/10373">よくあるご質問</a>のドキュメントをご確認ください。</li></ul></li><li>アーカイブストレージ、ディープアーカイブストレージタイプのデータは、直接読み取りまたはダウンロードができません。<ul style="margin: 0;"><li>未復元（または未解凍）のアーカイブストレージまたはディープアーカイブストレージデータに直接アクセスしようとすると、リクエストエラーが発生します。このリクエストはアーカイブストレージ/ディープアーカイブストレージの読み取り/書き込みリクエストとして課金されます。詳細については、<a href="https://buy.intl.cloud.tencent.com/price/cos?lang=en&pg=">製品価格</a>をご確認ください。</li><li>アーカイブストレージタイプのデータを復元（または解凍）すると、標準ストレージタイプのレプリカが作成され、このレプリカは標準ストレージとして課金されます。このレプリカにアクセスすると、読み取り/書き込みリクエストが発生し、標準ストレージ読み取り/書き込みリクエストとして課金されます。</li><li>ディープアーカイブストレージタイプのデータを復元（または解凍）すると、標準ストレージタイプのレプリカが作成され、このレプリカは標準ストレージとして課金されます。このレプリカにアクセスすると、読み取り/書き込みリクエストが発生し、ディープアーカイブストレージ読み取り/書き込みリクエストとして課金されます。</li></ul></td>
<td>すべてのストレージタイプ</td>
<td>従量課金</td>
</tr>
</tbody></table>


## INTELLIGENT_TIERINGオブジェクト監視料金

<table>
<thead>
<tr><th style="width: 65%;">課金項目の説明</th><th style="width: 16%;">適用されるストレージタイプ</th><th style="width: 19%;">適用される課金方式</th></tr>
</thead>
<tbody>
<tr>
<td>INTELLIGENT_TIERINGストレージタイプデータのオブジェクト監視料金。データのアクセス状況の監視に用いられます。</td>
<td>INTELLIGENT_TIERINGストレージ</td>
<td>従量課金</td>
</tr>
</tbody></table>

## ディープアーカイブ取得リクエスト料金

<table>
<thead>
<tr><th style="width: 65%;">課金項目の説明</th><th style="width: 16%;">適用されるストレージタイプ</th><th style="width: 19%;">適用される課金方式</th></tr>
</thead>
<tbody><tr>
<td>ディープアーカイブストレージタイプのデータを復元（解凍）した場合、COSは送信された復元リクエストの回数に基づいてディープアーカイブ取得リクエスト料金を課金します。<br/>ユーザーが選択可能な2種類のリカバリモード（標準取得モードと一括取得モード）によって、料金が次のように区分されます。<ul  style="margin: 0;"><li>ディープアーカイブ標準取得リクエスト料金</li><li>ディープアーカイブ一括取得リクエスト料金</li></ul></td>
<td>ディープアーカイブストレージ</td>
<td>従量課金</td>
</tr>
</tbody></table>


## リクエスト料金の課金方式と計算方法

|  課金方式   |   適用される課金項目   |   計算方法   |
|-----|--------|------|
|  従量課金   |    読み取り/書き込みリクエスト料金 </br> INTELLIGENT_TIERINGオブジェクト監視料金  </br> ディープアーカイブストレージ取得リクエスト料金 </br>      |  <ul  style="margin: 0;"><li>日次決済  </li><li>リクエスト料金 = リクエスト回数（または監視数）1万回あたりの単 x 1日の累計リクエスト回数（または監視数） / 10000 </li></ul>       |


## リクエスト回数価格

リクエストの単価については、[製品価格](https://buy.intl.cloud.tencent.com/price/cos?lang=en&pg=)をご確認ください。

## 課金の例

>?
> - 次の例に記載した料金価格は参考用です。実際の価格については、COS[製品価格](https://buy.intl.cloud.tencent.com/price/cos?lang=en&pg=)をご参照ください。
> - リクエスト数はリクエストの成否にかかわらず計算されます。


### 事例：標準ストレージ容量料金 + 標準ストレージリクエスト料金

ユーザーのAさんが2020年11月1日に広州リージョンのCOSバケットに標準ストレージタイプのデータ10GBをアップロードし、その日のうちにGET Bucket APIを呼び出して合計10万回繰り返しオブジェクトリストを照会したと仮定します。それ以外の時間には他の操作を行わず、前日に発生した料金を1日単位で決済する場合、次のとおりとなります。

- 標準ストレージ容量料金：2020年11月2日より毎日決済されます。
- 標準ストレージリクエスト料金：2020年11月2日に決済されます。

料金の分析は、次のとおりです。

-  標準ストレージ容量料金 = 0.024米ドル/GB/月/30 x 10GB x 30 = 0.24米ドル
-  標準ストレージリクエスト料金 = 0.002米ドル/万回 x 10万回 = 0.02米ドル


上記の分析を総合すると、11月中のAさんの料金総額は0.24 + 0.02 = 0.26米ドルとなります。
