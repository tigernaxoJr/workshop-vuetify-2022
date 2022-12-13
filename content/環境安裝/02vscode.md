---
title: "02.VSCode"
date: 2022-12-13T14:43:54+08:00
---
NodeJS 
VSCode 

## 
- [git]()
- [npm]()

## VSCode
1. `Ctrl-Shift-P` 輸入 json 搜尋，選擇 `Preference: Open User Settings (JSON)`
2. 加入 lint 設置
	```js
	"files.autoSave": "onWindowChange", // 切換視窗自動存檔
	"editor.formatOnSave": true, // 存檔時自動 format
	"vetur.validation.template": false, // 關閉 vetur 驗證
	"editor.defaultFormatter": "esbenp.prettier-vscode" // 預設 format 使用 prettier
	```
3. 設置 vscode 排除追蹤檔案
	```js
	/* 
		node_module、.git 等等資料夾底下有非常多不需要追蹤的檔案，
		如果不排除於追蹤清單外，vscode會因為追蹤(watch)的檔案數量檔案達到飽和，
		無法對正在編輯的檔案進行追蹤、執行hot reload。
		*/
	"files.watcherExclude": {
		"**/.git/objects/**": true,
		"**/.git/subtree-cache/**": true,
		"**/node_modules/*/**": true
	},
	```