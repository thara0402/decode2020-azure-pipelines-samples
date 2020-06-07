# Azure Web Apps 向けパイプライン
## パイプラインの構成
この Azure Pipelines YAML は、下記のようなディレクトリ構成となっています。

| YAML | ディレクトリ | 説明 |
----|----|---- 
| [build-pipelines.yml](./pipelines/build-pipelines.yml) | pipelines | ビルド用パイプライン（テンプレート） |
| [release-pipelines.yml](./pipelines/release-pipelines.yml) | pipelines | リリース用パイプライン（テンプレート） |
| [azure-pipelines.yml](./azure-pipelines.yml) | | Azure DevOps に登録するパイプライン（開発環境） |
| [azure-pipelines-production.yml](./azure-pipelines-production.yml) | | Azure DevOps に登録するパイプライン（本番環境） |

## パイプラインのパラメータ
この Azure Pipelines YAML を実行するパラメータとして、Azure DevOps プロジェクトで設定を追加する必要があります。

### Service Connections
| Type | Name | Value |
----|----|---- 
| Azure Resource Manager | azure | デプロイ先の Azure 接続情報 |

### Environment
| Name | Value |
----|---- 
| Commit-Stage | 開発環境のため、名称のみを設定 |
| Production-Stage | 本番環境のため、承認者のメールアドレスを設定 |

### Variable group
| Name | Key | Value |
----|----|---- 
| variable-group-commit | webAppsName | 開発環境の Azure Web Apps Name |
| variable-group-production | webAppsName | 本番環境の Azure Web Apps Name |
|  | resourceGroupName | 本番環境の Azure Web Apps が所属するリソースグループ |
