#lowest
* limits[meta header]
* std[meta namespace]
* numeric_limits[meta class]
* function[meta id-type]
* cpp11[meta cpp]

```cpp
static constexpr T lowest() noexcept;
```

##概要
型ごとの値の最小値を取得する


##戻り値
指定された型の有限値のうち最小のもの。  
浮動小数点数の場合、無限大やNaNではない。


##例外
投げない


##備考
`is_specialized == false`の場合は`T()`が返される。


##例
```cpp
#include <iostream>
#include <limits>

int main()
{
  constexpr int i = std::numeric_limits<int>::lowest();
  constexpr double d = std::numeric_limits<double>::lowest();

  std::cout << i << std::endl;
  std::cout << d << std::endl;
}
```
* lowest[color ff0000]

###出力例
```
-2147483648
-1.79769e+308
```


##バージョン
###言語
- C++11

###処理系
- [Clang, C++11 mode](/implementation.md#clang): 3.0
- [GCC, C++11 mode](/implementation.md#gcc): 4.5.4
- [ICC](/implementation.md#icc): ?
- [Visual C++](/implementation.md#visual_cpp): 10.0, 11.0, 12.0, 14.0, 14.1

##参照
- [N2348 Wording for `std::numeric_limits<T>::lowest()`](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2348.pdf)

