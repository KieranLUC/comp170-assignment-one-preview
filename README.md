
# Comp 170 Assignment One:  Basic Input and Output

## Due date: January 25, 2022, 6:00pm

## Be sure to complete all 4 parts for full credit!

### Step One - Fork the repository to your own GitHub space and clone your forked repository - 5 points

First, click the "Fork" button in the upper right-hand corner of the GitHub view.  This will 
create a **fork** of this repository in your personal GitHub space.

Second, clone your forked repository.  Do not clone the original repository!!  Clone the repository 
that you find in your personal space in GitHub.

### Step Two: Implement Hello World - 5 points

We will begin by writing a very simple program called **Hello World**.  This program simply prints "Hello World"
to the console.  As you continue your study of computer science you will encounter **Hello World** frequently.

Open your cloned codebase in IntelliJ, and navigate to the `main(String[] args)` method in
the file `App.java`, located at `src/main/java/comp170/App.java`.

Add one line of code to print "Hello World" to `System.out`:

```
    public static void main(String[] args) {
        // TODO - put your code here!!
        System.out.println("Hello World!"); // add this line!
    }
```

Now **run the program** and verify that you see "Hello World!" in the console output.

### Step Three: Greet the user by name - 10 points

Now we’d like to get some input from the user.  
Let’s start by having the user type their name into the console, and then printing a personalized hello message of, “Hello &lt;your name>!”.

To do this we can use Java’s Scanner class.  Let’s create a Scanner and store it in a variable named `scanner`:

```
import java.util.Scanner;
...
public static void main(String[] args) {
   // TODO - put your code here!!
   System.out.println("Hello World!");
   
   Scanner scanner = new Scanner(System.in);
}
```

Notice the first line, `import java.util.Scanner`.  That’s Java’s syntax for making some other Java programs 
available in our Java program, in this case a ***class*** called `Scanner` which is 
available from the `java.util` ***package***.  

Also notice that when we create a `Scanner`, we need to supply a stream for the scanner to read from.  
We want to read user input from the console, so we will create our scanner to read the default system input, 
which we access as `System.in`.  Notice how this corresponds to the `System.out` that we are printing to.  
`System.out` is the default system output stream, which we can view in the console.  

Run your program.  It should print “`Hello World!`”, as before.

Now let’s add some code to read something that the user will type into the console.  
Let’s start by asking the user to enter their name, and then reading what the user types:

```
public static void main(String[] args) {

   // TODO - put your code here!!
   System.out.println("Hello World!");
   
   Scanner scanner = new Scanner(System.in);

   System.out.print("Please type your name: ");
   String name = scanner.next();

   
}
```

Run the program again.  It should now ask you to type your name, and wait for you to hit **<Enter>** before printing “`Hello World!`”.  
Notice that we are now using two different print commands: `System.out.print(..)`, and `System.out.println(..)`.  
Look in the console output when you run your program.  Can you see what the difference is in what is printed by each command?

Let’s finish this first part of the assignment by printing our personalized message.  Let’s use our new tools to expand out print statement like this:

```
System.out.print("Hello");
System.out.print(" ");
System.out.print(name);
System.out.println("!");
```

Now run your program.  You should be greeted more personally now.  Notice that we are using the `System.out.print(..)` statement 
multiple times, followed by a single `System.out.println(..)` statement.  What if we could do all that in a single call 
to `System.out.println(..)`?

#### Discssion: Operators and Data Types

We can join string values together using an operation called _concatenation_.  If we have two strings, 
“foot”, and “ball”, and we _concatenate_ them, we will have “football”.  For string values in 
Java (variables of datatype  `java.util.String`), we express concatenation using the ‘+’ character:

```
String football = "foot" + "ball"; // "football"
```

Used this way, the `+` character is interpreted as a special type of character called, “operators”.  `+` is an operator that takes two arguments and returns the sum of them:

	(left hand side argument) + (right hand side argument) = (sum of the two arguments)

It makes sense to use the `+` character for this purpose.  I am “adding” two strings, and the `+` operator gives me a new string which is the concatenation of the two arguments.  

But what if I want to “add” two numbers?  In Java I will use the `+` operator in that case as well, and the result will be a new number which is the sum 
of the two arguments:

```
int eleven = 10 + 1; // 11, not "101"
```

Why does this usage of the `+` operator yield a value of datatype `int` rather than of datatype `String`?  
Answer: Because the arguments are of type `int`.  

Why does the `+` operator yield the sum of 10 and 1 rather than the concatenation of “10” and “1”?  
Answer: because the `+` operator is used to indicate addition, and addition of two numbers yields their sum.

Let’s use concatenation to replace our System.out.print statements:

```
System.out.println("Hello " + name + "!");
```

### Step Four: Compute the Average of Five Numbers entered by the User - 15 points

Let’s put all of these tools together and write code to do something meaningful.  
Add code to make your program do the following:

1. Ask the user to enter 5 numbers
2. Print the average of those five numbers

**Hints**: 
* Division is denoted with the `/` operator, and it yields a result of datatype `double`, not `int`!  
Experiment with the `/` operator and see how the results change.
* To get 5 numbers from the user, you can ask the user to enter a single number 5 times, storing
each number in a variable (`int numberOne`, `int numberTwo`, etc.)

### Deliverable (Total of 35 pts):

* Commit and push your code
* Raise a Pull Request
* Submit a link to your Pull Request in Sakai
