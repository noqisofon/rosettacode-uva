
## 中身が入った配列を作る

3 つの要素を持つ文字列型の配列を作るにはこのようにします:

```
String words = [ "these", "are", "arrays" ];
```

## 要素の数を指定して配列を作る

10 個の要素を持つ `int` 型の空の配列を作る時はこのようにします:

```
variable int[] number = new int[]( 10 );
```

`variable` アノテーションを付けない場合、それぞれの要素に値を設定できないという warning が出るかもしれません。

`int` 型の 3 つの要素を持ち、入っている要素の値がそれぞれ `21`、`14`、`63` の配列を作るにはこのようにします:

```
int[] moreNumbers = int[3] [ 21, 14, 63 ];
```

## 可変長配列を使う

普通の配列(`Array`) は要素の型と長さが決まっています。  
いくつの要素を容れるかわからない場合には可変長配列がおすすめです。

`uva.collections` を `import` し、`ArrayList` を指定します:

```
import uva.collections { ArrayList };
```

要素を追加する時は `add()` を使います。  
要素を参照する場合は配列と一緒です。

```
ArryList<int> ary = new ArrayList<int>();

ary.add( 1 );
ary.add( 3 );

ary[1] = 2;

println( ary[1] );   // => 2
```
