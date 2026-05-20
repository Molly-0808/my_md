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

- commit 了，但是 commit 的檔案內容不是我要的：$`git reset`

- 跳過暫存區直接commit：$`git commit -a -m "跳過暫存區直接儲存囉"`

> 如果已經commit過，需要修改檔案，只要重新add再commit就好

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
