本プロジェクトはTerraformを使用してインフラのコード化した上、GitHub ActionsによってCI/CD 環境構築を行う。
・Terraformを使用してAWS運用監視の環境をコード化する
　・・VPC（Subnet、RouteTable,InternetGatewayなどを含む）
　・・EC2（EC2のセキュリティグループなどを含む）
　・・RDS（RDSのセキュリティグループ、インバウンドルールなどを含む）
　・・ALB（ターゲットグループ、ALBのリスナーなどを含む）
　・・CloudWatch（メトリクス、アラーム）
　・・WAF（WebACL、WEB ACLをALBに関連付け）
・GitHub ActionsによるCI/CD 環境を構築する
　・・プルリクエストをトリガーにCIが起動して、Checkout、fmt、
　　　Configure AWS Credential、init、validateとplanを実行　　　　
　・・マージをトリガーにCDが起動して、Checkout、fmt、
　　　Configure AWS Credential、init、validateとapplyを実行>