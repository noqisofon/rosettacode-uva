
## 配列の宣言

100 の要素を持つ bool 型の配列、doors を用意します。

variable はこの変数が可変だという意味を持つアノテーションです。  
variable を付けない場合、変数は値の再設定が認められません。

```
variable bool[] doors = new bool[]( 100 );
```

値の再設定が認められないということが、変数が指している参照のことなのか、実体のことなのかはまだ決まっていません。

## for 文

Uva は C 言語風の for 文を使うことができません。  
代わりに for-in 文を使うことができます。

```
for ( int i in 0..doors.length ) {
    doors[i] = false;
}
```

`bool` 型のデフォルト値は `false` なので、上記の `false` に初期化する処理は不要です。

```
for ( int i in 0..doors.length ) {
    for ( int j in 0..doors.length ) {
        if ( ( j + 1 ) % ( i + 1 ) == 0 ) {
            doors[j] = ! doors[i];
        }
    }
}
```

## 標準出力への出力　その 2

`println()` は `stdout.println()` のエイリアスです。

```
println( "Passes Completed!!! Here are the results" );
println();
```

また、文字列リテラルに変数の値を埋め込むことができます。

```
for ( int i in 0..doors.length ) {
    String status = doors[i] ? "Open" : "Closed";

    println( "Door #${d + 1} ${status}" );
}
```
