# MK語法

- [MK語法](#mk語法)
  - [Markdown All in One 可用命令](#markdown-all-in-one-可用命令)
  - [標題](#標題)
  - [文字格式](#文字格式)
  - [清單](#清單)
  - [連結和圖片](#連結和圖片)
  - [任務](#任務)
  - [程式碼區塊](#程式碼區塊)
  - [引言](#引言)
  - [表格](#表格)
  - [分隔線](#分隔線)
  - [換行](#換行)
  - [好用的字元](#好用的字元)
- [VSCODE](#vscode)
  - [THEME](#theme)
  - [Font](#font)
  - [ICON](#icon)
  - [tokenColorCustomizations](#tokencolorcustomizations)
  - [快捷鍵](#快捷鍵)

## Markdown All in One 可用命令

| Markdown All in One | 命令字元                        | 命令                  |
| :-----------------: | ------------------------------- | --------------------- |
| Markdown All in One | :Create Table of Contents       | 創建目錄              |
| Markdown All in One | :Update Table of Contents       | 更新目錄              |
| Markdown All in One | :Add/Update section numbers     | 添加/更新部分編號     |
| Markdown All in One | :Remove section numbers         | 刪除部分編號          |
| Markdown All in One | :Toggle code span               | 切換代碼範圍          |
| Markdown All in One | :Toggle code block              | 切換代碼塊            |
| Markdown All in One | :Print current document to HTML | 將當前文檔列印為 HTML |
| Markdown All in One | :Print documents to HTML        | 將文檔列印為 HTML     |
| Markdown All in One | :Toggle math environment        | 切換數學環境          |
| Markdown All in One | :Toggle list                    | 切換清單              |

返回[MK語法](#mk語法)

## 標題

- \# 一級標題
- \## 二級標題
- \### 三級標題
- \#### 四級標題
- \##### 五級標題
- \###### 六級標題

返回[MK語法](#mk語法)

## 文字格式

- \*\*粗體文字\*\*
- \*斜體文字\*
- \~~刪除線~~
- \`行內程式碼`

返回[MK語法](#mk語法)

## 清單

- \- 無序清單項目 1
- \- 無序清單項目 2
- \- 子項目
- 1\. 有序清單項目 1
- 2\. 有序清單項目 2
- 1\. 子項目

返回[MK語法](#mk語法)

## 連結和圖片

- \[連結文字\](https://example.com)
- \!\[圖片替代文字\](image.jpg)

返回[MK語法](#mk語法)

## 任務

- \- \[x\] 已完成任務
- \- \[ \] 未完成任務

返回[MK語法](#mk語法)

## 程式碼區塊

- \`\`\`語言名稱
- 程式碼內容
- \`\`\`

返回[MK語法](#mk語法)

## 引言

- \> 引言
- \> 可以多行

返回[MK語法](#mk語法)

## 表格

- \| 標題1 \| 標題2 \|
- \|-------|-------|
- \| 內容1 \| 內容2 \|

返回[MK語法](#mk語法)

## 分隔線

- \---

返回[MK語法](#mk語法)

## 換行

- \<br>

## 好用的字元

```
├──

└──
```

返回[MK語法](#mk語法)

---

# VSCODE

## THEME

推薦主題：在延伸模組中搜尋

1. Dracular Theme Official

2. Panda Theme

## Font

推薦字型：[SauceCodePro Nerd Font](https://www.nerdfonts.com/font-downloads)

解壓縮後，開啟資料夾，選取 `LICENSE` `README` 以外的檔案，拖移到 `設定>個人化>字型` 安裝字型。

在VSCODE中安裝字型：

設定>搜尋 `Editor: Font Family` 輸入 `SauceCodePro Nerd Font, Consolas, 'Courier New', monospace`

## ICON

推薦掛件：[Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)

更改特定檔案或資料夾：

開啟設定> `setting.json` >

更改檔案：

```json
"material-icon-theme.files.associations": {
    "*.ts": "typescript",
    "**.json": "json",
    "fileName.ts": "angular"
}
```

更改資料夾：

```json
"material-icon-theme.folders.associations": {
    "folder1": "example",
    "folder2": "Rules",
    "folder3": "Keys"}
```

## tokenColorCustomizations

個人化語法色彩及字型樣式

```json
"editor.tokenColorCustomizations": {
        "textMateRules": [
            {
                "scope": [
                    "string",
                    "string.quoted.double",
                    "string.quoted.single"
                ],
                "settings": {"foreground": "#ff9f50"}
            }
```

編輯器反白色彩

```json
"workbench.colorCustomizations": {
        "editor.selectionBackground": "#ff99008e"
```

## 快捷鍵

- ctrl + shift + p 開啟命令
- ctrl + K + ctrl + S 開啟快捷鍵設定
