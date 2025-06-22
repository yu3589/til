times記法

1. ブロックを {} で書く方法：  
(do と end が`{}`に置き換わるイメージ)
```ruby
n.times { |i| arr[i] = gets.to_i }
```

2. ブロックを do...end で書く方法：
```ruby
n.times do |i|
  arr[i] = gets.to_i
end
```
