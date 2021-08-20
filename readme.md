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
        <ol>
            <a href="#chapter-3-1">
                <li>Small & Short</li>
            </a>
            <a href="#chapter-3-2">
                <li>Do Just One Thing</li>
            </a>
            <a href="#chapter-3-3">
                <li>One Level Abstraction</li>
            </a>
            <a href="#chapter-3-4">
                <li>Switch Statement</li>
            </a>
            <a href="#chapter-3-5">
                <li>Descriptive Name</li>
            </a>
            <a href="#chapter-3-6">
                <li>Function Argument</li>
            </a>
            <a href="#chapter-3-7">
                <li>Have No Side Effect</li>
            </a>
            <a href="#chapter-3-8">
                <li>Output Arguments</li>
            </a>
            <a href="#chapter-3-9">
                <li>Command Query Separation</li>
            </a>
            <a href="#chapter-3-10">
                <li>Prefers Exception to Error Code</li>
            </a>
            <a href="#chapter-3-11">
                <li>Don't Repeat Yourself</li>
            </a>
        </ol>
    </li>
    <li>
        <a href="#chapter-4">Chapter 4 - Comments</a>
    </li>
</ul>

<hr>

<details open>
<summary>Chapter 1 - Clean Code</summary>
    
<h2 id="chapter-1" style="text-align:center">
    Chapter 1 - Clean Code
</h2> 

Creating a clean code is important, it might help you to add more features in the future easily. Have you ever been slowed down by someone else's messy code? That's why writing a good code is important. So, what is clean code? 

Clean Code ...
<ul>
    <li>is elegant and efficient</li>
    <li>is simple and direct</li>
    <li>has meaningful names and is self-documenting</li>
    <li>is pleasing to read, and reads like well-written prose</li>
    <li>does one thing well</li>
    <li>does not tempt the developer to write bad code - on the flip side, when others change bad code, they tend to make it worse</li>
    <li>never hides the designer's intent but is rather full of crisp abstractions and straightforward lines of control</li>
    <li>is when each method you read turns out to be pretty much what you expected (Least Astonishment Principle)</li>
    <li>can be read, and enhanced by a developer other than its original author </li>
    <li>has unit and acceptance tests</li>
    <li>is minimal (KISS and YAGNI)</li>
    <li>does not repeat itself (DRY Principle)</li>
</ul>
</details>

<hr>

<details open>
<summary>Chapter 3 - Function</summary>

<h2 id="chapter-3" style="text-align:center">
    Chapter 3 - Function
</h2>

These are some several rules, to make your function cleaner:

1. <span id="chapter-3-1">A function should be **small and short**</span>
    <br/>

    Make the function not so big so the it fits into your screen, so you can read all the function does without scrolling vertically or horizontally. This approach will make you grasp the purpose of the function in the first place from the first line into the last line.
    <br/>
    
    It should be readable from top to bottom as a paraghraph

➖➖➖

2. <span id="chapter-3-2">A function should **do just one thing**</span>
    <br>

    <p style="color: green; font-weight: 500">
        Function should only do one thing, They should do it well, and they should do it only
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

3. <span id="chapter-3-3">Use one **level of abstraction**</span>
    <br/>

    Make sure that your function has only one level of abstraction. From my understanding, your function shouldn't has a nested condition since reading a nested is will confused you. If you have a nested condition within your function, you better break the function into smaller part;
    <br />

    ```
    // ❌ Avoid a function which has nesterd condition
    createUser(user) {
        let shouldDoAMilitaryWork;
        let isSmoking;
        
            if(user.gender === GENDER.MAN) {
                if(user.age > 17 && user.age < 40) {
                    shouldDoAMilitaryWork = true;
                } else {
                    shouldDoAMilitaryWork = false;
                }

                if(user.isSmoking) {
                    isSmoking = false;
                } else {
                    if(user.isHealty) {
                        ...
                    } else {
                        ...
                    }
                }
            } else {
                ...
            }
    }

    // ✅ Do like this instead

    createUser(user) {
        const shouldDoAMilitaryWork = isShouldDoAMilitaryWork(user);
        const isSmoking = isUserSmoking(user)
    }

    isShouldDoAMilitaryWork(user) { ... }
    isUserSmoking(user) { ... }

    ```

    

