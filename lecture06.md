# 第6回課題
- CloudTrailイベントとその内容3件
  - StopInstances：EC2インスタンスの停止  
   1."type": "IAMUser"  
   2."eventTime": "2023-01-07T16:07:53Z"  
   3."eventSource": "ec2.amazonaws.com"

  ![イベント履歴](https://user-images.githubusercontent.com/114926650/211324476-b44afe9d-9865-455e-aa48-5881b4eb6607.png)

- CloudWatch アラームとアクションを設定した状態で、Rails アプリケーションが使える、使えない状態にして、動作を確認
  ![アラーム状態](https://user-images.githubusercontent.com/114926650/211284447-5b83a543-5179-4cdd-87f8-974cbb515468.png)

  ![アラーム状態メール](https://user-images.githubusercontent.com/114926650/211284560-6c5cfa97-b50c-40a2-9dbc-d670277517a7.png)

  ![ヘルスチェックOK](https://user-images.githubusercontent.com/114926650/211285028-47d49e42-2ca6-43f7-9300-b92e01d1dbf2.png)

  ![OK状態](https://user-images.githubusercontent.com/114926650/211285146-568c7d5c-ef6c-47b7-84a1-93cb240d11a3.png)

  ![OK状態メール](https://user-images.githubusercontent.com/114926650/211285219-a6ec1cd8-236f-48ec-a05c-47625d8919c2.png)

- 今までに作成したリソースの内容を見積
https://calculator.aws/#/estimate?id=1d0f35b6edab9c479d96b73727288f18e29fa969

- 先月のEC2 料金
  ![12月EC2コスト](https://user-images.githubusercontent.com/114926650/211285545-27f6a874-e657-4818-9e74-602ec2c3bd0d.png)

- 現在の利用料を確認（無料利用枠で収まっているか）
![現在のコスト](https://user-images.githubusercontent.com/114926650/211285748-c9c038cf-e675-4f38-b399-3d6bf0533a49.png)
  
# 感じた事など
11月にRDSの料金が発生した際、Budgetsからのメールで気づきました。RDSを止める必要があることを知らなかったので、通知が来たことで何に料金がかかっているのかを確認して対応できました。料金に限らず、アラームを設定しておくことで早く問題に気づいて対処できるので今後活用していきたいと感じました。
