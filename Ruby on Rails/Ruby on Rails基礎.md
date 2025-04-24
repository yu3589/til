## asset pipeline
JavaScript、CSS、画像ファイルなどの静的アセットを整理・キャッシュ・配信するために設計されたライブラリ
- マニフェストファイルにブラウザで表示したいJavaScriptやCSSを記載する




### mapメソッド・pluckメソッドの違い
- mapメソッド
要素を1つずつ処理して新しい配列を返す。
取り出したいカラム以外の情報も取得するため、メモリ使用量が増える。
```ruby
# SELECT `staffs`.* FROM `staffs`

Staff.all.map(&:name)
# => ["Aさん","Bさん","Cさん"]
```

- pluckメソッド
特定のカラムの値だけ取得したい場合に使う。
メモリ使用量が少なく、大量のデータを扱う場合はパフォーマンスが高い。
メソッド実行時に毎回SQL文が発行されてしまうため注意が必要。
```ruby
# SELECT `staffs`.`name` FROM `staffs`

Staff.all.pluck(:name)
# => ["Aさん","Bさん","Cさん"]
```
