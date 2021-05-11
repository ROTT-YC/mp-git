# Git 入門
參考順序 --- [git add、git commit - 提交版本](https://w3c.hexschool.com/git/b9be5b1e)
* git status
```
Untracked 的意思是，Git 偵測到你有新增這筆檔案，但尚未是 Git 追蹤的對象
```
* git add
```
將檔案加入到索引
```
* git commit -m " 填寫版本資訊 "
```
透過commit指令，來提交一個新版本
```
* git log
```
觀看新增的版本
```
* git remote add origin *https://github.com/ROTT-YC/mp-git.git*
>要準備把東西推上遠端的 Git 伺服器，需要設定一個端節的節點
>>1. git remote 指令，主要是跟遠端有關的操作。
>>2. add 指令是指要加入一個遠端的節點。
>>3. 在這裡的 origin 是一個「代名詞」，指的是後面那串 GitHub 伺服器的位置。

---
* pwd 
顯示目前路徑
* ls -al
列出所有目錄下檔案(-al包含隱藏檔案)
* mkdir  mp-git
新增資料夾 命名為mp-git
* cd
切換到輸入的目錄底下(在目錄名後要加/)
cd兩個句點會回到上層目錄
* touch
新增檔案
* rm
移除檔案
* echo "內容" >> Readme.md
新增內容至檔案中

![](https://i.imgur.com/n4WSE4i.png)
有更新的檔案需push的話，需先add進入索引後commit，再push才OK





```
內容引用: https://gitbook.tw/chapters/github/push-to-github.html
```


---
# Branch

* git branch
```
查閱分支
```
>新增分支 - guest
>ex: $ git branch guest
>切換分支
>ex: $ git checkout guest
>刪除分支
>ex: $ git branch -d guest


