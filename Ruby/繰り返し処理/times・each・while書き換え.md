## 繰り返し処理
- 引数numberに渡された数値を使って、1から順に渡された引数の値までを足し算し、合計値を返す処理。
### times
```ruby
def total_until(number)
  response = 0 # 合計値を入れる変数。初期値は0
  number.times do |n| # numberの数だけ処理を行う。nは0から始まる
    response += (n + 1) # 繰り返すたびに　(n + 1) を足していく
  end
  response　# 最終的な合計値を返す
end
puts total_until(5)
# => 15
```
### each
- each ver.
```ruby
def total_until(number)
  response = 0 
  (1..number).each do |n| # nは1から始まる
    response += n 
  end
  response
end
puts total_until(5)
# => 15
```
### while
- while ver.
```ruby
def total_until(number)
  response = 0  
  n = 1         # カウンター変数（1から始める）

  while n <= number  # number以下の間繰り返す
    response += n    
    n += 1           # カウンターを1増やす
  end

  response  #
end
puts total_until(5)
# => 15
```
