# Server Infos

  * UserName
   
    xyz12345

## MariaDB

  ```
  cd mariadb
  docker build
  docker run --name marianode -e MYSQL_ROOT_PASSWORD=xxholic -d xx5/marianode
  ```

  ** --name は containerにつける名称 **
  ** MYSQL_ROOT_PASSWORD は mysql のroot password**

## Data

  container内に永続データを置いておけないのでdata directoryに入れておく。
  
  data
    + db
    + app
