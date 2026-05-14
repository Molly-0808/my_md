# Git 技術筆記

- [Git 技術筆記](#git-技術筆記)
  - [git config](#git-config)
  - [git init](#git-init)
    - [如何建立 .git 資料夾](#如何建立-git-資料夾)
    - [如何取消 git init](#如何取消-git-init)
  - [git add](#git-add)
    - [如何 git add](#如何-git-add)
    - [如何取消 git add](#如何取消-git-add)
  - [git commit](#git-commit)
  - [查看紀錄相關指令](#查看紀錄相關指令)
    - [git status](#git-status)
    - [git blame](#git-blame)
    - [git log](#git-log)
    - [用 git config 設定指令別名(縮寫)](#用-git-config-設定指令別名縮寫)
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

## git config

- 1\. 開啟 VS Code 內建終端機：按 Ctrl ` (Tab 上面那個鍵)

- 2\. 檢查git設定值：$`git config --list `

- 3\. 設定user.name：$`git config --global user.name "我的名字"`

- 4\. 設定user.email：$`git config --global user.email "我的信箱"`

> 因為有傳遞 --global參數，只需操作一次

> $代表要在 PowerShell 裡面執行，不須寫入指令

返回[Git 技術筆記](#git-技術筆記)

## git init

### 如何建立 .git 資料夾

- 1\. 在電腦建立新資料夾

- 2\. 用Windows PowerShell (電腦終端機) cd 到該資料夾

- 3\. 輸入 code . (.前面要有空格)開啟有該資料夾的 VS Code

- 4\. 或不採用前兩步驟，直接開啟 VS Code 新視窗，拖拉新資料夾進入 VS Code

- 5\. 開啟 VS Code 內建終端機：按 Ctrl ` (Tab 上面那個鍵)

- 6\. 生成 .git 資料夾：$`git init`

- 7\. 確認版本號：$`git --version `

### 如何取消 git init

- 使用 VS Code 內建終端機
  - 輸入$`Remove-Item -Recurse -Force .git`

- 手動刪除
  - 開啟 VS Code 檔案總管，直接刪除 .git 資料夾

返回[Git 技術筆記](#git-技術筆記)

## git add

### 如何 git add

- 加入某個檔案：$`git add aaa.md`

- 加入某個資料夾(內的所有檔案)：$`git add 資料夾名稱/`

- 加入某個資料夾內的某個檔案：$`git add 資料夾名稱/aaa.md`

- 加入目前所有資料夾內全部新增或修改過的檔案：$`git add .`(.前面要有空格)

- 一次性加入特定多個檔案：$`git add aaa.md bbb.md ccc.md`(檔案中間空格即可)

> git add 只會加入檔案，若命令輸入資料夾，代表加入該資料夾內的所有檔案

### 如何取消 git add

- 移除某個檔案：$`git restore --staged aaa.md`

- 清空暫存區：$`git restore --staged .`

返回[Git 技術筆記](#git-技術筆記)

## git commit

- 儲存檔案：$`git commit -m "第一次commit"`

> git add檔案之後 commit的就是剛才add的那些檔案

- 修改最新commit的備註訊息：$`git commit --amend -m "有錯字可以這樣改"`(SHA值會變)

> 如果已經commit過，需要修改檔案，只要重新add再commit就好

- 跳過暫存區直接commit：$`git commit -a -m "跳過暫存區直接儲存囉"`

返回[Git 技術筆記](#git-技術筆記)

## 查看紀錄相關指令

### git status

- 用於察看以下檔案情況：
  - 查看「未追蹤的檔案」：新建立的檔案還沒add，顯示紅色

  - 查看「已修改但尚未暫存」：已經追蹤過，但因為有修改過，還沒重新add，顯示紅色

  - 查看「準備提交的變更」：已經add，在暫存區排隊，顯示綠色

### git blame

- 查看每一行最後修改者、提交時間：$`git blame`

### git log

- 查看commit歷史紀錄：$`git log`

- 單行顯示commit歷史紀錄：$`git log --oneline`

- 限制顯示幾個commit歷史紀錄：$`git log -n 3`

- 查看包含branch的走向：$`git log --graph`

- 查看完整修改內容：$`git log -p`

- 查看特定人的commit：$`git log --oneline --author="想查的名字"`

> =和後面的”人名”之間不能有空格，且人名呈現灰色是正常的

- 查看特定字的commit：$`git log --oneline --grep="想查的字"`

- 查看特時間區間的commit：$`git log --since="2026-04-14 09:00" --until="2026-04-14 17:30"`

### 用 git config 設定指令別名(縮寫)

- ：$`git config --global alias.別名al "原指令log --oneline --author"`
  - 縮寫變：$`git al`

返回[Git 技術筆記](#git-技術筆記)

# MK語法

- [Git 技術筆記](#git-技術筆記)
  - [git config](#git-config)
  - [git init](#git-init)
    - [如何建立 .git 資料夾](#如何建立-git-資料夾)
    - [如何取消 git init](#如何取消-git-init)
  - [git add](#git-add)
    - [如何 git add](#如何-git-add)
    - [如何取消 git add](#如何取消-git-add)
  - [git commit](#git-commit)
  - [查看紀錄相關指令](#查看紀錄相關指令)
    - [git status](#git-status)
    - [git blame](#git-blame)
    - [git log](#git-log)
    - [用 git config 設定指令別名(縮寫)](#用-git-config-設定指令別名縮寫)
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
