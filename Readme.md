## Functional Interface:-

- An interface which has only one abstract method is called as functional interface.
  This functional interface can have any number of default, static methods, but can contains only one
  abstract method.
  A functional interface can have methods of the Object class also.
  Functional Interface is also known as Single Abstract Method Interfaces or SAM Interfaces. It is a
  new feature in Java 8, which helps to achieve functional programming approach.

Some of the new functional interfaces introduced in java 8 to perform functional style of programming. these interfaces belongs to java.util.function package.

1. Predicate<T>
2. Consumer<T>
3. Supplier<T>
4. Function<T,R>

5. java.util.function.Predicate<T>:

- We can use predicate to do conditional check and it takes parameter and returns boolean result.
  This interface contains only one abstract method called:

```
{
public boolean test(T t);
}

Create an interface with Predicate name
{
public interface Predicate<T> {
boolean test(T t);
}

=> T denotes the input parameter type.

Predicate<Integer> p = (i) -> (i > -10) && (i < 10);
System.out.println(p.test(9));
```

2. java.util.function.Function<T,R>:
   - Function<T, R> is used to perform some operation & returns some result. Unlike Predicate<T> which returns only boolean, Function<T, R> can return any data type or value.

```
Typically Function internally it written as
{
interface Function<T,R> { T is method input parameter & R is return type
R apply(T t);
}

Function<String, Integer> f = s -> s.length();
System.out.println(f.apply("I am a java Developer"));
```

```
import java.util.function.Function;
public class Main {
public static void main(String[] args) {
Function<Integer,String> f = i -> "This is a number "+i;
System.out.println(f.apply(10));

        Function<String,Integer> f2 = s -> Integer.parseInt(s);
        System.out.println(f2.apply("200")+500);


        Function<String,Integer> f3 = Integer::parseInt;
        System.out.println(f3.apply("400")+200);

}
}
```

3. java.util.function.Consumer<T>:

- Consumer<T> is used when we have to provide some input parameter, perform certain operation, but don’t need to return anything. Moreover, we can use Consumer to consume object and perform certain operation.

```
interface Consumer<T> {
void accept(T t);
}

=> T denotes the input parameter type.

Consumer<String> c = s -> System.out.println(s);
c.accept("I consume data but don't return anything");
```

4. java.util.function.Supplier<T>:
   - Supplier<R> doesn’t take any input and it always returns some object. However, we use it when we need to get some value based on some operation like supply Random numbers, supply Random OTPs, supply Random Passwords etc. For example, below code denotes it :

```
interface Supplier<R>{ //here R is return type
R get();
}

Supplier<String> s = () -> "This is from Lambda Expression";
System.out.println(s.get());

Supplier<String> randomNumbers= () -> {
String randomNumber= "";
for (int i = 1; i <= 4; i++) {
randomNumber= randomNumber+ (int) (Math.random() \* 10);
}
return randomNumber;
};
System.out.println(randomNumbers.get());
System.out.println(randomNumbers.get());
System.out.println(randomNumbers.get());
```
