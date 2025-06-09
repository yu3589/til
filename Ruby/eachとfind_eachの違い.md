### eachとfind_eachの違い
- each : 全レコードを取得する
```ruby
Student.all.each do |student|
    puts student.name
end
```

- find_each : 分割してレコードを取得する
```ruby
Employee.find_each(batch_size: 500) do |employee|
    puts employee.name
end
```
batch_size は1回あたりに取得するレコード数を示す。(デフォルトでは1000件)

### SQLでの比較
- each :
```sql
SELECT * FROM students
```

- find_each :
```sql
-- 1回目
SELECT * FROM employees ORDER BY employee_id ASC LIMIT 500
-- IDの昇順で１〜500までのレコードを取り出す

-- 2回目（ループ処理後）
SELECT * FROM employees WHERE employee_id > 500 ORDER BY employee_id ASC LIMIT 500
-- 1回目の最後のID以降のレコードを取り出す

-- 以後同様
```
**同じIDを読み込むことないので、大量のデータを読み込む際は`find_each`を使った方が効率がいい**

参考：[【Rails】find_eachで大量データを扱う](https://qiita.com/taka_2525/items/ead7245aa2048f9216e6)
