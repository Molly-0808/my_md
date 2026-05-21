# Git 技術筆記

- [Git 技術筆記](#git-技術筆記)
  - [git config](#git-config)
    - [基本設定](#基本設定)
    - [用 git config 設定指令的縮寫](#用-git-config-設定指令的縮寫)
    - [用 git config 設定今後的 master 都自動變成 main](#用-git-config-設定今後的-master-都自動變成-main)
  - [git init](#git-init)
    - [如何建立 .git 資料夾](#如何建立-git-資料夾)
    - [如何取消 git init](#如何取消-git-init)
  - [git add 【從工作目錄加到暫存區】](#git-add-從工作目錄加到暫存區)
    - [如何 git add](#如何-git-add)
    - [如何取消 git add](#如何取消-git-add)
  - [git commit 【從暫存區加到本地儲存庫】](#git-commit-從暫存區加到本地儲存庫)
    - [如何 commit](#如何-commit)
    - [如何取消 commit](#如何取消-commit)
  - [查看紀錄相關指令](#查看紀錄相關指令)
    - [git status](#git-status)
    - [git blame](#git-blame)
    - [git log](#git-log)
    - [git branch](#git-branch)
  - [git branch](#git-branch-1)
    - [git switch](#git-switch)
    - [git checkout](#git-checkout)
  - [git push / git pull](#git-push--git-pull)
    - [在本地加入遠端 GitHub 專案](#在本地加入遠端-github-專案)
    - [正式 git push](#正式-git-push)
  - [.gitignore](#gitignore)
  - [git reset](#git-reset)
  - [git reflog](#git-reflog)
  - [git merge](#git-merge)
    - [vim 編輯器](#vim-編輯器)
  - [git rebase](#git-rebase)

## git config

### 基本設定

- 1\. 開啟 VS Code 內建終端機：按 Ctrl ` (Tab 上面那個鍵)

- 2\. 檢查git設定值：$`git config --list `

- 3\. 設定user.name：$`git config --global user.name "我的名字"`

- 4\. 設定user.email：$`git config --global user.email "我的信箱"`

> 因為有傳遞 --global參數，只需操作一次

> $代表要在 PowerShell 裡面執行，不必把錢字號也寫上去

### 用 git config 設定指令的縮寫

- $`git config --global alias.別名nnn "原指令log --oneline --author"`
  - 縮寫變：$`git nnn`

### 用 git config 設定今後的 master 都自動變成 main

- $`git config --global init.defaultBranch main`

返回[Git 技術筆記](#git-技術筆記)

## git init

### 如何建立 .git 資料夾

- 1\. 在電腦建立新資料夾

- 2\. 直接開啟 VS Code 新視窗，拖拉新資料夾進入 VS Code

- 3\. 開啟 VS Code 內建終端機：按 Ctrl ` (Tab 上面那個鍵)

- 4\. 生成 .git 資料夾：$`git init`

- 5\. 確認版本號：$`git --version `

### 如何取消 git init

- 使用 VS Code 內建終端機
  - 輸入$`Remove-Item -Recurse -Force .git`

- 手動刪除
  - 開啟 VS Code 檔案總管，直接刪除 .git 資料夾

返回[Git 技術筆記](#git-技術筆記)

## git add 【從工作目錄加到暫存區】

### 如何 git add

- 加入某個檔案：$`git add aaa.md`

- 加入某個資料夾(內的所有檔案)：$`git add 資料夾名稱/`

- 加入某個資料夾內的某個檔案：$`git add 資料夾名稱/aaa.md`

- 加入目前所有資料夾內全部新增或修改過的檔案：$`git add .`(點點前要有空格)

- 一次性加入特定多個檔案：$`git add aaa.md bbb.md ccc.md`(檔案中間空格即可)

> git add 不會加入資料夾，只會加入「檔案」。若命令輸入資料夾，代表加入該資料夾內的所有檔案。

### 如何取消 git add

- 移除某個檔案：$`git restore --staged aaa.md`

- 清空暫存區：$`git restore --staged .`

返回[Git 技術筆記](#git-技術筆記)

## git commit 【從暫存區加到本地儲存庫】

### 如何 commit

- 儲存檔案：$`git commit -m "第一次commit"`

> git add 後 commit 的東西就是剛才 add 過的檔案

- 修改最新commit的備註訊息(SHA值會變)：$`git commit --amend -m "有錯字可改"`

- 把所有「已修改」和「已刪除」的檔案 add 並 commit：$`git commit -a -m "跳過暫存區直接儲存囉"`

### 如何取消 commit

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

### git branch

- 查看目前 (本機) 有哪些 branches：$`git branch`

- 查看所有 branch 包含遠端(all)：$`git branch -a`

返回[Git 技術筆記](#git-技術筆記)

## git branch

- 在現在位置建立名為 momo 的分支：$`git branch momo`

- 刪除名為 momo 的分支：$`git branch -d momo`

- 強制刪除名為 momo 的分支：$`git branch -D momo`

- 重命名目前的分支：$`git branch -m 新分支名`

- 強制重命名目前的分支：$`git branch -M 新分支名`

- 在指定的 commit（SHA）位置建立一個新的分支：$`git branch 分支名 SHA值`

### git switch

- 將 HEAD(我的編輯位置) 移到指定的分支：$`git switch 指定分支名`

- 建立新分支並把位置切換去新分支：$`git switch -c 分支名`

- 切換位置回上一個分支：$`git switch -`

- 切換位置到指定 commit（進入斷頭 detached HEAD）：$`git switch --detach SHA值`

### git checkout

- 將 HEAD(我的編輯位置) 移到指定的分支：$`git checkout 指定分支名`

- 建立新分支並把位置切換去新分支：$`git checkout -b 分支名`

- 切換位置回上一個分支：$`git checkout -`

- 切換位置到指定 commit（進入斷頭 detached HEAD）：$`git checkout SHA值`

- 僅單一檔案內容恢復成指定 commit 的版本：$`git checkout SHA值 aaa.md`

返回[Git 技術筆記](#git-技術筆記)

## git push / git pull

### 在本地加入遠端 GitHub 專案

- 在本地加入遠端 GitHub 專案並取暱稱：$`git remote add 儲存庫名 儲存庫網址`

> 儲存庫名預設是 origin ，可自己改別的暱稱。

- 首次推送本地分支 main 到遠端儲存庫 origin，並設定上游分支的對應：$`git push -u 儲存庫名origin 本地分支main`

> 設定上游分支的對應是指 -u，即 --set-upstream 的縮寫。

- 儲存庫重新命名：$`git remote rename 舊名 新名`

### 正式 git push

- 推送預設分支到預設的遠端儲存庫：$`git push`

- 推送分支到遠端儲存庫：$`git push 儲存庫名origin 分支名main`

- 強制推送：$`git push 儲存庫名origin 分支名main -f`

- 本地的某分支推到遠端的某分支 (名字相同時可省略)：$`git push 儲存庫名origin 本地分支名:遠端分支名`

> 此動作容易將本地分支和遠端分支取不同名字導致不便。

- 刪除遠端分支：$`git push 儲存庫名origin :遠端分支名`

> 冒號前面要留空格，因為冒號前面原本是本地分支的位置，但現在空著，等於是用「空無一物」覆蓋遠端分支，結果就是把該遠端分支刪除了。

返回[Git 技術筆記](#git-技術筆記)

## .gitignore

返回[Git 技術筆記](#git-技術筆記)

## git reset

返回[Git 技術筆記](#git-技術筆記)

## git reflog

返回[Git 技術筆記](#git-技術筆記)

## git merge

返回[Git 技術筆記](#git-技術筆記)

### vim 編輯器

返回[Git 技術筆記](#git-技術筆記)

## git rebase

返回[Git 技術筆記](#git-技術筆記)
