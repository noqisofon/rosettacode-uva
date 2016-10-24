
`functions` は `int` 型を返すクロージャのリストです。

```
variable auto functions = new List<void -> int>();
```
  
ここで、`int` 型を返すクロージャの型は `void -> int` と表されています。  
普通に(`auto` を使わずに)クロージャを宣言してしまうと:

```
int|float->int|float square = (int|float x) => x * x;      // `->` の間のスペースを詰めなければならないわけではないが、
                                                           // なんとなく詰めたくなってくる。
```

というようなことになるので、何かしら考えなければいけないところです。

```
for ( auto i in 0..10 ) {
    variable auto capturedValue = i;
    
    closures.add( () => capturedValue * capturedValue );
}
```

```
functions.forEach( (auto fn) => println( fn() ) );
```
