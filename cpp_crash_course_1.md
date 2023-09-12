Act as a C/C++ Linux Software Engineer and Tutor. 

You are on a special board to devise a quick crash course into “C++ development on linux” for Windows frontend HTML, CSS, JS, JQuery developers with 3 years of exp. They are aware of fundamental software subjects such as variables, arrays, functions, objects, loops, branching, memory, debugging, IDE etc. A big step ahead than complete novice.

Students are expected to have 3 lessons a week with tutor, 35 minutes each. Course must be 6 months long. This is meant to be a practical course that converts frontend/js people into practical junior C++ (Linux) software developers. Thus each lesson is expected to have 15 minutes of theory and 20 minutes practice of 1-n tasks with following the tutor. Stick to this format. 

Another part of this crash course is the "practice" part of the education. "Practice" is meant in the following context: As a software engineer a person is self obligated to devote 30 minutes a day to practice his main language (C++) by writing something from scratch, just to get it running and then throwing it away. By throwing away it is meant that he does not continue where he left off the next day during the 30 in "practice" time. If he did not finish the last time, he may start over or do another task. 

This “Practice” is not the main concert atm, but bear this in context, when developing the course, i.e. lessons have to be sufficiently straightforward to grant enough knowledge of coding to do at least 2 x 30 minutes of practice.

The goal is to eventually build C++ programs (executables, objects, static/shared libs) in linux initially using command line and then meson. But since lesson time is too limited, it is not possible to explain something in the first Week1.day1 that would be practical to code and to explain g++ compilation at the same time. To reduce the noise, additional info is that first 1.5 months students will be learning C++ in an automated build environment GUI with buttons such as Build and Run. Keep this in mind and at the start of the course, to focus only on writing code.

## Summary of Key Remarks, Requirements, and Constraints

### Environment & Tools:
- Students will use a pre-configured machine with Visual Studio Code and the GDB debugger set up.
- For the first 1.5 months, students will learn C++ in an automated build environment GUI with basic features like Build and Run.

### Language & Standards:
- Focus on C++17, avoiding a deep dive into the language's history or evolution.

### Teaching Approach:
- Emphasize practical aspects of C++ and not the object-oriented paradigm.
- Use the term "object" mostly in the context of the C++ standard, denoting something occupying memory space.
- Avoid early discussions on low-level memory management, stack, or heap. After 3 months

### Content & Curriculum:
- Prioritize practicality, eschewing overwhelming theoretical concepts or extensive historical context.
- Steer clear of a C-centric teaching approach.
- Libraries: XML, JSON, CSV for file content manipulation, argument parsing, and HTTP, Websockets for client/server communication.
- Begin with the structure of C++ programs and gradually transition to variables, data types, and algorithms.
- Early introduction of `std::vector` and `std::stack`. Highlight practical STL algorithms for `std::string`.

### Lesson Format:
- 15 minutes of theory followed by 15 minutes of practical coding.
- Each topic/point is to be presented in markdown format for easy git documentation.

### Post-lesson Activities:
- Dedicate 15-30 minutes for "practice" post each lesson.
- Encourage coding from scratch, testing the run, and not extending it the following day.

another key requirement is to write as simple language as possible, technical where required, otherwise simple plain english. This course is meant for people whose primary lang is not english.

**Goal:** Transform frontend developers into junior C++ (Linux) software developers in 8 months.

Below is an finished full details descrption of week1.day1 15min theory:

## Week1.Day1 Theory: Dive into C++ with Basic Data Types and STL Basics

---

### Basic Structure of a C++ Program (1 minute):

Every C++ program begins with the `main` function. This is where we put our instructions. At the end of `main`, we often see `return 0;`. We use this to check how our code works.

---

### Variables and Standard Data Types (7 minutes):

When we talk about data types, we focus on three main things: how big they are, what actions you can do with them, and what values they can hold.

#### Integers (`int`):

- **Size:** Ordinarily 4 bytes, though this might deviate depending on the platform.
- **Operations:** Basic arithmetic like addition, subtraction, multiplication, and more.
- **Values:** Typically spans from roughly -2 billion to 2 billion in many systems.
```cpp
int age = 30;
```

#### Floating-Point Numbers (`double`):

- **Size:** 8 bytes on most systems.
- **Operations:** Standard arithmetic operations with decimal precision.
- **Values:** Capable of holding expansive or minuscule numbers.
```cpp
double pi = 3.14;
```

#### Characters (`char`):

- **Size:** Generally 1 byte.
- **Operations:** Mainly comparisons and assignments.
- **Values:** Encompasses any ASCII character, from alphabets to symbols.
```cpp
char initial = 'A';
```

#### Strings (`string`):

- **Size:** Modulates with the content's length.
- **Operations:** Various, from appending and insertion to deletion and searching.
- **Values:** An amalgamation of characters.
```cpp
string greeting = "Hello, World!";
```

---

### Introduction to Containers: `vector` and `stack` (5 minutes):

C++ offers containers to help us store and manage groups of data. Let's explore two commonly used containers.

#### `vector`:
A `vector` is like a flexible list. It can change its size by adding or removing elements. It's more versatile than a regular array.

- **Creating and Adding**: Define a vector and add elements to it.

```cpp
vector<int> numbers = {1, 2, 3, 4, 5};
numbers.push_back(6);
```

- **Accessing Elements**: Use indices just like with arrays.

```cpp  
int firstNumber = numbers[0];
```

- **Iterating**: A `vector` provides methods like `begin()` and `end()` to help go through its elements.

```cpp
for(vector<int>::iterator it = numbers.begin(); it != numbers.end(); ++it) {
    cout << *it << " ";
}
```

#### `stack`:
A `stack` follows a Last-In-First-Out (LIFO) system. This means the most recent item you add is the first one you take out.

- **Adding and Removing**: You can use `push()` to add and `pop()` to remove items.

```cpp
std::stack<std::string> books;
books.push("Effective C++");
books.pop();
```

---

### The Power of the STL Algorithms with vector (7 minutes):

The **Standard Template Library (STL)** in C++ has tools that make working with `vector` efficient and easy.

1. **Key Algorithms with `vector`:**

   - **Searching with `find`** 
     
     Quickly check if an element is in the vector. It gives a pointer to the element if it's there, or a pointer to the vector's end if it's not.

```cpp
vector<int> numbers = {1, 2, 3, 4, 5};
auto it = find(numbers.begin(), numbers.end(), 3);
```

   - **Sorting with `sort`**
     
     Put the vector's elements in order, either from smallest to largest or based on rules you give.

```cpp
sort(numbers.begin(), numbers.end());
```

   - **Flipping order with `reverse`**
     
     Make the last element first, the second last second, and so on.

```cpp
reverse(numbers.begin(), numbers.end());
```

   - **Counting with `count`**
     
     See how many times an element is in the vector.

```cpp
int twos = count(numbers.begin(), numbers.end(), 2);
```

   - **Changing elements with `replace`**
     
     Swap one value for another wherever it appears in the vector.

```cpp
replace(numbers.begin(), numbers.end(), 2, 7);
```

2. **Using Loops with `vector`:**

   A simple way to go through a `vector` is with a range-based `for` loop:

```cpp
for(const int& num : numbers) {
    cout << num << " ";
}
```

END on Week1.day1

Notice how narrowly focused it is on multiple broad topics. Every lesson needs to be like this.

First step is to provide a list of each day and one line of topics that will be covered for all the 24 weeks. Like:

Week1.day.: Standard data types: int, double, char, string. Containers: vector, stack. STL algorithms with vector: fnd, sort, reverse, count, replace, range loop
