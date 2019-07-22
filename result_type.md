# The `Result` type

From [The Book](https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html#handling-potential-failure-with-the-result-type):

> The Result types are enumerations, often referred to as enums. An enumeration is a type that can have a fixed set of values, and those values are called the enum’s variants. Chapter 6 will cover enums in more detail.
> 
> For Result, the variants are Ok or Err. The Ok variant indicates the operation was successful, and inside Ok is the successfully generated value. The Err variant means the operation failed, and Err contains information about how or why the operation failed.
> 
> The purpose of these Result types is to encode error-handling information. Values of the Result type, like values of any type, have methods defined on them. An instance of io::Result has an expect method that you can call. If this instance of io::Result is an Err value, expect will cause the program to crash and display the message that you passed as an argument to expect. If the read_line method returns an Err, it would likely be the result of an error coming from the underlying operating system. If this instance of io::Result is an Ok value, expect will take the return value that Ok is holding and return just that value to you so you can use it. In this case, that value is the number of bytes in what the user entered into standard input.