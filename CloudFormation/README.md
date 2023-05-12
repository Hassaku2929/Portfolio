# CloudFormationを利用した環境構築
## 概要
無料枠の範囲内でAWS環境構築を実施。
※マルチAZ構成は有料枠なので一旦はシングルAZ構成で作成

### VPC
|項目|内容|
| :--- | :--- |
|CIDRブロック|192.168.0.0/16|
|DNS機能|有効|
|DNS名割り当て|有効|

### Subnet
|VPCセグメント|サブネット名|AZ|備考|
| :--- | :--- | :--- | :--- |
|192.168.0.0/28|mySubnet01a|ap-northeast-1a|パブリック|
|192.168.0.128/28|mySubnet01c|ap-northeast-1c|パブリック|
|192.168.0.16/28|mySubnet02a|ap-northeast-1a|プライベート|
|192.168.0.144/28|mySubnet02c|ap-northeast-1c|プライベート|

### SecurityGroup
#### ec2用
|プロトコル|ポート番号|用途|
| :--- | :--- | :--- |
|tcp|22|ssh|
|tcp|80|http|
|tcp|8080|Webサーバ接続|
|tcp|443|https|
|tcp|3000|rails接続|

#### alb用
|プロトコル|ポート番号|用途|
| :--- | :--- | :--- |
|tcp|80|http接続|

#### rds用
|プロトコル|ポート番号|用途|
| :--- | :--- | :--- |
|tcp|3306|mysql接続|


## 構成図
![image_0](img/image_0.png) 

## 実施結果
1. CloudFormation  
![image_1](img/image_1.png)  

2. VPC  
![image_2](img/image_2.png)  

3. ルートテーブル
![image_7](img/image_7.png)  

4. セキュリティグループ
![image_6](img/image_6.png)  

5. RDS  
![image_3](img/image_3.png)  

6. EC2  
![image_4](img/image_4.png)  

7. ALB
![image_8](img/image_8.png)  

8. S3  
![image_5](img/image_5.png)  

### その他
作成したソースコード格納先  
[Network](../source/Network-properties.yml)  
[Security](../source/Security-properties.yml)  
[Application](../source/App-properties.yml)  
