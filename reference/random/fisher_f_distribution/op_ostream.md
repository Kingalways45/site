#operator<<
* random[meta header]
* std[meta namespace]
* function[meta id-type]
* cpp11[meta cpp]

```cpp
namespace std {
  template <class CharT, class Traits, class RealType>
  basic_ostream<CharT, Traits>& operator<<(
    basic_ostream<CharT, Traits>& os
    const fisher_f_distribution<RealType>& x);
}
```
* basic_ostream[link /reference/ostream/basic_ostream.md]

##概要
ストリームへの出力を行う。


##効果
`os`に対して、分布オブジェクト`x`の現在状態を出力する。


##事後条件
`os`のフォーマットフラグが、この関数を呼び出す前の状態に戻ること。


##戻り値
`os`


##例
```cpp
#include <iostream>
#include <random>

int main()
{
  std::fisher_f_distribution<> dist(3.0, 4.0);
  std::cout << dist << std::endl;
}
```

###出力例
```
3.00000000000000000e+00 4.00000000000000000e+00 1.50000000000000000e+00 1.00000000000000000e+00 0.00000000000000000e+00 1.00000000000000000e+00 0 2.00000000000000000e+00 1.00000000000000000e+00 0.00000000000000000e+00 1.00000000000000000e+00 0
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation.md#clang): ??
- [GCC](/implementation.md#gcc): 
- [GCC, C++11 mode](/implementation.md#gcc): 4.7.2
- [ICC](/implementation.md#icc): ??
- [Visual C++](/implementation.md#visual_cpp) ??


##参照


