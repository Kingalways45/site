#begin
* set[meta header]
* std[meta namespace]
* set[meta class]
* function[meta id-type]

```cpp
iterator begin() noexcept;
const_iterator begin() const noexcept;
```


##概要
`set` コンテナの先頭要素を参照するイテレータを返す。

内部的に、`set`コンテナは要素を下位から上位へと並べており、従って `begin()` は `set` 内の最下位のキーにあたる値を返す。


##戻り値
コンテナの先頭要素へのイテレータ。

`iterator` と `const_iterator` はともにメンバ型である。`set` クラステンプレートにおいて、これらは双方向イテレータである。


##計算量
定数時間。


##例
```cpp
#include <iostream>
#include <set>

int main()
{
  std::set<int> c;
  c.insert(5);
  c.insert(2);
  c.insert(4);
  c.insert(1);
  c.insert(0);
  c.insert(0);
  c.insert(9);

  std::set<int>::iterator i = c.begin();
  while (i != c.end())
    std::cout << *i++ << " ";
  std::cout << std::endl;
}
```
* iostream[link ../../iostream.md]
* set[link ../../set.md]
* insert[link insert.md]
* begin[color ff0000]
* end[link end.md]
* cout[link ../../iostream/cout.md]
* endl[link ../../ostream/endl.md]

###出力
```
0 1 2 4 5 9 
```

##関連項目

| 名前                       | 説明                             |
|----------------------------|----------------------------------|
| [`set::end`](end.md)       | 末尾を指すイテレータを取得する   |
| [`set::rbegin`](rbegin.md) | 末尾を指す逆イテレータを取得する |
| [`set::rend`](rend.md)     | 先頭を指す逆イテレータを取得する |
