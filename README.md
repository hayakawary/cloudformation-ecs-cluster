# redmineをECSクラスタで構築
※ローカルで使用していたredmineをECSで構築

①リポジトリ作成<br>
cloudformationのスタック作成からテンプレートファイルのアップロードで以下のファイルをアップロードする。<br>
ecr-repository.yml<br>
<br>
パラメータ入力でリポジトリ名を入力<br>
ローカルで使用していたredmineのdockerイメージをECRリポジトリにプッシュする。<br>
※ECRリポジトリへのプッシュ方法はリポジトリのプッシュコマンドを表示を参照<br>
<br>
②セキュリティグループを作成　<br>
cloudformationのスタック作成からテンプレートファイルのアップロードで以下のファイルをアップロードする。<br>
ecs-ec2-securitygroup.yml<br>
<br>
パラメータで以下を入力<br>
ECSクラスター名<br>
VPCの選択<br>
<br>
③ECSクラスターを作成　<br>
cloudformationのスタック作成からテンプレートファイルのアップロードで以下のファイルをアップロードする。<br>
ecs-cluster-ec2.yml<br>
<br>
パラメータで以下を入力<br>
ECSクラスター名<br>
EC2インスタンスに設定するセキュリティグループを選択<br>
AMI<br>
インスタンスタイプ<br>
インスタンスキーペア<br>
<br>
④ECSサービス及びタスクを作成<br>
cloudformationのスタック作成からテンプレートファイルのアップロードで以下のファイルをアップロードする。<br>
ecs-service.yml<br>
<br>
パラメータで以下を入力<br>
ECSクラスター名<br>
コンテナ名<br>
コンテナ数<br>
コンテナポート番号:3000<br>
※redmineのデフォルトポート番号は3000<br>
ホストポート番号:80<br>
コンテナイメージ<br>
※リポジトリにプッシュしたイメージURIをコピーして貼り付け<br>
サービス名<br>
<br>
⑤使用<br>
ECSコンテナの外部リンクをクリック<br>
