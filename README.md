# ubuntu 18.04 建立 Matomo Server

Matomo（以前稱為Piwik）是由一組國際開發人員開發的免費開源Web分析應用程序，它在PHP / MySQL Web服務器上運行。

在 ubuntu 18.04 上利用 docker 快速建立 mariadb,matomo,nginx。

## 環境依賴
- ubuntu 18.04
- Cloudflare DNS

## 部署步驟
1. 設定系統環境變量 (.env)
    ```bash
    DB_ROOT_PW=<Root_Password>
    DB_NAME=<Database_Name>
    DB_USER=<User_Name>
    DB_PW=<Password>
    ```
2. 設定 nginx (etc/nginx/conf.d/matomo.conf)
    ```
    server {
        server_name <Domain_Name>;  # 替換 Domain
    }
    ```
3. 上傳 TLS/SSL 憑證至指定路徑
    ```
    etc/nginx/conf.d/ssl/cert.pem
    etc/nginx/conf.d/ssl/key.pem
    ```
 
4. 於目錄下執行 Docker
    ```
    docker-compose up -d
    ``` 
