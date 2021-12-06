---
description: Ruby Method
---

# Ruby Basic Method

## Method

```ruby
#=== メソッド ====
def say
  "Hey!"
end

puts say # Hey!

#=== 引数 ===

def saySay(volime)
  "#{volime}声をを出す"
end

puts saySay("小さく") # result: 小さく声をを出す

#=== 返り値 ===

def sayReturn(r)
  return "#{r}声をを出す" # result: 大きく声をを出す / ここまでを返す
  puts "スコープ外" # 非表示
  "スコープ外!" # 非表示
end

puts sayReturn("大きく")

#=== 返り値 + 条件分岐 ===

def calc(num)
  return "お金を持っています" if num > 0 # <- 該当しない
  "お金がありません" # <- result
end

puts calc(0)

```
