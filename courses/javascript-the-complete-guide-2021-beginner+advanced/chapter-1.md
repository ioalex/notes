# 1. Getting Started

## Table of Contents

- [1. Getting Started](#1-getting-started)
  - [Table of Contents](#table-of-contents)
  - [(1.1) What is JavaScript?](#11-what-is-javascript)
  - [(1.2) How do webpages work?](#12-how-do-webpages-work)
  - [(1.3) More on JavaScript](#13-more-on-javascript)
  - [(1.4) How is JavaScript executed?](#14-how-is-javascript-executed)
  - [(1.5) Dynamic? Weakly Typed? What does this mean?](#15-dynamic-weakly-typed-what-does-this-mean)
  - [(1.6) JavaScript Runs in a Host Environment](#16-javascript-runs-in-a-host-environment)
    - [(1.6.1) **Browser-side**](#161-browser-side)
    - [(1.6.2) **"Other" (e.g. Server-side)**](#162-other-eg-server-side)
  - [(1.7) JavaScript vs Java](#17-javascript-vs-java)
  - [(1.8) Client-side vs Server-side JavaScript](#18-client-side-vs-server-side-javascript)
  - [Client-side (Browser) vs Server-side (Node JS)](#client-side-browser-vs-server-side-node-js)
  - [(1.9) So... why should we l**earn client-side JavaScript first?**](#19-so-why-should-we-learn-client-side-javascript-first)

<br />

## (1.1) What is JavaScript?

JavaScript is a **dynamic**, **weakly typed** programming language which is **compiled at runtime**. It can be executed as part of a webpage in a browser or directly on any machine ("**host environment**").

JavaScript was created **to make webpages more dynamic** (e.g. change content on a page directly from inside the browser). Originally, it was called LiveScript but due to the popularity of Java, it was renamed to JavaScript.

JavaScript is totally **independent** from Java and has **nothing in common with Java**!

To gain a better understanding of JavaScript, we'll take a step back…

<br />

## (1.2) How do webpages work?

Users visits & interacts webpages using their machines, computers, laptops aka. Client (Browser) where they have a browser installed on it. They enter a URL or click a search result on Google and webpage gets loaded. To be precise, when you initially visit a website, a Request is sent to the Server (to a computer on the internet, where the HTML files are hosted). That Server then loads that webpage and sends it back to your browser, in a so-called Response.

Now let's say the user fills out a form and clicks a button to submit the form…

Again another Request is sent to the Server to send this form submission to the server, and the server will handle that incoming request, maybe store that ordered data in a database. And once it's done, it will reply back with a New Response - maybe the Order Confirmation page.

**JavaScript makes this all more "reactive."** It helps make a website more reactive and skip that second Request / Response flow and instead change the already loaded page and do something there.

![How Do Webpages Work?](<assets/chapter-1/original_(1).jpg>)

<br />

## (1.3) More on JavaScript

JavaScript:

- is a **dynamic**, **weakly-typed** programming language
- **Interpreted** "on the fly" compiled language
- "**Hosted** language": Runs in **different environments** (eg. In the browser)
- Most prominent use case: **Run code in a browser** (on a webpage)

<br />

## (1.4) How is JavaScript executed?

In order to have an effect on webpages, your JavaScript code is interpreted by JavaScript Engines eg. V8 (Chrome) and SpiderMonkey (Firefox) which are built-in to the browser.

These engines parse code (parse, read and understand your JS code), then **Compile it to Machine Code** on the fly which is faster to execute by the machine. Then, it **executes** that machine code and we have our effect on our webpage.

Modern engines have a lot of optimisation, they might start executing your uncompiled code and then compile the code whilst they're already executing it, to get started executing faster and then switch to the compiled code dynamically and so on.

JavaScript code execution always happens in one single thread on your operating system..

![How Is JavaScript Executed?](<assets/chapter-1/original_(2).jpg>)

<br />

## (1.5) Dynamic? Weakly Typed? What does this mean?

JavaScript:

- is a **dynamic**, **interpreted** Programming language

  - Not pre-compiled, instead parsed and compiled "on the fly" (e.g. in the browser)
  - Code evaluated and executed at runtime
  - Code can change at runtime (e.g. type of a variable)

- is a **weakly-typed** programming language
  - This means that when we work with data in JS, for example text, data or numbers, you don't have to tell JS that you're working with a text now or you're going to work with a number now, or that you want to work with text now
    - Data types are assumed (e.g. assigned to variables) automatically
    - Which relates to JS's dynamic nature where data types can also change from one line to another
  - You don't define that some variable has to hold a certain value (e.g. a number)
  - Data types are not set in stone but can change

<br />

## (1.6) JavaScript Runs in a Host Environment

So that means a JavaScript engine can be part or can be executed in different environments.

The most well known environment is the **browser**. Modern browsers have JavaScript built-in and they're therefore capable of executing JavaScript code. But you can also run JS in **other** environments.

For example, on the **Server-side**. So right on the computer, without having a browser in between, so not inside of a browser but simply execute code on your machine.

### (1.6.1) **Browser-side**

- JS was invented to create more dynamic websites by executing in the browser
- JS can manipulate HTML code, CSS, send background HTTP requests (some behind-the-scenes requests and fetch data) & much more
- JS cannot access the local filesystem, interact with the operating system etc.
  - This is for security reasons otherwise every webpage you visit would be able to read your file system, maybe delete files on your computer
  - In general, you could say it is running inside a sandbox

### (1.6.2) **"Other" (e.g. Server-side)**

- Google's JS engine (V8) was extracted to run JS anywhere (called Node JS)
- Node JS can be executed on any machine and is therefore often used to build web back-ends (server-side JS)
- Node JS can access the local filesystem, interact with the OS etc. **It cannot manipulate HTML and CSS - since it does not have access to the loaded webpage.**

<br />

## (1.7) JavaScript vs Java

![JavaScript Logo](assets/chapter-1/icons8-javascript-240.png)

![Java Logo](assets/chapter-1/icons8-java-240.png)

**Totally independent programming languages with different syntax and principles!**

JavaScript runs in the browser, whereas Java does not.

You can use Java on the server-side to render HTML dynamically there and send it back
to users. You can also use it in a non web development context but you cannot run it in the browser.

Different principles!

Java is strictly object oriented and strongly typed, you need to define what kind of data you need to store in a data container, whereas JavaScript is really flexible. You don't have to work with only objects there and is weakly typed.

JavaScript was named JS to "sound cool."

<br />

## (1.8) Client-side vs Server-side JavaScript

## Client-side (Browser) vs Server-side (Node JS)

| Client-side (Browser)                                                      | Server-side (Node JS)                                                                 |
| -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| The origin of JavaScript                                                   | Why not use JS outside of the browser? Allows for code & knowledge re-usage!          |
| Different browser vendors provide their own JS executable engines          | Extracted V8 engine to run JS anywhere                                                |
| Allows interaction with webpages and browser APIs (e.g. get user location) | Special non-browser APIs (e.g. to work with file system, incoming HTTP requests etc.) |

The syntax, concepts, core features etc. are exactly the same for client-side and server-side JavaScript!

<br />

## (1.9) So... why should we l**earn client-side JavaScript first?**

- It's JavaScript's origin
- There is no alternative to JavaScript in the browser
- Node JS uses the same syntax
- It's more fun to learn it - you see something on the page!

Next up...

[2. Language Basics, Base Syntax](./chapter-2.md)
