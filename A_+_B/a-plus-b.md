
```
while ( true ) {
```


## `process` オブジェクト

`process` はビルトインの現在のプロセスを表すオブジェクトです。

```
    variable String? input = process.readLine();
```

## `null` 許容型

`process.readLine()` の戻り値は `String?` です(おそらく)。  
`String?` の後ろの方の `?` は `null` が入っているかもしれない `String` 型という意味です。  
`String?` を別の表記(複合型表記)で表すと `String|Null` です。

`Null` 型の唯 1 つのオブジェクトが `null` です。

```
    if ( exists input ) {
        String[] tokens = input.split();
        int?[] numbers   = tokens.map( int.parse );
```

例えば `int.parse()` は整数値にパースできない文字列が渡された場合、`null` を返します。  
このようなメソッドないしは関数の戻り値型は ? 付きです。

## `is` 式

ある型 `T` の `null` 許容型 `T?` の値が `null` かどうかを確かめる 1 つの方法が `is` 式を使うことです。  
`is` 式は右オペランドの値が左オペランドの型あるいは左オペランドの型を継承した型である場合、真を返します。

## `if-exists` ガード句

もう 1 つの方法が `if-exists` ガード句を使う方法です。

```
Hoge? hoge = getHogeOrNull();

if ( exists hoge ) {
    // このブロックでは hoge は Hoge 型であることが明確になる。
    println( "it's Hoge" );
} else {
    println( "it's null" );
}
```

```
        if ( numbers.any( (int? element) => element is Null ) ) {
            println( "numbers only, please" );
        } else if ( numbers.length != 2 ) {
            println( "two numbers, please" );
        } else if ( !numbers.coalesced.every( (int element) => -1000..1000.include( element ) ) ) {
            println( "only numbers between -1000 and 1000, please" );
        } else if ( exists a = numbers.first, exists b = numbers.last ) {
            println( a + b );
        } else {
            println( "something wen wrong" );
        }
```

```
    } else {
        break;
    }
```


```
}
```
