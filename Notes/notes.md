# Variables and Data Types

In Java and many other programming languages, the way computers store information is by way of **variables**. Variables are spots in computer memory assigned to hold onto particular information for use by the program.

There are different types of information that might need to be stored (i.e. numbers versus letters), and so each variable is assigned a **data type** so the computer knows what type of information is being stored there (and therefore how much memory is needed to hold it).

We are going to start with the most basic data types, referred to as the **primitive data types** that Java uses. They are called primitive due to their direct and simple nature, where the data is smaller and stored exactly at the point in memory that is being used by the variable.

Advanced Note: This will be contrasted at a later date with **referential data types**, which store more complex information and instead of storing the information directly in the memory tied to the variable, stores a reference in the memory tied to the variable to a different location in memory where the larger and more complex information is stored.

The basic types in Java cover 3 main types of information:
- Numbers
- True/False
- Letters (characters)

The AP Computer Science A course looks specifically at two types of numbers and the True/False type (called Boolean). See the end of these notes for brief information about the other types not covered in-depth by this course.

---

## Numbers

The largest category of information we will cover is numbers. To start, we can make a large distinction between two types of numbers: whole numbers and fractional/decimal numbers.

### Integers

When we say whole numbers, we mostly refer to the idea of **integers**, meaning positive or negative whole numbers. In Java, we will be referring to integers as `int`-type values. This specifically covers the range of values from `-2,147,483,648` to `2,147,483,647`. Obviously this doesn't store numbers that are very large (for example, the population of the Earth is over `8,000,000,000`), but covers enough values that we can accomplish many tasks within this range.

Advanced Note: Integers use 4 bytes (32 bits) of storage in Java, with the leading bit being used for the sign of the number (positive or negative), and the remaining 31 bits making up the number (note that 2^31 is 2,147,483,648).

Let's start with this code sample from `NotesInt1.java`:

```java
int wholeNumberVariable = 10;
```

Much of this line of code goes through the process of **declaring** and **initializing** a variable, which we will be doing in detail in the next section, but for that sake of this section, we can hone in a couple of specific details. The most important is the first piece of the line, which is `int`. This portion tells the computer what type of information the variable we are about to create is supposed to hold (and therefore how much memory to allocate for it). The next piece `wholeNumberVariable` is a variable name, which is essentially a codeword we would use throughout the program to refer to the variable when needed. Finally at the end we have `= 10`, which assigns a value to the new variable to be stored in its newly-assigned memory. It is critical that the value being assigned (in this case `10`), matches the type for the variable: in this case we are all set, as `10` is an `int`-type value.

An important side-note here is the yellow-highlighting of the `NotesInt1.java` file, which indicates a **warning**. A warning is an issue that the computer is foreseeing with the program that is not enough of a problem to prevent you from running the program, but it think is especially odd or inefficient. In this case, we are getting a warning in the file since we are going through the effort of creating a variable and then not using it do anything. This won't prevent us from running the program (not that it does much), but the computer knows that this is a waste of memory and is calling it out to us.

### Floating-Point Numbers

With whole numbers out of the way, we have the much more common types of numbers in the real-world: fractional or decimal numbers. Java and most programming languages use a system called **floating-point numbers** to store these kinds of more complicated numbers. The main data type we are interested in here is called **double-precision floating-point numbers**, or for the sake of our programming, the `double` type.

The `double` type can store very large numbers (much bigger than integers), with up to 15 decimal digits. The biggest downside that comes with this data type is precision. Due to the nature of storing information so much more complicated than whole numbers, these only end up being a very close approximation of precise numbers. That being said, it is an incredibly close approximation, so much so that we very rarely worry about its accuracy.

Advanced Note: Double-precision floating-point numbers use 8 bytes (64 bits) of storage in Java, with the leading bit being used for the sign of the number (positive or negative), the next 11 bits being used for an exponent (2^11 is 2,048, so the exponent can range from -1,023 to 1,024), and the final 52 bits used to store the number in a form of scientific notation.

Let's look at this code sample from `NotesDouble1.java`:

