# 2 minute introduction to RX

출처 : https://medium.com/@andrestaltz/2-minute-introduction-to-rx-24c8ca793877#.uaezyoygv

* Think of it as an asynchronous immutable array.
* Event "application started", event "API response arrived", event "keyboard key pressed", event "invalidateLayout()", event "device slept", etc.
* Virtually anything can be a stream of events. It's just a matter of composing and combining them properly.

You know arrays? Of course you do. Here is one:
```
[ 14, 9, 5, 2, 10, 13, 4 ]
```
If I would tell you this is an immutable array and you need to take away all the odd numbers, how would you do it? This is a popular way:
```
[ 14, 9, 5, 2, 10, 13, 4 ]
filter( (x) -> x % 2 == 0 )
[ 14, 2, 10, 4 ]
```
