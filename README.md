# Realization of lists (IndexedList and LinkedList) #

## Structure ##

| interfaces   | abstractClasses |    MyLists    |  	              |
|    :---:     |      :---:      |     ---:      |        ---: 	      |
| MyCollection | MyAbstractList  | MyIndexedList | RealizationOfLists |
| MyList       | 	         | MyLinkedList  |		      |
| MyQueue      |		 |		 |	              |
| MyDeque      |		 |		 |	              |

These lists are generalized.

* **IndexedList** is a resizable-array implementation of the *List* interface. Implements
  the next list operations:
	* void add(int index, T elem);
	* void add(T elem);
	* void ensureCapacity(int min capacity);
	* int size();
	* T get(int index);
	* T set(int index, T elem);
	* T remove (int index);
	* void showList().

* **LinkedList** is a doubly-linked list implementation of the *List* and *Deque* interfaces.  
  Implements the next list operations:
	* void addFirst(T elem);
	* void add(T elem);
	* void add(int index, T elem);
	* T removeFirst();
	* T removeLast();
	* T remove(int index);
	* void set(int index, T elem);
	* T getFirst();
	* T getLast();
	* T get(int index);
	* void showList().
