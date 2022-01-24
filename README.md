# Java Streams

From Oracle Certified Professional Java SE 8 Programmer Exam:<br>
A stream is a sequence of elements and we can perform sequential operations when we obtain a stream using the stream() method. Streams provide pipelining capability—you can filter, map, and search data. The most common source of stream is collection objects such as sets, maps, and lists, but the stream API can be used independent of the collections.

Link about this information:
* http://www.java2s.com/Tutorials/Java/Java_Stream/index.htm
* http://tutorials.jenkov.com/java-functional-programming/streams.html
* https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html

## Streams Objects

The streams are objects who contain bytes of data for further processing.

* Interface Stream\<T\>
* IntegerStream
* DoubleStream
* LongStream
* Stream\<T\>

## Operations

The operations which are operating on streams can be grouped in:
* source operation
* intermediate operation
* terminal operation

### Source Operations

These operation deliver the streams for furhter processing. As we can see in from the next list the stream can be returned by many objects through their methods:
  * Values
    * \<T\> Stream\<T\> of(T...values)
    * Stream.<T>builder()    
  * IntStream.range/rangeClosed
  * Empty streams
    * Stream.empty() 
  * Functions
    * \<T\> IStream\<T\> iterate(T  seed, UnaryOperator<T>  f)
    * \<T\> IStream\<T\> generate(Supplier<T> s)
    * java.util.Random.ints()/doubles()
  * Arrays
    * Arrays.stream()
  * Collections
    * Collection.stream()
  * String
    * chars()
    CharSequence, StringBuilder. StringBuffer
    Pattern.splitAsStream
  * Files
    * Files.lines(path)
    * Files.walk(dir)
  * Other sources

### Intermediate Operations

The operations who are modifing the stream or its items are known as intermediate operations. They are also lazy which means they are executed after the terminal operations after inner optimization.

  * distinct - Returns a stream consisting of the distinct elements by checking equals() method.
  * filter - Returns a stream that match the specified predicate.
  * flatMap - Produces a stream flattened.
  * limit - truncates a stream by number.
  * map - Performs one-to-one mapping on the stream
  * peek - Applies the action for debugging.
  * skip - Discards the first n elements and returns the remaining stream. If this stream contains fewer than requested, an empty stream is returned.
  * sorted - Sort a stream according to natural order or the specified Comparator. For an ordered stream, the sort is stable.

### Terminal Operations

The terminal operation is the last invoked operation in the method chain invocation. It eager operation means when exeuting it all other itermediate operations are executed after optimization.

  * allMatch - Returns true if all elements in the stream match the specified predicate, false otherwise. Returns true if the stream is empty.
  * anyMatch - Returns true if any element in the stream matches the specified predicate, false otherwise. Returns false if the stream is empty.
  * findAny - Returns any element from the stream. Returns an empty Optional object for an empty stream.
  * findFirst - Returns the first element of the stream. For an ordered stream, it returns the first element; for an unordered stream, it returns any element.
  * noneMatch - Returns true if no elements in the stream match the specified predicate, false otherwise. Returns true if the stream is empty.
  * forEach - Applies an action for each element in the stream.
  * reduce - Applies a reduction operation to computes a single value from the stream.
  * collect - Collects the stream as Set, List or Map.

## Stream Related Objects
 
 * Predicate
 * Collector
 * Supplier
 * Consumer
 * UnaryOperator
 * BiConsumer
 * Function
 * ToDoubleFunction
 * ToIntFunction
 * ToLongFunction
 * BinaryOperator
 * BiFunction 
 * IntFunction
