# hands on 2 (リモートリポジトリを取り込もう)
### リモートリポジトリを取り込もう

現状の状態だとリモートリポジトリとローカルリポジトリに差異があります。その差異を無くしましょう。

---

## 手順

### 1. 今のブランチの状況を確認する
以下のコマンドを実行して、現在作業中のブランチ（カレントブランチ）を確認します：
```bash
git branch
```

---

### 2. mainブランチに戻る
カレントブランチが`main`でない場合、以下のコマンドで`main`ブランチに切り替えます：
```bash
git switch main
```

📖 **参考資料**
- [git switch](./command_docs/branch_and_switch.md#git-switch)

---

### 3. リモートリポジトリのmainブランチを取り込む
リモートリポジトリの最新の状態をローカルに反映するには、以下のコマンドを実行します：
```bash
git pull origin main
```

📖 **参考資料**
- [git pull](./command_docs/pull_fetch.md#git-pull)

---

### 4. 他の作業者のブランチを取り込む
他の作業者が作成したブランチを取得するには、以下のコマンドを実行します：
```bash
git fetch
```

📖 **参考資料**
- [git fetch](./command_docs/pull_fetch.md#git-fetch)

---

### ⚠️⚠️注意点⚠️⚠️
- 必ず作業を始める前に、リモートリポジトリの最新状態を取り込むようにしましょう。
- `git pull`や`git fetch`を実行する前に、現在のカレントブランチを確認してください。

### [落ち穂拾い]git pull / git fetchの違いについて

- [git fetch](./command_docs/pull_fetch.md#備考git-pullとfetchの違い)



---
[next page](hands_on_3.md)
