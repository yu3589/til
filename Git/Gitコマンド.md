- git log : コミットの履歴確認
- git stash : コミットしたくないファイルの一時退避
- git fetch : margeをせずに履歴を取得

---

- mainブランチで作業＆コミットした時の対処法
```ruby
# 1. コミットを取り消してステージング状態に戻す
$ git reset --soft HEAD^

# 2. 状態確認（変更がステージにある）
$ git status

# 3. 一旦変更分を退避
$ git stash

# 4. 新しいブランチを作成
$ git checkout -b <任意のブランチ名>

# 5. 退避した変更を戻す (新しいブランチに変更分が反映される)
$ git stash pop

# 6. add & commit
$ git add  <変更分のファイル名>
$ git commit -m "任意のメッセージ"

# 7. プッシュしてプルリクエスト作成
$ git push origin <4.のブランチ名>
```
