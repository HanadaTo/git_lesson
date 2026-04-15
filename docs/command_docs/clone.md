# Git Clone
```
💡Gitリポジトリをローカル環境に複製するためのコマンドです。
```
![image](./images/github_clone_image.png)

## 利用するケース
- 初めてチームのリポジトリをローカル環境に複製する場合
- 新しいプロジェクトに参加し、リポジトリを取得する必要がある場合
- 他の開発者が作成したリポジトリを自分の環境で確認・編集したい場合


## 手順

1. クローンしたいリポジトリのURLを取得します。Githubを開いて、`code`->`SSH`->`URLをコピー`
    * SSH設定をしていない場合はHTTPSでもOK
   ![image](./images/github_clone.png)


2. ターミナルを開きます。(cmd + J)
3. 以下のコマンドを実行します。
   ```bash
   git clone <リポジトリのURL>
   ```
   例:
   ```bash
   git clone git@github.com:hrforcedsu/git_lesson.git

   Cloning into 'git_lesson'...
    remote: Enumerating objects: 3, done.
    remote: Counting objects: 100% (3/3), done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
    Receiving objects: 100% (3/3), done.

   ```
4. コマンド実行後、指定したリポジトリがローカル環境に複製されます。

### 注意点
- クローン先のディレクトリに同名のフォルダが存在しないことを確認してください。

[next page]()
