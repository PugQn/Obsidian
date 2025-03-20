I used this information to make a decision about naming conventions I used. There was more to the AI response but it was irrelevant so I ignored it.
![[Pasted image 20250321103537.png]]![[Pasted image 20250321103629.png]]
![[Pasted image 20250321103645.png]]


I wanted some ideas for structuring my program, to keep it organised and clean.
![[Pasted image 20250321114000.png]]
There were other examples but none that resonated with me. I asked the following subsequent prompts:
- I want to follow OOP best practice. Since none of my classes are parent or child classes, should I even have packages?
- What are some common package structures?
- the program will not have a UI but print statements to the terminal. There are set queries that will be run through main
- I have a main that will run the program. There are classes of objects, with their data and methods. Using this structure, where would I put the function that creates all the objects from my set list?
- what exactly are helper classes?
- so where would I put the function that traverses through all the objects in a class and returns a list of names of the objects?

From the responses to these questions, I decided to use a package structure that I am familiar with from work:
![[Pasted image 20250321114208.png]]
Main will only hold the main function.
Models will hold the object classes.
Utils will hold any other functions that need to happen to complete the assignment.


