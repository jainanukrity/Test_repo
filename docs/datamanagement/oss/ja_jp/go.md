# OSSにファイルをアップロード(移動)

このセクションでは、実際に3つの機能が必要です。

1. バケットを作成
2. バケットとオブジェクトをリスト(ファイル)
3. オブジェクト(ファイル)をアップロード

このファイルは2つのファイルで構成されます。

## oss.go

`/server/oss.go` ファイルを作成します。このファイルは最初の 2 つのフィーチャを処理し、次の内容を含める必要があります。

[oss.go](_snippets/viewmodels/go/oss.go ':include :type=code go')

フロントエンドで [jsTree](https://www.jstree.com/) をサポートする予定です。したがって、**GET oss/buckets** は、`id` クエリー文字列パラメータのハンドルを返し、`id=#` および `id=bucketKey` として渡された指定の bucketKey のオブジェクトを返す必要があります。


## uploader.go

次の内容で `/server/uploader.go` ファイルを作成します。

[uploader.go](_snippets/viewmodels/go/uploader.go ':include :type=code go')

!> クライアント(ブラウザ)から Autodesk Forge に直接ファイルをアップロードできますが、クライアントに **書き込み可能** アクセス トークン(**安全ではない**)を指定する必要があります。

次へ:[ファイルを変換する](modelderivative/translate/)