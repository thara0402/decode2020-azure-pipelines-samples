# .NET Core 向け Azure Pipelines YAML
Azure DevOps において、.NET Core で構築するアプリケーション向けのパイプラインを構築できます。

- [Azure Web Apps](./web-apps/README.md)
- [Azure Functions](./function-apps/README.md)

開発環境と本番環境向けにブランチとパイプラインを分けることを想定しています。

| パイプライン | ブランチ | 承認 | Deployment Slot | 説明 |
----|----|----|----|---- 
| 開発環境向け | master | なし | なし | ブランチの更新をトリガーとして、ビルドとリリースを自動実行します。 |
| 本番環境向け | production | あり | あり | ブランチの更新をトリガーとして、ビルドを自動実行します。リリースは承認制となっており、staging slot にデプロイ後にスワップします。|

提供するパイプラインの解説については、[こちら](http://gooner.hateblo.jp/entry/2020/03/06/085256)のブログを参照してください。

## License
Copyright (c) 2020 Toshiyuki Hara  
Released under the MIT License - see the LICENSE file for details
