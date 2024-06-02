## Step 1:
Install Container Manager package. If you already have Container Management packaged installed, skip this step.

## Step 2:
Go to Control Panel / Login Portal / Advanced Tab / click Reverse Proxy.

## Step 3:
Now click the “Create” button.

## Step 4:
Fill out the form with the following information:

Reverse Proxy Name: microbin
Source:
  Protocol: HTTPS
  Hostname: microbin.yourDomain.com
  Port: 443
Enable HSTS: CHECKED
Destination:
  Protocol: HTTP
  Hostname: localhost
  Port: 5101

## Step 5:
Select Custom Header tab / click Create / click WebSocket / click Save

## Step 6:
Go to File Station and create new folder inside your docker folder, and name it microbin.

## Step 7:
Go to Container Manager / Project / click Create.

## Step 8: 
Fill out the form with the following information:

Project name: microbin
Path: /docker/microbin
Source: select Create docker-compose.yml
```
version: "3.9"
services:
  microbin:
    container_name: microbin
    image: danielszabo99/microbin:latest
    restart: on-failure:5
    ports:
     - 5101:8080
    volumes:
     - /volume1/docker/microbin:/app/microbin_data
    environment:
      MICROBIN_ADMIN_USERNAME: microbinadmin
      MICROBIN_ADMIN_PASSWORD: m1cr0b1n
      MICROBIN_EDITABLE: true
      MICROBIN_HIDE_FOOTER: false
      MICROBIN_HIDE_HEADER: false
      MICROBIN_HIDE_LOGO: false
      MICROBIN_NO_LISTING: false
      MICROBIN_HIGHLIGHTSYNTAX: true
      MICROBIN_BIND: 0.0.0.0
      MICROBIN_PRIVATE: true
      MICROBIN_PURE_HTML: false
      MICROBIN_DATA_DIR: "microbin_data"
      MICROBIN_JSON_DB: false
      MICROBIN_PUBLIC_PATH: https://microbin.davisdre.network
      MICROBIN_READONLY: false
      MICROBIN_SHOW_READ_STATS: true
      MICROBIN_THREADS: 1
      MICROBIN_GC_DAYS: 90
      MICROBIN_ENABLE_BURN_AFTER: true
      MICROBIN_DEFAULT_BURN_AFTER: 0
      MICROBIN_WIDE: false
      MICROBIN_QR: true
      MICROBIN_ETERNAL_PASTA: false
      MICROBIN_ENABLE_READONLY: true
      MICROBIN_DEFAULT_EXPIRY: 24hour
      MICROBIN_NO_FILE_UPLOAD: false
      MICROBIN_HASH_IDS: false
      MICROBIN_ENCRYPTION_CLIENT_SIDE: true
      MICROBIN_ENCRYPTION_SERVER_SIDE: true
      MICROBIN_MAX_FILE_SIZE_ENCRYPTED_MB: 256
      MICROBIN_MAX_FILE_SIZE_UNENCRYPTED_MB: 2048
```

## Step 9:
click Next / click Next / click Done / click Close.

## Step 10:
Open your web browser and go to https://microbin.yourDomain.com. Your paste link.
