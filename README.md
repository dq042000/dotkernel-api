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

2. 於專案根目錄執行以下指令安裝相依套件：

   ```bash
   composer install
   ```

3. 設定環境變數檔案 .env

4. 初始化資料庫：

   ```bash
   php bin/console doctrine:migrations:migrate
   ```

5. 啟動伺服器：

   ```bash
   php -S localhost:8000 -t public
   ```

## 目錄結構

- `/src`：主要程式碼
- `/config`：設定檔
- `/public`：公開入口
- `/tests`：單元測試

## 相關資訊

- 官方網站：[Dotkernel](https://dotkernel.com/)
- 文件：[Dotkernel 文件](https://docs.dotkernel.com/)
