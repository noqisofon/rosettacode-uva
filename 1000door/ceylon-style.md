## クラス

`Door` クラスを定義してみます。

ドアには開いている状態(`opended`)と閉じている状態(`closed`)があります。  
下記のようになります:

```
shared abstract class Door(shared actual String label) of opened | closed {
    shared formal Door toggle();
}
```

これを Rust で書けばこうなります:

``` rust
enum Door {
    opened,
    closed
}
```

## object クラス(シングルトン)

```
object opened extends Door("Open") { toggle() => closed; }
```

```
object closed extends Door("Closed") { toggle() => opened; }
```

Rust で書けばこうなるでしょう:

``` rust
impl Door {
    fn toggle(&self) -> Door {
        match self {
            opened => closed,
            closed => opened
        }
    }
}
```

```
variable Door[] doors = new Door[]( 100 );

for ( int i in 0..doors.length ) {
    for ( int j in 0..doors.length ) {
        if ( ( j + 1 ) % ( i + 1 ) == 0 ) {
            doors[j] = doors[i].toggle();
        }
    }
}
```

```
for ( int i in 0..doors.length ) {
    Door door = doors[i];
    
    println( "Door #${i} ${door.label}" );
}
```
