# dotkernel-api 安裝

學習 Dotkernel Api 專案

## 專案簡介

本專案為基於 Dotkernel 的 API 伺服器，適合用於快速建構現代化 Web 服務。專案結合多種常用函式庫，具備良好延展性與相容性，方便開發者進行二次開發與整合。

## 主要功能

- RESTful API 設計
- 內建用戶驗證與授權
- 支援多種資料庫
- 易於擴充的模組化架構
- 交易式資料處理
- 完善的錯誤處理與日誌紀錄

## 安裝步驟

1. 下載或複製本專案原始碼

2. 執行下列指令啟動 docker 佇列環境：

   ```bash
   sh setup.sh
   ```

3. 於專案根目錄執行以下指令安裝相依套件：

   ```bash
   docker exec -ti dotkernel-api_php_1 composer install
   ```

4. 設定環境變數檔案 .env

5. 初始化資料庫：

   ```bash
   docker exec -ti dotkernel-api_php_1 vendor/bin/doctrine-migrations migrate
   ```

   此指令會執行資料庫遷移，建立或更新資料表結構，確保資料庫與程式碼結構相容。

6. 查看可用的範例資料 (fixtures) 清單：

   ```bash
   docker exec -ti dotkernel-api_php_1 php bin/doctrine fixtures:list
   ```

   此指令會顯示目前可用於載入的所有範例資料 (fixtures) 資訊，方便你確認有哪些資料可以寫入資料庫。

7. 載入預設資料 (fixtures)：

   ```bash
   docker exec -ti dotkernel-api_php_1 php bin/doctrine fixtures:execute
   ```

   此指令會將預先定義的範例資料 (fixtures) 寫入資料庫，方便開發或測試時使用。

8. 打開瀏覽器，於網址列輸入：

   <http://localhost:9810>

   畫面若顯示：

   ```json
   {"message": "Dotkernel API version 6"}
   ```

   即完成。

## 目錄結構

- `/src`：主要程式碼
- `/config`：設定檔
- `/public`：公開入口
- `/tests`：單元測試

## 相關資訊

- 官方網站：[Dotkernel](https://dotkernel.com/)
- 文件：[Dotkernel 文件](https://docs.dotkernel.com/)
