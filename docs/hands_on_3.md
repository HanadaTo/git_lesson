# hands on 3
### 間違えたcommitを取り消ししよう。

最初は間違えてaddしたり、commitしたり、pushしたりします。
その時に落ち着いた作業できるように練習しましょう。

---
## 事前準備
### 1. 今のブランチを確認しましょう
```
git branch
## もしカレントブランチがmainでなければswitchしてください。
git switch main
```

### 2. 新しいブランチを作成しましょう
```
git branch {自分の名前}_hanson3
```

### 3. ブランチを切り替えましょう
```
git switch {自分の名前}_hanson3
```

## ケース1 | 間違えてgit addしちゃった。。。

### 1. hands-onで作成した{自分の名前}.mdの２行目に内容を記載しましょう

例
```
2. 明日の天気は？
> 晴れ
```

### 2. 今の状況を確認してみましょう
```
git status
```
📖 **参考資料**
- [git status](./command_docs/log_and_status.md#git-status)

### 3. ステージングにあげましょう
```
git add {自分の名前}.md
```

### 4. もう一度今の状況を確認してみましょう
```
git status
```

### 5. git addを取り消しましょう
```
git reset HEAD
```

### 6. もう一度今の状況を確認しましょう
```
git status
```

### 7. 回答結果が上記2と同じ状態になっていれば成功


## ケース2 | 間違えてcommitしちゃった。

### 1. hands-onで作成した{自分の名前}.mdの２行目に内容を記載しましょう (⚠️すでに記載済みならスルーでOK)

例
```
2. 明日の天気は？
> 晴れ
```

### 2. ステージングにあげましょう
```
git add {自分の名前}.md
```

### 3. commitしましょう
```
git commit -m '間違いだよーん。'
```

### 4. git logで状態を確認しましょう
```
git log
```

📖 **参考資料**
- [git log](./command_docs/log_and_status.md#git-log)

結果
```
commit 123123123 (HEAD -> xxxxx)
Author: xxxx <xxxxx>
Date:   Sun Apr 1 23:59:59 2025 +0900

    間違いだよーん。
```

### 5. commitを取り消そう
- 先ほどのgit logのcommit No.をコピーしておきましょう
```
git reset --soft 123123
```

📖 **参考資料**
- [git reset](./command_docs/reset_and_revert.md#git-reset)

### 6. 再度git logをしましょう
```
git log {自分の名前}_hanson3
```

- 先ほどのcommit messageが消えていればOK


## ケース3 | git commitしたけど、変更した内容/commitどちらも要らない

### 1. hands-onで作成した{自分の名前}.mdの２行目に内容を記載しましょう (⚠️すでに記載済みならスルーでOK)

例
```
2. 明日の天気は？
> 晴れ
```

### 2. git add ~ git commit しましょう
```
git add {自分の名前}.md
git commit -m 'やらかしたー。'
```

### 3. git logを確認して、commit Hashをコピーしておきましょう
```
git log
```

結果
```
commit 123123123 (HEAD -> xxxxx)
Author: xxxx <xxxxx>
Date:   Sun Apr 1 23:59:59 2025 +0900

    やらかしたー。
```

### 4. 取り消そう
```
git reset --hard {さっきのgitlogで取得したcommit hash}
```

📖 **参考資料**
- [git reset](./command_docs/reset_and_revert.md#git-reset)

### 5. git logを再度確認して、先ほどのcommitが消えているか確認しましょう
```
git log
```


## ケース4 | 間違えてpushしてしまった。けど間違えたことも履歴に残しておきたい。

### 1. hands-onで作成した{自分の名前}.mdの２行目に内容を記載しましょう (⚠️すでに記載済みならスルーでOK)

例
```
2. 明日の天気は？
> 晴れ
```

### 2. ~git pushまでしましょう
```
git add
git commit -m 'git revert'
```

### 3. git logで上記のcommit idをコピーしましょう
```
git log
```

### 4. git revertしましょう
```
git revert {上記のcommit id}
```

📖 **参考資料**
- [git revert](./command_docs/reset_and_revert.md#git-revert)

### 5. git pushしてgithubがどんな状態になっているか確認しましょう
```
git push origin  {自分の名前}_hanson3
```


# 落ち穂拾い
クレデンシャル情報（PASSWORDなど）を誤ってgithubにpushしてしまった場合、git resetコマンドをしてもリモートリポジトリに履歴が残るとして残ってしまいます。
なので、
- クレデンシャル情報（PASSWORDなど）のハードコーディングはしない。
- システム上クレデンシャル情報が必要な場合は、.envなどにまとめて、そこから認証する。(.envを.gitignoreすることが前提）
- もし誤ってPUSHしてしまった場合は、速攻で柳谷にご連絡ください。

---
[next page](hands_on_4.md)
