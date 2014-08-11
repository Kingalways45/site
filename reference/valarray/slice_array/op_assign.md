#operator=
```cpp
const slice_array& operator=(const slice_array& ar) const; // (1)
void operator=(const valarray<T>& ar) const;               // (2)
void operator=(const T& value) const;                      // (3)
```

##概要
- (1) : 元となる`valarray`オブジェクトから参照によって抽出した各要素に、`ar`が参照する各要素を代入する
- (2) : 元となる`valarray`オブジェクトから参照によって抽出した各要素に、`ar`の各要素を代入する
- (3) : 元となる`valarray`オブジェクトから参照によって抽出した各要素に、`value`を代入する


##効果
概要通り


##戻り値
- (1) : `*this`
- (2), (3) : なし


##備考
- (2) : `valarray`から抽出した要素数と`ar`の要素数が異なる場合、その挙動は未定義。


##例
```cpp
#include <iostream>
#include <valarray>

template <class T>
void print(const char* name, const std::valarray<T>& v)
{
  std::cout << name << " : {";
  bool first = true;

  for (const T& x : v) {
    if (first) {
      first = false;
    }
    else {
      std::cout << ',';
    }
    std::cout << x;
  }
  std::cout << "}" << std::endl;
}

int main()
{
  std::valarray<int> v = {1, 2, 3, 4, 5, 6};

  const std::size_t start = 1u;  // 開始位置
  const std::size_t length = 3u; // 要素数
  const std::size_t stride = 2u; // 何個置きに処理するか

  std::slice_array<int> result = v[std::slice(start, length, stride)];

  // (1)
  // result1が参照する各要素に、resultが参照する各要素を代入する
  std::valarray<int> v1 = {1, 2, 3, 4, 5, 6};
  std::slice_array<int> result1 = v1[std::slice(0, 3, 1)];
  result1 = result;
  print("assign slice_array", v1);

  // (2)
  // resultが参照する要素全てに、33を代入
  result = std::valarray<int>(33, length);
  print("assign valarray", v);

  // (3)
  // resultが参照する要素全てに、55を代入
  result = 55;
  print("assign value", v);
}
```

###出力
```
assign slice_array : {2,4,6,4,5,6}
assign valarray : {1,33,3,33,5,33}
assign value : {1,55,3,55,5,55}
```

