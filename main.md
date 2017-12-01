# Effective Rubyつまみ食い

---

## Effective 言語名とは
多分Effective C++が一番最初

言語特有の罠を学び正しく書けるように

仕事で使うには必読

### いくらか面白いのを紹介します

---

## Struct
Dataを扱うようにWrapされたclass

特定の要素を持つHashを置換できる

メソッドが定義できるので柔軟

```ruby
# 定義
Person = Struct.new(:name, :age) do
  def to_s
    "#{name} (#{age})"
  end
end
# 利用
ponkotuy = Person.new('ponkotuy', 30)
p "#{ponkotuy.to_s}が逮捕された"
```

---

## 等値の違い
Rubyには4種類の等値がある(ひどい)

- ==
- equal?
- eql?
- ===

この全てで結果と利用方法が異なる

---

### ==
最も良く見るやつ

ちなみに1.0 == 1

### equal?
オブジェクト参照の比較

同じオブジェクトを参照しているとtrue

---

### eql?
Hashで等値比較をするときに使われる

eql?がtrueのときだけHashのkeyがマージされる

==との主要な違い

1.eql?(1.0) # false

### ===
case文で使われる等値比較

特に正規表現の実装が==と異なる

*見た目に反して交換則を満たさない*
