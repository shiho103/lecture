# 第5回課題
- EC2 上にサンプルアプリケーションをデプロイ（組み込みサーバー）
![puma起動](https://user-images.githubusercontent.com/114926650/208250023-617ed6cd-2b52-4cdc-96c0-1d7839adffb7.png)

![puma起動後アプリケーション表示](https://user-images.githubusercontent.com/114926650/208250046-dfc1909d-24df-49d5-99c1-7fbe5337de73.png)

- EC2 上にサンプルアプリケーションをデプロイ（nginx・unicorn）
![nginx・unicorn起動](https://user-images.githubusercontent.com/114926650/208250151-3223de2e-8da5-42e8-8dd1-37bc645b411c.png)

![nginx・unicorn起動後アプリケーション表示](https://user-images.githubusercontent.com/114926650/208250183-9d32ab96-3a3b-4f07-bf91-0aa0b5a623c5.png)

- ELB(ALB)を追加
![ALB追加](https://user-images.githubusercontent.com/114926650/208250233-7ed82634-2173-4142-9371-20da64b630c2.png)

![ヘルスチェック](https://user-images.githubusercontent.com/114926650/208250245-5be9455e-bafe-487d-b16a-81360eca94c6.png)

-  S3 を追加（画像保存先として使用）
![S3追加（画像保存先）](https://user-images.githubusercontent.com/114926650/208250282-ae0659cb-0756-425b-848b-52a209c6e762.png)

![S3に保存された画像](https://user-images.githubusercontent.com/114926650/208250294-35791a94-2f50-482f-b005-37887da6209c.png)

- 構成図
![構成図](https://user-images.githubusercontent.com/114926650/208251187-439a7f71-db8c-4bc7-8ed3-61e29409c97a.png)


# 感じたことなど
今回はエラーが頻発して詰まることが多く、対処方法を調べるのにかなり時間がかかった。  これからも以下2点について気を付けていきたい。
- エラー内容を翻訳して意味を理解する
- エラーログを確認し何処がおかしいのか調べる

落ち着いて１つずつ調べれば解決するので、焦らずに根気強く対応していきたいと感じた
