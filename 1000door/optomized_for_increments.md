
開いているドアの数です。

```
variable int openDoorAmount = 1;
```

ドアの総数です。

```
variable int doorAmount     = 0;
```

## 範囲リテラル

`0..10` は 0 から 9 までですが、`1...10` は 1 から 10 迄です。

```
for ( int i in 1...100 ) {
    print( "Door #${i + 1}" );
    
    if ( i == openDoorAmount ) {
        println( "Open" );
        
        ++ doorAmount;
        openDoorAmount += 2 * doorAmount + 1;
    } else {
        println( "Closed" );
    }
}
```
