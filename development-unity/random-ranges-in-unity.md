# Random Ranges in Unity

* Unity 2020, probably all other versions also

In almost any game you create, you'll often need to generate random numbers. Unity includes a random number generator in the scripting API:

Random.Range

This method is overloaded, and you can call it by passing in either floats or integers for min and max values. Avoid bugs in your game by paying attention to the differences between the two overloads' behavior.

Using floats, Random.Range is inclusive of both min and max values Using integers, Random.Range is inclusive of min, but exclusive of max When using integers always remember this and adjust your max value if needed.

For example, if you want a random int between 1 and 10 (including 10 as a possible value) then:

```
int min = 0;
int max = 10;

int randomInteger = UnityEngine.Random.Range(min, max + 1);
```
