## マイグレーション操作について：削除・ロールバック・null制約の注意点  
### マイグレーションファイル削除手順
1. statusを確認  
`docker compose exec web rails db:migrate:status`
2. 削除したいマイグレーションIDをdownさせる  
`docker compose exec web bundle exec rails db:migrate:down VERSION='マイグレーションID'`
3. 対象のマイグレーションIDがdownになったのを確認  
`docker compose exec web rails db:migrate:status`
4. ファイルを削除　※ ディレクトリ消したい場合は`rm -rf`を使う  
`rm 削除したいマイグレーションファイルの相対パス or フルパス`

### null制約追加時の注意  
- 対象カラムにNULL値があるとmigrationでエラーになるため、事前に `update_all` などで補完しておく。  

### ロールバックの使い所  
- マイグレーションファイルを修正したい時  
例) `docker compose exec web bundle exec rails db:rollback STEP=2`  
    => 直近の2つのマイグレーションをロールバック  
  　(STEPを記載しないと直近のマイグレーションIDが適応される)  

参考：[【Rails】マイグレーションファイルの削除](https://qiita.com/ISSO33/items/33a935cb3255c269bef2)
