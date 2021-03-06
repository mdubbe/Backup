---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-26"

---
{:new_window: target="_blank"}

# EVault の再登録

このタスクは、サーバーのオペレーティング・システムの再ロード後に最もよく利用されます。 これらのステップは、[1 つのサーバーのバックアップを使用して、別のサーバー上にデータをリストアする場合](restore-from-another-computer.html)に使用することもできます。

1. WebCC を開始してログインします。 手順については、[バックアップ・サービス入門](/docs/infrastructure/Backup/index.html)を参照してください。 <br/>WebCC には、{{site.data.keyword.BluVPN}} を介してのみアクセスできることを忘れないでください。

2. 左側にある**「すべてのエージェント」**をクリックします。

3. 右上で、**「編集」**をマウスオーバーします。

4. **「ボールト設定 (Vault Settings)」**を選択します。

5. **「再登録 (Reregister)」**をクリックします。
 
6. フォームに入力します。
  - ボールト名 (Vault name)
  - ボールト・アドレス (Vault address)
  - アカウント <br/>**注**: 「アカウント」は[{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}の「アカウント名」と同等です。 通常、「SLE[account ID]」のようになります。
  - ユーザー名
  - パスワード

7. **「コンピューターのロード (Load Computers)」**をクリックして、ロードするコンピューターを選択します。

8. **「変更の保存」**をクリックします。

9. Web サイトを最新表示して、以前のバックアップ・ジョブをリストアします。

10. 各バックアップ・ジョブを同期して、セーフセットの履歴をリストアします。

11. 暗号化パスワードを使用してバックアップ・ジョブが作成されている場合、データをリストしたり、バックアップを続行したりするには、暗号化パスワードを入力する必要があります。

12. **「閉じる」**をクリックします。
