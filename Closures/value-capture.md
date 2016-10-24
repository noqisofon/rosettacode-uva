
```
variable auto functions = new List<void -> int>();

for ( auto i in 0..10 ) {
    variable auto capturedValue = i;
    
    closures.add( () => capturedValue * capturedValue );
}
```

```
functions.forEach( (auto fn) => println( fn() ) );
```
