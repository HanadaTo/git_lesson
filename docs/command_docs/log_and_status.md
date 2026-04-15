# git log

## コマンドの概要
- **git log**: リポジトリのコミット履歴を表示します。
  - 誰が、いつ、どのような変更を行ったかを確認できます。

## コマンド例
```bash
# 全てのコミット履歴を表示
git log

# 最新の3件のコミットを表示
git log -n 3

# 特定のファイルに関連するコミットを表示
git log <file-name>
```

## オプションコマンド
- `-n <number>`: 表示するコミットの数を指定します。
- `--oneline`: 各コミットを1行で簡潔に表示します。
- `--graph`: ブランチの構造を視覚的に表示します。
- `--author=<name>`: 特定の作者によるコミットを表示します。

## 利用するケース
- 過去の変更履歴を確認したい場合。
- 誰が特定の変更を行ったかを調べたい場合。
- ブランチの構造やマージの履歴を視覚的に確認したい場合。

---

# git status

## コマンドの概要
- **git status**: リポジトリの現在の状態を確認します。
  - 変更されたファイルや、ステージングエリアに追加されたファイルを確認できます。

## コマンド例
```bash
# 現在の状態を確認
git status

# 簡潔な出力形式で状態を確認
git status -s
```

## オプションコマンド
- `-s` (または `--short`): 簡潔な形式で状態を表示します。
  - 例: `M` (変更あり), `A` (追加されたファイル), `??` (未追跡のファイル)。
- `--ignored`: 無視されているファイルも表示します。

## 出力の見方
`git status` コマンドの出力には、リポジトリの現在の状態が表示されます。以下は主な出力例とその意味です。

### 主な出力例
1. **ブランチ情報**
   ```
   On branch main
   ```
   - 現在作業中のブランチ名を示します。

2. **変更がない場合**
   ```
   nothing to commit, working tree clean
   ```
   - 変更がなく、リポジトリが最新の状態であることを示します。

3. **変更がある場合**
   ```
   Changes not staged for commit:
     (use "git add <file>..." to update what will be committed)
     (use "git restore <file>..." to discard changes in working directory)
       modified:   file1.txt
   ```
   - **Changes not staged for commit**: ステージングエリアに追加されていない変更。
   - `modified`: ファイルが変更されたことを示します。

4. **新しいファイルがある場合**
   ```
   Untracked files:
     (use "git add <file>..." to include in what will be committed)
       new_file.txt
   ```
   - **Untracked files**: Git にまだ追跡されていない新しいファイル。

5. **ステージングエリアに追加された変更**
   ```
   Changes to be committed:
     (use "git restore --staged <file>..." to unstage)
       new file:   file2.txt
   ```
   - **Changes to be committed**: 次のコミットに含まれる変更。
   - `new file`: 新しいファイルがステージングエリアに追加されたことを示します。

### 状態の確認フロー
1. **`git status` を実行**して、現在の状態を確認します。
2. 必要に応じて以下の操作を行います:
   - ステージングエリアに追加: `git add <file>`
   - 変更を破棄: `git restore <file>`
   - ステージングエリアから削除: `git restore --staged <file>`

---

## まとめ

| コマンド       | 主な用途                     | 主なオプション例             |
| -------------- | ---------------------------- | ---------------------------- |
| **git log**    | コミット履歴の確認           | `-n`, `--oneline`, `--graph` |
| **git status** | 現在のリポジトリの状態を確認 | `-s`, `--ignored`            |

| 状態                      | 出力例                          | 意味                                     |
| ------------------------- | ------------------------------- | ---------------------------------------- |
| 変更なし                  | `working tree clean`            | リポジトリが最新の状態                   |
| 変更あり (未ステージング) | `Changes not staged for commit` | ステージングエリアに追加されていない変更 |
| 新しいファイル            | `Untracked files`               | Git に追跡されていないファイル           |
| ステージング済みの変更    | `Changes to be committed`       | 次のコミットに含まれる変更               |

```bash
# 実践例: 状態を確認して履歴を調べる
git status
git log --oneline --graph
```

初心者の方は、まず `git status` で現在の状態を確認し、次に `git log` で履歴を調べる流れを覚えると便利です！


