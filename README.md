# redmineをECSクラスタで構築
※ローカルで使用していたredmineをECSで構築

①リポジトリ作成　　
cloudformationのスタック作成からテンプレートファイルのアップロードで以下のファイルをアップロードする。　　
ecr-repository.yml　　
　　
パラメータ入力でリポジトリ名を入力　　
ローカルで使用していたredmineのdockerイメージを作成したECRリポジトリにプッシュ　　
　　
②セキュリティグループを作成　　
cloudformationのスタック作成からテンプレートファイルのアップロードで以下のファイルをアップロードする。　　
ecs-ec2-securitygroup.yml　　


③ECSクラスターを作成　　
cloudformationのスタック作成からテンプレートファイルのアップロードで以下のファイルをアップロードする。　　
ecs-cluster-ec2.yml　　


④ECSサービス及びタスクを作成　　
cloudformationのスタック作成からテンプレートファイルのアップロードで以下のファイルをアップロードする。　　
ecs-service.yml　　
