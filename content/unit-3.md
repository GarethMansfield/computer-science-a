# Boolean Expressions

In [Unit 1](/unit-1) we introduced arithmetic operators that manipulate numbers. There are another type of operators that allow us to compare numbers, these are called *relational operators*.

## Relational Operators

For example, we can check if numbers are equal, or for which one is larger. Here are the following relational operators:
 - `==` is equality. It checks if two numbers are equal. For example, `2 == 2` returns `true` while `2 == 5` returns false.
 - `!=` is not equality. It returns the opposite of what `==` returns.
 - `>` is greater than. `a > b` returns whether `a` is greater than `b`
 - `<` is less than.
 - `>=` is greater than or equal to.
 - `<=` is less than or equal to.
 <div class="callout callout--error">
     <p><strong>Equality and Assignment</strong></p>
     <p>It is easy to confuse = and ==. One is the assignment (that assigns a value) operator, the other is equality. Mixing the two will not work. Keep in mind that if you are <b>checking</b> for equality, use the ==. </p>
 </div>

Like arithmetic operators, you place numbers on the two sides:
```java
a == b
```

which would return a `boolean` value which you can use elsewhere.

<div class="callout callout--warning">
    <p><strong>Comparing Objects</strong></p>
    <p>While you can use these operators to compare primitive variables, be careful when using this with objects. Equality will only return <code>true</code> if two object references are the same (say, <code>kitty</code> and <code>kittyTwo</code>). Even if they have the same attributes, it will return <code>false</code> if the objects are different (different 'boxes'). You can instead check for each attribute/object variable individually. </p>
</div>


# `if` Statements and Control Flow

(This section relies on an object introduced earlier called `kitty` which is of class `Cat`. `kitty` has a `happyBirthday()` method which increments `kitty`'s age, and an `eat()` method which adds to `kitty`'s weight.)

*Control flow* is referring to how our program executes and which parts of the code to run. For example, if it is `kitty` the `Cat`'s birthday, we might want to wish `kitty` a happy birthday, otherwise, we shouldn't. This is best achieved through an `if` statement.
```java
boolean isBirthday = true;
if (isBirthday) {
    kitty.happyBirthday()
}
```
Here, we are checking for the boolean `isBirthday`, which is within parentheses after the `if` statement. If it is true, the code between the curly braces executes, otherwise, it gets skipped over.

Sometimes, we might want to do something if the condition is not true. Here, we can use an `else` statement. Let's say we still want `kitty` to eat even it it isn't `kitty`'s birthday.
```java
if (isBirthday) {
    kitty.happyBirthday()
} else {
    kitty.eat(1.0)
}
```

It is also possible to check for multiple conditions. For example, if `kitty` is is young, we might want to feed `kitty` less food. While putting `if` statements within `if` statements is possible, it is not recommended. This causes *nested* if statements.

A better way to achieve this is to use an `else if` statement (which does a different thing for each condition met).

Let's say `kitty` should have half a pound of food if she is less than 2 years old, and a pound of food if she is less than 4, and 1.5 pounds of food otherwise. Here's how we would do that with an `else-if` statement.
```java
int age = kitty.getAge() // Gets kitty's age.
if (age < 2) {
    kitty.eat(0.5)
} else if (age < 4) {
    kitty.eat(1)
} else {
    kitty.eat(2)
}
```
`else if` statements can be chained to check for multiple conditions. This allows us to avoid nesting `if` statements.

# Summary
In this unit:
 - Relational operators (comparing primitive variables).
 - `if` statements.
    - `else` and `else-if` statements.
