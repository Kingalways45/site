#money_base
* locale[meta header]
* std[meta namespace]
* class template[meta id-type]

```cpp
namespace std {
  class money_base {
  public:
    enum part { none, space, symbol, sign, value };
    struct pattern { char field[4]; };
  };
}
```

##概要
(ここに、クラスの概要を記載する)

###メンバ型

| | |
|----------------------|--------------------------------------------------------------|
| `part` | 金額のフォーマットを表現するための列挙型 |
| `pattern` | 金額のフォーマット型 |

###part列挙型

| | |
|---------------------|-----------------------------------------------------------------------------------------------------|
| `none` | フォーマットのない文字を解析するための、省略可能な空白文字 |
| `space` | フォーマットが必要とされる文字を解析するための、省略可能な空白文字 |
| `symbol` | 通貨記号(￥、$など) |
| `sign` | 金額の正負を表す記号 |
| `value` | 金額の値 |


###patternクラス

| | |
|-----------------------------|------------------------------------------------------------------------|
| `char field[4];` | `char`に変換された`part`列挙値の配列 |


##例
```cpp
```

###出力
```
```

###参照
