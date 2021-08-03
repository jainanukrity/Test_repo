# ハブとプロジェクトをリストする(.NET Framework)

## DataManagementController.cs

**DataManagementController** という名前の .NET WebAPI コントローラを作成し([コントローラの作成方法](environment/setup/net_controller)を参照)、次の内容を追加します。

> エラーが少し表示され、直後に修正されます。

[DataManagementController.cs](_snippets/viewhubmodels/net/DataManagementController.1.cs '{3}')

上記は、UIツリーから要求を受け取ります。`id` パラメータは展開されているノードを示します。`#` はルート ノードを意味し、ハブをリストします。その後、リソースの `href` が含まれるため、1 つの `hub` を展開すると、エンドポイントはハブのプロジェクトを返す必要があります。上記のコードは、異なる `get` 関数を呼び出します。これを完了するには、次の内容もファイルにコピーします(同じ `DataManagementController` クラス内)。

[DataManagementController.cs](_snippets/viewhubmodels/net/DataManagementController.2.cs '{3}')

最後の `get` 関数は、各項目(ファイル)の **Versions** を返します。ここで、`.relationships.derivatives.data.id` プロパティには、**Viewer** の `URN` が含まれます。一部の項目に表示可能な項目(ZIPファイルやDOCxファイルなど)がない場合や、まだ翻訳されていない場合があるため、この属性が使用可能かどうかをテストすることが重要です。

プロパティによって公開される `資格情報`を再利用する方法に注意してください。

次へ:[ユーザ情報](oauth/user/readme)