
```
bool isFizz(int n) => n % 3 == 0;

bool isBuzz(int n) => n % 5 == 0;

bool isFizzBuzz(int n) => isFizz( n ) && isBuzz( n );

for ( int i in 1...100 ) {
    if ( isFizzBuzz( i ) ) {
        println( "FizzBuzz" );
    } else if ( isFizz( i ) ) {
        println( "Fizz" );
    } else if ( isBuzz( i ) ) {
        println( "Buzz" );
    } else {
        println( i );
    }
}
```
