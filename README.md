
The core concept to understand to be good at programming is the called the development cycle.

The cycle has a goal. For examples: You could have an intended change in functionality in the software you are creating, or perhaps there is some information that you want to learn.

The cycle usually looks like this:
1) you gather information. This involves reading code and documentation. This might involve asking someone a question.
2) you make a hypothesis about how you can achieve your goal. This step can be done with the eyes shut.
3) you write and run tests to see if your hypothesis is true. If it is wrong, you start back at step 1. If it is right, then you are done, you have achieved the goal.

(How good you are as a programmer) = 1/(how long it takes you to complete an average development cycle.)

Implementing a feature will take a certain number of cycles N, in order to gather all the information needed to achieve the goal. If you can do each cycle in 1/2 the time, then you will achieve your goal in about half the time.

Some programmer ask themselves, "What could I learn to most improve my programming skills?".
You should look at your development cycle. Identify what is called the "bottleneck" of your develpment cycle. This is the step that is taking up the most time. Find ways to depend less on this step, or find ways to do it faster.

Getting better at any aspect of programming besides your bottle-neck a waste of your time. You wont see any improvement in your ability to program.

How fast is fast enough?
Somewhere between 5 and 10 seconds seems to be the ideal development cycle for the human brain. We are an animal, it is hard for us to remember much. A fast cycle like this puts more effort on the computer, and less on the human.
As programming tools improve, the development cycle has been getting faster. Maybe in 20 years the ideal development cycle will be less than 1 second.
It is not always possible to go so fast. Some problems are inherently slow. 
If you want to win, then you need to be faster than your competition.

Here are some common bottlenecks in the development cycle:
1) wasting too much time looking up the same things in documentation.
* implement helper functions with short memorable names, so you don't have to look at documentation so much.
* print statements can often be a faster alternative.
2) using a mouse.
* learn better programming tools so you don't touch the mouse.
3) Testing.
* write tiny tests that take < 1/2 a second, and catch almost all errors for the feature you are building.
* if you identify that a function is the bottle-neck of the test, preventing the test from running in < 1/2 a second, then optimize that function to be faster.
* On every iteration of the development cycle you should have more information, which means you need fewer tests. If the first 2 iterations take a minute, but the next 20 iterations take 5 seconds each, then your average development cycle is only 11 seconds which is very good.
- Think of this as a binary search. The first test cuts the code in half, and you know which half has the bug. The second test cuts the half into 2 quarters, so now you know which quarter of the code the bug is in.
4) Maintaining type information.
* compile-time type checking is good for a final product, to remove lots of bugs.
* but it is bad for a work in progress, because it takes longer to modify the code, so it slows the development cycle.
5) spaghetti-code. If the bottleneck of your development cycle is in understanding why control flow is moving the way it does.
* break the problem into sub-goals. Instead of solving it directly, first make a language which would be better for expressing the solution to the problem. Then use this language to solve the problem. When a problem is being solved from the right layer of abstraction, then you can do the development cycle faster because you spend less time modifying the code in each cycle.
- using domain specific languages this way also improves testing. Tests that run at a lower layer of abstraction are faster. The first development cycles will be at the highest layer of abstraction, and you will move towards the lower layers with each cycle.
6) typing can be the bottle-neck.
* looking down at your hands can be the bottle-neck.
- learn to type without looking at your hands.
* Find ways to type less:
- Use a tool like emacs that can display multiple files at a time, and copy paste between them, all without using a mouse.
- Use programmable editors that can do typing for you.
- Use a language that doesn't require so much typing.
7) perfectionism
* If you try to do everything with the optimal algorithm, it would take too long. Leave a note estimating how slow it is. Only improve it if it becomes the bottle-neck of your development cycle, or you have tests proving that it is too slow.
8) Not being able to understand what a function is doing at a glance.
* names should be short, and also they should descibe what they do accurately.
* mutable variables make it take longer to read code, you have to look at every line of a function to know the values stored in variables on the last line. So if you use mutability, the number of steps your brain needs to do to understand a function = (number of lines) * (number of variables).
With immutable variables you only have to look at the one line where the variables was instantiated. So the number of steps your brain needs to do to understand a function = (number of variables).
- if you must use mutable variables, you can partially get rid of their cost by using very short functions.
* In many cases your code can be more easily understood if you make it functionally pure. So the output only depends on the inputs, and there is no hidden state.
* Make sure you are using a text-editor that colorizes the words.

Besides making it fast, we also want the develpment cycle to be efficient. We want to accomplish as much as possible with each cycle.
If you run a cycle and don't learn anything new, and haven't implemented your goal feature, then this is a waste.
If 1/2 of your develpment cycles are wasted, this is about as bad as if your development cycle takes twice as long.

Here are common ways programmers waste development cycles:
1) writing unused features
* Take more time to think before you program. Only write something if you are certain that you will need it. This determines the order in which things get written. First write the thing that you have the most confidence in how it will look.
2) not realizing when a non-deterministic bug occurs, like a race condition. These types of bugs can hide themselves from your tests randomly, so it is easy to superstitiously attribute them to unrelated things. The human brain is made to see patterns, and we are so good at it, we see them when there are none.
* If something impossible seems to have happened, then check for non-determinism by running the test a few times in a row.
* If you use parallelism, you need to carefully look at the processes to see if there is any race condition. Write the code so that it is obvious that there are no race conditions. I recommend using message-passing style concurrency for a first-draft, because it is easy to edit it and keep your development cycle short.
* be careful when using non-deterministic features, avoid them when possible. Wrap them up in more code to create a deterministic version.
3) not fully utalizing each development cycle.
* You can print out a lot of information from a single cycle, so you can learn a lot from a single cycle.
4) Using a text editor that doesn't catch errors.
* text editors should warn you if parenthasis are unmatched, or if you forgot a symbol to terminate a function.
5) Writing code that never terminates.
* These types of errors are very hard to solve. Since the code never crashes and outputs an error report, it can be hard to even know where to start.
* Avoid using tools where it is easy to make a bug like this.
* consider using a tool that runs your code one line at a time, and displays information about the state at every line.



Considering the development cycle, lets break some common misconceptions about programming:
1) "If someone doesn't know the language/tool, then they cannot help with a project."
* false. Even if you have to look up every language feature in the documentation, it still probably isn't the bottleneck of your development cycle. Only spend time learning your language or tools if the bottleneck of your development cycle is looking these things up in documentation.
2) "you need to be smart to be a programmer"
* false. If your development cycle is twice as fast, it is just as good as being twice as smart. Being twice as smart is only a small advantage in comparison to what you can achieve by making the development cycle faster.

