```
import uva.random { DefaultRandom };
```

```
auto random = new DefaultRandom();

auto ary = 0..10.asArray();

auto thatElement = ary[random.next( ary.length )];

println( "I picked element ${thatElement}" );
```