➖➖➖

4. <span id="chapter-3-4">Avoid **switch statement**</span>
    <br/>

    //TODO: Need to read once more to fully understand this one
    Use polymorphism and bury the switch statement in an abstract factory.

➖➖➖

5. <span id="chapter-3-5">Use **descriptive name**</span>
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

➖➖➖

6. <span id="chapter-3-6">Function Argument</span>
    <br/>

    Some point you should have to consider when creating a function:
    * Better to use no argument
    * You can add one argument or two. But better to avoid three or more argument
    * If you really need to pass three or more argument, consider to pass a map/object
    * Avoid flag argument. Avoid a flag which contains boolean value 
    <br/> 

    ```
    ❌ function saveUser(name, address, age, gender) {...}
    ✅ function saveUser(user) {...}
    
    ❌ function saveUser(isFromEdit) {...}
    ✅ better to make seperate scenario that will invoke same function instead of avoid flag 
    ```

➖➖➖

7. <span id="chapter-3-7">Have **No Side Effect**</span>
    <br/>

    Your function should has no side effect, it should only do what the name suggest. **Don't do anything else**
    <br/>

    ```
    function isUserValid(username, password) {
        const isValid = // some operation to check user within databse

        if (isValid) {
            createSession(x); // ❌ this cause a side effect
        }
        return isValid;
    }
    ```

➖➖➖

8. <span id="chapter-3-8">Output Arguments</span>
    <br/>

    Avoid setting an output as argument to a function, it ambigous and hard to add changes in the future. Do something like this instead:
    <br/>

    ```
    ❌ activateJob(job) { ... }
    ✅ job.activate() { ... }
    ```

➖➖➖

9. <span id="chapter-3-9">Command Query Separation</span>
    <br/>

    Your function should do a command or a query. **But not both**
    <br/>

    ```
    ❌ boolean setRole() { ... }
    ✅ void setRole() { ... }
    ```

➖➖➖

10. <span id="chapter-3-10">Prefers Exception to Error Code</span>
    <br/>

    Prepare an **exception block** to catch an error, rather than to leave the error code as is. It is a best practice to catch error and handling it in certain way.


    <br/>

    ```
    transformUserToStaffFormat () { 
        {}.map() // ❌ Will caused error with no handler
    }
    
    ✅ transformUserToStaffFormat () { 
        try {
            {}.map()
        } catch (error) {
            handleErrro(error)
        }
    }
    ```

➖➖➖

11. <span id="chapter-3-11">Don't Repeat Yourself</span>
    <br/>

    When you write a function, it should minimize or even remove repeated code or purpose since a function should represent one purpose. And also, please noted that when you are wiriting function you should take a notice that you shouldn't do repeated code 

</details>

<hr />

<details open>
<summary>Chapter 4 - Comment</summary>

<h2 id="chapter-4" style="text-align:center">
    Chapter 4 - Comments
</h2>

Generally, **comments is bad**. You should avoid comment in your code as possible. From [Chapter 2 - Naming](#chapter-2) and [Chapter 3 - Function](#chapter-3) you should already aware that your code should self explanatory, it should express the purpose. So avoid using comment in your code.

But there is some exception to white comment:

* TODO comment
* Legal comment
* The necessary comment in case the code couldn't speak it self (<i>ex: regex pattern</i>)
* Clarification and Amplification comment

Clarification and amplication comment example:
```
const mapResponseToForm = () => {
    ... 

    // This is the best way so far to avoid to prevent race condition. Don't remove
    setTimeOut(() => {
        setFormTypeBasedOnProjectCategory(response.project_category);
    }, 1000)
}


// Avoid using this function unless you really need to kill entire app
const killProcess() {
    ...
}

```
<br/>

In conclusion,
<span style="color: red; font-size: 25px">Don't leave a comment in your code!!!</span>
</details>


<hr />
