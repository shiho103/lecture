# 第11回課題
Serverspecでテストを行う
- 必要なモジュール、ツールをインストール  
  git、Node.js、yarn、Ruby、rails、rake、gem、ServerSpec、Nginx 等

- ServerSpecの初期設定を行う  
  $ serverspec-init  
  Select OS type:

  1) UN*X
  2) Windows

  Select number: 1

  Select a backend type:

  1) SSH
  2) Exec (local)

  Select number: 2  
  ※今回はCloudFormationで作ったEC2の中だけでテストするためlocalを選択

- サンプルテストファイルの中身を変更  
  テストファイルの場所：  
  ec2-user/spec/localhost/sample_spec.rb  

  変更内容：  
  listen_port = 80

- Nginx接続確認用にhtmlファイルを作成し保存  
  保存場所：/usr/share/nginx/html  
  保存したhtmlファイル：check.html

- nginx.confの中身を書き換えて、上記で作成したhtmlファイルが表示されるようにする  
  変更内容：  
  $ sudo vim /etc/nginx/nginx.conf  

  server {
        listen       80;  
        listen       [::]:80;  
        server_name _;  

  ※locationに表示させたいhtmlファイルを記載  
	location / {  
            root /usr/share/nginx/html;  
	    index check.html check.htm;
	        }

- Nginxを起動して、テスト実行  
  $ rake spec
  - テスト結果
  ![テスト結果](https://github.com/shiho103/lecture/assets/114926650/1b1a3a0c-8cf6-4a48-a037-d3f8cb810118)
  
  - 127.0.0.1（localhost）をブラウザ上で確認
  ![接続確認](https://github.com/shiho103/lecture/assets/114926650/08af68c9-7d46-412c-a5a5-ac98acd584bc)

【感想など】  
Serverspecの初期設定で、SSHを選択した後にlocalに変更するため再度初期設定をすると、テスト実行時に参照される「spec_helper.rb」が上書きされないことが分かった。設定を変えたい場合は、まず間違って作成したファイル等を削除し、新たに設定し直すよう気を付けたい。  

テストコードの（3）「ステータスコード200が返ってくるかの確認」が中々クリアできず、時間がかかってしまった。  
ポート番号8080だと、nginx.confのlisten portの設定を変えてもテストでは200が返ってこなかった。  
だが、curlコマンドで確認すると200が返ってきていた。  
$ curl -I http://127.0.0.1:8080  
HTTP/1.1 200 OK  

nginx.confとsample_spec.rb
のポート番号を80にしてテスト実行してみたところテストがクリアできたが、何故ポート番号8080だとクリアできなかったのかが不明。