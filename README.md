# Collections and Streams #

## Tasks ##

1. Using Stream API write a method that returns a comma separated string based on a given list of integers. 
Each element should be preceded by the letter 'e' if the number is even, and preceded by the letter 'o' if the number is odd. 
For example, if the input list is (3,44), the output should be 'o3,e44'.
 
2. Using Stream API implement a method that produces the largest city per state. 

```
Map<String, City> getLargestCityPerState(Collection<City> cities) { } 
```
```
class City { 
	private String state; 
	private long population; 
}
``` 

3. Write a method `public static <T> Stream<T> zip(Stream<T> first, Stream<T> second)` that alternates elements from the streams first and second, 
stopping when one of them runs out of elements.

4. You have a class Book with fields (title, author, isbn). You have a List of books. 
You have `Map<String, Integer>` where key - author name and value - number of books that were written by this author in a list. 
You have to implement a mechanism when every change in the list immediatly reflect the map. 
For example there was a book by "Author1" added to the list. In this case value by key "Author1" have to increase by 1.