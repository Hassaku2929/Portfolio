# AWSでRailsアプリケーションを構築
## 概要
無料枠の範囲内でAWS環境構築を実施。  
AWS環境構築完了後、RailsアプリケーションをEC2に構築しアプリケーションが動くことを確認。  
※マルチAZ構成は有料枠なので一旦はシングルAZ構成で作成  


### VPC環境構築
![image_9](img/image_9.png)  


### EC2環境構築
![image_10](img/image_10.png)  


### RDS環境構築
![image_11](img/image_11.png)  

1. RDS接続確認
![image_8](img/image_8.png)  

### Railsアプリケーションを構築  

1. rails server -b 0.0.0.0　コマンド  
　　→[EC2アプリケーションデプロイ](Construction/EC2.md)  
![image_1](img/image_1.png)  

2. Web/APサーバの構築  
　　→[Web/APサーバの構築](Construction/Web・AP.md)  
2.1 Unicorn起動  
![image_2](img/image_2.png)  

2.2 Nginx起動  
![image_3](img/image_3.png)  

2.3 動作確認  
![image_4](img/image_4.png)  

3. ALB構築  
DNS nameでWebサイトにアクセス  
![image_5](img/image_5.png)  

4. S3構築  
　　→[S3構築](Construction/S3.md)  
![image_6](img/image_6.png)  
![image_7](img/image_7.png)  

5. 構成図  
![RaiseTech構成図](img/RaiseTech構成図.png)  
