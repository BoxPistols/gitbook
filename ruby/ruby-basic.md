---
description: Ruby code basic
---

# Ruby Basic

## Ruby基本構文

### 条件分岐

```ruby
# 変数宣言
t = 100

# もし (変数が101以上、かつ120でなければ。) / あえてややこしく表記
if (t > 100 && t != 120)
  puts "多い"
elsif t == 100
  puts "等しい"
else
  puts "その他"
end

# result 等しい
```

### Loop

#### while

```ruby
# while: 1になるまで引き算して繰り返す
i = 5
while  i > 0 do
  puts i
  i -= 1
end

# 5 4 3 2 1
```

#### for

```ruby
# for: 1から5まで繰り返す
for i in 1..5
  puts i
end
# 1 2 3 4 5
```

#### each do

```ruby
fruits = {"バナナ"=>2, "りんご"=>1, "マスカット"=>12}

puts "1人につき、"
fruits.each do |f, n| #ハッシュのキーバリューの代入
  puts "#{f}を#{n}個"
end
puts "ずつ配ります"

# 1人につき、
# バナナを2個
# りんごを1個
# マスカットを12個
# ずつ配ります
```

#### while break

```ruby
i = 1
while i <= 10 do
  if i == 3
    puts "一時停止"
    break
  end
  puts i
  i += 1
end

# 1 2 一時停止
```
