第四週：Git Flow、GitHub Flow 的用法
本次作業主要練習 Git 與 GitHub 的基本協作流程，包括：
1. 建立分支（Branch）
2. 合併分支（Merge）
3. Fork 專案
4. 建立 Pull Request
專案連結
1. 母專案 -- https://github.com/Erkmrcl17/git-example/tree/main
   - 分支 -- https://github.com/Erkmrcl17/git-example/tree/testbranch
2. 子專案 -- https://github.com/Erkmrcl17/git-examples
3. Pull Request -- https://github.com/se-test-examples/git-examples/pull/2
一、建立分支 Branch
首先將自己的專案 Clone 到本機：
git clone https://github.com/Erkmrcl17/git-example.git
cd git-example
確認 Remote Repository：
git remote -v
建立新的 testbranch 分支：
git checkout -b testbranch
查看目前分支：
git branch
接著在 testbranch 中修改 index.html，完成後執行：
git add .
git commit -m "add branch practice"
git push -u origin testbranch
這樣 GitHub 上就會同時存在 main 與 testbranch。
分支：
https://github.com/Erkmrcl17/git-example/tree/testbranch
二、合併分支 Merge
完成 testbranch 的修改後，切換回 main：
git checkout main
將 testbranch 合併到 main：
git merge testbranch
本次執行結果為 Fast-forward Merge。
最後將合併後的 main Push 到 GitHub：
git push origin main
至此完成分支建立與合併操作。
三、Fork 專案
本次 Fork 的原始專案：
https://github.com/se-test-examples/git-examples
在 GitHub 上點選：
Fork → Create fork
完成後，在自己的 GitHub 帳號下建立子專案：
https://github.com/Erkmrcl17/git-examples
GitHub 顯示：
Forked from se-test-examples/git-examples
代表 Fork 成功。
四、修改 Fork 後的子專案
將 Fork 後的 Repository Clone 到本機：
git clone https://github.com/Erkmrcl17/git-examples.git
cd git-examples
確認 Remote：
git remote -v
接著新增 forkPractice.md，用來練習 Fork 與 Pull Request。
完成修改後執行：
git add .
git commit -m "add forkPractice.md"
git push origin main
修改即成功 Push 到自己的 Fork Repository。
五、建立 Pull Request
完成子專案修改後，在 GitHub 上選擇：
Contribute → Open pull request
Pull Request 的方向：
Erkmrcl17/git-examples
        │
        │ Pull Request
        ▼
se-test-examples/git-examples
設定為：
base repository: se-test-examples/git-examples
base: main

head repository: Erkmrcl17/git-examples
compare: main
Pull Request 標題：
Add fork practice file
說明：
新增 forkPractice.md，用於練習 GitHub Fork 與 Pull Request 流程。
最後點選 Create pull request。
Pull Request：
https://github.com/se-test-examples/git-examples/pull/2
目前 Pull Request 狀態為 Open。
六、Git 流程說明
Branch 與 Merge
本次先建立獨立的 testbranch：
git checkout -b testbranch
在分支完成修改後，再合併回主要的 main：
git checkout main
git merge testbranch
這種分支開發方式可以避免直接在主要分支進行修改，完成後再將功能整合回主線。
Fork 與 Pull Request
Fork 與 Pull Request 的流程如下：
原始 Repository
      ↓
     Fork
      ↓
自己的 Repository
      ↓
修改、Commit、Push
      ↓
Pull Request
      ↓
原始 Repository
這種方式屬於 GitHub 常見的協作流程。當開發者沒有原始 Repository 的直接寫入權限時，可以先 Fork 專案，在自己的 Repository 完成修改，再透過 Pull Request 請原專案管理者審查與決定是否合併。
七、本次使用指令整理
# Clone 自己的母專案
git clone https://github.com/Erkmrcl17/git-example.git
cd git-example

# 查看 Remote
git remote -v

# 建立 testbranch
git checkout -b testbranch

# 查看分支
git branch

# Commit 分支修改
git add .
git commit -m "add branch practice"

# Push testbranch
git push -u origin testbranch

# 切換回 main
git checkout main

# 合併 testbranch
git merge testbranch

# Push main
git push origin main

# Clone Fork 後的子專案
git clone https://github.com/Erkmrcl17/git-examples.git
cd git-examples

# Commit 子專案修改
git add .
git commit -m "add forkPractice.md"

# Push 到自己的 Fork
git push origin main
八、心得
透過本次練習，我實際操作了 Git 的 Branch 與 Merge，也使用 GitHub 完成 Fork 與 Pull Request。Branch 可以讓不同修改在獨立分支中進行，完成後再合併至主要分支；Fork 則可以將其他人的專案複製到自己的帳號中進行修改，再透過 Pull Request 將修改提交給原專案。
經過這次實際操作，我更加了解 Branch、Merge、Fork 與 Pull Request 的差異，以及 Git 與 GitHub 在版本控制和多人協作中的基本使用方式。