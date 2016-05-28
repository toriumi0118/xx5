# Server Infos

  * UserName
 
    xyz12345

## MariaDB

  **mariadb実行コマンド**

  ```bash
  ### 実行コマンド
  cd mariadb
  docker build .
  docker run --name marianode -v maria_data:/var/lib/mysql -d xx5/marianode
  ```

  > **optionについて**
  >
  > --name : containerにつける名称  
  > -v : volumeをmountできる。    
  > host側のmaria_data(/var/lib/docker/volumes/にいる)をcontainer側の/var/lib/mysqlにマウントする
  >
  > 接続しているvolumeを確認するには  
  > docker volume inspect maria_data

  **marianodeへアクセス**

  ```bash
  docker exec -it marianode bash
  mysql -u xyz12345 -pbobox1099
  use xx5;
  show tables;
  ```

## Application

  WebApi

    : scala + finagle

  Backend

    : python3

  Frontend

    : js
  
  OtherScripts

    : Haskell
  
  app以下に**Dockerfile**とソースコードをいれておく。  
  Dockerfileで作られるコンテナ内には**xx5レポジトリト**の内容がコピーされ   
  appディレクトリ内の内容が起動するようにする予定   

  ```bash
  docker run -port 80:8080 xx5/appnode # これで80 -> 8080のマッピングが行われる
  ```

  > portマッピングは今後の運用で変えていくことになりそう。

## WebCrawler

  Ruby


## Data

  container内に永続データを置いておけないのでdata directoryに入れておく。

  ```
  data  
    + db  
    |  + Dockerfile # mariadbの設定   
    + app   
       + Dockerfile # finagleの起動設定    
       |    
       + application files    
       ....   
  ```

  > 将来的にはCasanndra or HBASE or 自作の何かでやりたい

