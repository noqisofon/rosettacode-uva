## アスタリスクの階段を作る

以下のような出力を行います:

    *
    **
    ***
    ****
    *****

```
for ( auto i in 1..5 ) {
    for ( auto j in 1..j ) {
        print( "*" );
    }
    println();
}
```
