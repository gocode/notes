Generics

Collections

Anonymous class
	Implementation of an interface without specifing a name for the class
	It is used near to where it is declared
	Created using new keyword on interface

Lambda Expression
	Type is functional interface
	Easier way to write anonymous class
	Can be assigned to functional interface variables
	Not an object ie, no regular object is created when lambda expression is created
	Should not call equals(), toString() etc. on it
	Parameter types can be omitted
	Function paranthesis can be omitted when there is only one parameter
		Comparator c = (s1, s2) -> s1-s2
		Runnable r = () -> System.out.Println("Hello world")
	Method reference is a strictly equivalent syntax to lambda expressions

Functional Interface
	Interface with only one abstract method
	Methods form the parent Object class does not count
	For convinence @FunctionalInterface annotation can be used on the interface for compile time checking
	java.util.function has common functional interfaces
		Supplier
		Consumer, BiConsumer
		Predicate, BiPredicate
		Function, BiFunction
			Uinary Operator
			Binary Operator

Default method
	Method defined in interface
	Used to prevent breaking legacy code when new methods are added to existing interface	
	Static methods can also be added to interface
		public interface Iterable<T> {
			default void forEach(consumer<T> c) {
				for(T t: this) {
					consumer.accept(t)
				}
			}
		}
	
Stream
	Typed interface
	Parallizes and pipelines
	Does not hold data
	Its an object on which operations are defined
	Does not change (mutate) the data it processes
	All operations on stream that return a stram are lazy and are called intermidatory operations
	Terminal operations trigger processing of data
	A stream can have only one terminal operation
	Consume, Map, Filter and Reduce operations

Optional
	May not contain a value
	isPresent() returns true when value is present
	get() returns value
	orElse() can return given value when novalue is present
	orElseThrow() can be used to throw an exception when no value is present

Reflection


JDBC

JNDI