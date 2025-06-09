### mapメソッド・pluckメソッドの違い

- mapメソッド (Ruby arrayクラスのメソッド)  
各要素に処理を適用して、新しい配列を返す
```ruby
# SELECT `staffs`.* FROM `staffs`

Staff.all.map(&:name)
# => ["Aさん","Bさん","Cさん"]
```
=> 取り出したいカラム以外の情報も取得するため、メモリ使用量が増える。


- pluckメソッド (Railsの**ActiveRecord**のメソッド)  
データベースから特定カラムだけを配列で取り出す
```ruby
# SELECT `staffs`.`name` FROM `staffs`

Staff.all.pluck(:name)
# => ["Aさん","Bさん","Cさん"]
```
=> メモリ使用量が少なく、大量のデータを扱う場合はパフォーマンスが高い。
=> メソッド実行時に毎回SQL文が発行されてしまうため注意が必要。