```java
double decimalNumberVariable = -3.957;
```

Just like before we want to hone in on just two primary pieces of this. First of all, the line starting with `double` tells the program what kind of information the `decimalNumberVariable` is going to store. Second of all, its important that the value being assigned (in this case `-3.957`), matches the type for the variable: in this case we are all set, as `-3.957` is a `double`-type value.

---

## Booleans

The final primitive data type we will cover in this AP course is the `boolean` type. A **boolean** is a single binary digit, or bit. Binary uses the values `1` and `0`, where we usually refer to `1` as `true`, and `0` as `false`. A `boolean` in Java is the value `true` or `false`, exactly as written.

Let's look at this code sample from `NotesBoolean1.java`:

```java
boolean booleanVariable = true;
```

The structure of this is much the same as the previous examples. The important thing here is that `true` is written in all lowercase. You can see the unique coloring of it, indicating it successfully recognizes it as a boolean value.

Advanced Note: While booleans do not hold much information, they are extremely space-efficient as they only use a single bit of space.

---

## `final` Keyword

When we don't want a variable's value to change after we create it, we use the keyword `final` at the beginning of the declaration. 

Let's look at this code sample from `NotesFinal1.java`:

```java
final int wholeNumberVariable = 5;
```

Notice that after the `final` keyword, the declaration and assignment of the variable is otherwise unchanged from our previous example!

With this, the variable `wholeNumberVariable` won't be able to be changed throughout the program, ensuring some level of consistency with whatever we need to do with it.

---

## Final Notes

Taking our very first example from `NotesInt1.java`, the whole file looks like this:

```java
public class NotesInt1{
    public static void main (String[] args){
        int wholeNumberVariable = 10;
    }
}
```

We only honed in on the middle line with our variable initially, but every piece of this file is important to the program running and doing what we want. Taking a look at our second example from `NotesDouble1.java`, that whole file looks like this:

```java
public class NotesDouble1{
    public static void main (String[] args){
        double decimalNumberVariable = -3.957;
    }
}
```

Comparing the first two lines of code from both files should feel extremely similar, with only a slight variation. All of our Java files for the foreseeable future will have this structure. The first line is `public class NameOfFileHere{`, where you'll notice that in both examples, it utilizes the name of the file without the `.java` extension. The second line is identical in both cases as `public static void main (String[] args){`.

Throughout the year we will end up unpacking these lines and better understand how they work to better use them to our advantage. For the time being though, we will let Visual Studio Code autofill those lines when we create a Java file and understand that it's on the third line where we put our code using things like our variable statements.

---

## Assignment

Now that you have gone through the notes for this section, you can check out the `assignment.md` and `Assignment.java` files to try a short assignment using this material.

---

## Advanced Notes - Other Primitive Types

Here is some basic information about other whole number types:
- `byte` - takes up a byte (8 bits) of memory. First bit is used for sign and the other 7 bits are used for value. Can store -128 to 127.
- `short` - takes up 2 bytes (16 bits) of memory. First bit is used for sign and the other 15 bits are used for value. Can store -32,768 to 32,767.
- `long` - takes up 8 bytes (64 bits) of memory. First bit is used for sign and the other 63 bits are used for value. Can store -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.

The other floating-point number type is a single-precision floating-point number, which is just referred to as `float` and can safely store 6 to 7 decimal digits. It takes up 4 bytes (32 bits) of memory, with the leading bit being used for the sign of the number (positive or negative), the next 8 bits being used for an exponent (2^8 is 256, so the exponent can range from -127 to 128), and the final 23 bits used to store the number in a form of scientific notation.

The final primitive type in Java is the `char` type, which is short for **character**. It stores a single piece of text, often in the form of something like a letter. It takes up 2 bytes (16 bits) of memory, where the bits represent an integer that is tied to particular characters via the American Standard Code for Information Interchange (ASCII) protocol. In this protocol, for example, the number 65 corresponds to the character `A`, 66 to `B`, etc. For more information on ASCII codes, look [here](https://en.wikipedia.org/wiki/ASCII).