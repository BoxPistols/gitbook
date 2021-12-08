---
description: Fizz Buzz Test
---

# Fizz Buzz on Rails

FizzBuzz.rb

```ruby
#=== FizzBuzzテスト ===

=begin
    - @Fizz 3の倍数
    - @Buzz 5の倍数
    - @FizzBuzz 3と5の倍数
    回答1. 1-30 まで表示
    回答2. 入力対話式
=end

#=== if文 === 対話式
# i = 入力
def fizzBuzz(i)
    if(i%3 == 0 && i%5 == 0)
        puts "FizzBuzz"
    elsif(i%3 == 0 )
        puts "Fizz"
    elsif(i%5 == 0)
        puts "Buzz"
    else
        puts "誰がやねん"
    end
end

puts "please input"
i = gets.to_i

puts fizzBuzz(i)


# 素材
# i = 30
# 3と5の倍数 puts "#{i} FizzBuzz"
# 3の倍数 puts "#{i} Fizz"
# 5の倍数 puts "#{i} Buzz"

# for: 1から30まで繰り返し、自動で表示
=begin
for i in 1..30
  if ((i % 3 == 0 && i % 5 == 0))
    puts "#{i} FizzBuzz"
  elsif (i % 3 == 0)
    puts "#{i} Fizz"
  elsif (i % 5 == 0)
    puts "#{i} Buzz"
  end
end
= end

=begin
    3 Fizz
    5 Buzz
    6 Fizz
    9 Fizz
    10 Buzz
    12 Fizz
    15 FizzBuzz
    18 Fizz
    20 Buzz
    21 Fizz
    24 Fizz
    25 Buzz
    27 Fizz
    30 FizzBuzz
=end

```
