### 同一性と等価性

```python

```

### 継承

- 抽象基底クラス ABC(abstract base class)ってのがあるんだ。いいね

`super`は組み込みの関数。
Ruby だと super()自体が継承元クラスの対応するメソッドの呼び出しに相当した。
python だと`Return a proxy object that delegates method calls to a parent or sibling class of type.`
つまり`super()`に続けて対応するメソッド呼び出し`.hoge()`などを記述する必要がある。

### 組み込みデータ型

#### container

> 他のオブジェクトに対する参照をもつオブジェクトもあります; これらは コンテナ (container) と呼ばれます。コンテナオブジェクトの例として、タプル、リスト、および辞書が挙げられます。

https://docs.python.org/ja/3/reference/datamodel.html#objects-values-and-types

#### iterator

> データの流れを表現するオブジェクトです。イテレータの \_\_next\_\_() メソッドを繰り返し呼び出す (または組み込み関数 next() に渡す) と、流れの中の要素を一つずつ返します。データがなくなると、代わりに StopIteration 例外を送出します。

> イテレータは、そのイテレータオブジェクト自体を返す \_\_iter\_\_() メソッドを実装しなければならない

https://docs.python.org/ja/3/glossary.html#term-iterator

#### iterable

> (反復可能オブジェクト) 要素を一度に 1 つずつ返せるオブジェクトです

> 反復可能オブジェクトを組み込み関数 iter() の引数として渡すと、 オブジェクトに対するイテレータを返します

https://docs.python.org/ja/3/glossary.html#term-iterable

#### sequence

> - 整数インデクスによる効率的な要素アクセスを \_\_getitem\_\_() 特殊メソッドを通じてサポートし、
> - 長さを返す **len**() メソッドを定義した
> - iterable です

https://docs.python.org/ja/3/glossary.html#term-sequence

### namedtuple

```python
>>> from collections import namedtuple
>>> Point = namedtuple('Point', ['x', 'y'])
>>> p = Point(2, 4)
>>> p.x
2
>>> p[0]
2
>>> p.x = 8
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: can't set attribute
```

- tuple との違い
  - ドットでアクセスできる = human readability が高い
- dict との違い
  - immutable
  - キーをインスタンス化以前に一律で定義できる
