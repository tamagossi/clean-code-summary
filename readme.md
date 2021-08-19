<div style="text-align: center; margin-bottom: 20px">
    <img src="https://images-na.ssl-images-amazon.com/images/I/51b7XbfMIIL.jpg" height="600"/>
</div>

Greetings :wave:::wave:::wave::,

This is the summary of :book:&nbsp; Clean Code: A Handbook of Agile Software Craftsmanship by Robert C. Martin&nbsp;:book:. 
I am trying to write this summary to strengthen my understanding of this book and try to implement Feynman Technique.

I hope I can make the sentence as simple as easy to understand for non-native English speakers (like me), so feel free to contribute, comment, and pull requests are a huge welcome :grin:

 
:warning: If you think that this repo should not be public caused by copyright infringement. Feel free to DM me on any platform I have. :warning:
___


<div style="text-align:center">
    <h1>Clean Code Summary</h1>
</div>


<h3 style="margin-top: 30px">Table of Contents</h3>

<ul>
    <li>
        <a href="#chapter-1">Chapter 1 - Clean Code</a>
    </li>
    <li>
        <a href="#chapter-3">Chapter 3 - Function</a>
    </li>
</ul>

<hr>

<h2 id="chapter-1" style="text-align:center">
    Chapter 1 - Clean Code
</h2>

Creating a clean code is important, it might help you to add more features in the future easily. Have you ever been slowed down by someone else's messy code? That's why writing a good code is important. So, what is clean code? 

Clean Code ...
* is elegant and efficient
* is simple and direct
* has meaningful names and is self-documenting
* is pleasing to read, and reads like well-written prose
* does one thing well
* does not tempt the developer to write bad code - on the flip side, when others change bad code, they tend to make it worse
* never hides the designer's intent but is rather full of crisp abstractions and straightforward lines of control
* is when each method you read turns out to be pretty much what you expected (Least Astonishment Principle)
* can be read, and enhanced by a developer other than its original author 
* has unit and acceptance tests
* is minimal (KISS and YAGNI)
* does not repeat itself (DRY Principle)

<hr>

<h2 id="chapter-3" style="text-align:center">
    Chapter 3 - Function
</h2>

These are some several rules, to make your function cleaner:

1. A function should be **small and short**
   <br/>

    Make the function not so big so the it fits into your screen, so you can read all the function does without scrolling vertically or horizontally. This approach will make you grasp the purpose of the function in the first place from the first line into the last line.
    <br/>
    
    It should be readable from top to bottom as a paraghraph

➖➖➖

2. A function should **do just one thing**
    <br>

    <p style="color: green; font-weight: 500">
        Function should only do one thing, They should do it well, and they should do it only**
    </p>
    <br/>

    Function should be only do the `verb` that the function name suggest. If you can still extract a function from the function, so it is not small enoung and do more than one thing.
    <br/>

    ```
    ❌ function order(int id, boolean clearCart, boolean flushOrderSession) {...}

    ✅ function order(int id) {...}
    ✅ function clearCart(int id) {...}
    ✅ function flushOrderSession(int id) {...}
    ```
➖➖➖

3. Avoid **switch statement**
   <br/>

    //TODO: Need to add more explanation on this one
    Use polymorphism and bury the switch statement in an abstract factory.

➖➖➖

4. Use **descriptive name**
   <br/>

    The name of the function should be clear, it suggest one thing. And from the name of the function the reader should have a clue what does the function is doing.
    <br/>

    Usually the  function is in `verb` form. Since the function is will doing something, but sometime the function name also could be in question format. It is okay to make a long function name, as long as the is no shorter way to describe what does the function is doing
    <br/> 

    ```
    ❌ function onHandleChange() {...} // Not describing what does the function do

    ✅ function setUserName(String name) {...}
    ✅ function isUserActive() {...}
    ```
<br/>
