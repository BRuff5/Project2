# Project2
Project 2
Introduction
This project aims to introduce students to object-oriented languages, interfaces, inheritance, polymorphism, modularity, encapsulation, sub-typing, and overloading VIA, creating a quadtree data structure in Java. Students are expected to use CS project management techniques and technologies to simplify the development process and submit their code for grading. Through a class vote, all projects are INDIVIDUAL, and as a result, there should not be any duplicate code within reason. If there is significant plagiarism in a submission, I will mark all submissions with the same code with a 0.
Note: changes are in bold
Additionally:
•	You must use a unique GitHub repository to host your code. You cannot share the repository with other project/homework code
•	You must use the same repository for all resubmissions of the project.
•	You must pass at least 1 of my test cases to qualify for extra credit.
Necessary Tools
Some tools you’ll need to fully complete this project are:
•	Eclipse
o	Technically, you CAN use any text Editor, such as VSCode, but it’s a very bad idea.
•	Java SDK (should be auto-installed with eclipse)
•	Git version control, such as Git for Windows
To score points on the extra credit, you will need unit tests and documentation. Eclipse includes mechanisms for helping you with both.
Project Initialization
Your project can be initialized in several ways, but my recommended approach is:
1.)	Create an empty directory for your project.
2.)	Follow Maven’s recommended file structure for your project.
a.	You’ll probably only use the following:
i.	./src/main/java/
ii.	./src/test/java/
iii.	./src/it/
iv.	README.md (the site says .txt, but I’d suggest .md instead)
Project Details
For this project, you’ll create a quadtree data structure and manipulate it with data. To ensure you learn proper object-oriented programming techniques, there will be a few requirements for your implementation of this project. Namely:
•	You must have a base Node class.
•	You must have an InternalNode class that inherits from the base Node class.
•	You must have a LeafNode class that inherits from the base Node class.
You’re tasked with implementing five operations on your data structure:
•	Insert Rectangle – insert a rectangle into the quadtree.
•	Delete Rectangle – delete a rectangle from the quadtree.
•	Find Rectangle – find a rectangle in the quadtree.
•	Dump tree – print the quadtree.
•	Update Rectangle – change the length and width of a rectangle.
Quadtree Overview
Your quadtree should begin with reference to a single leaf node and store an initial space of 100x100 units centered on 0, 0. This means that the X and Y axis both range from -50 to +50.
 
Your quadtree should “split” a data Node when a 6th rectangle is inserted into the tree. Or, in other words, a leaf node can hold at most five rectangles. A rectangle is considered to be within the space of a Node when the bottom left corner of the rectangle with within the node’s space. Upon division, each of the four created leaf nodes should then store a 50x50 unit space.
 
It doesn’t matter which quadrant gets called node 2, 3, 4, or 5, as long as you remain consistent. In your code, this will mean that you use the same index, the top right, top left, bottom right, and bottom left, respectively, each time. Because this is a tree data structure, nodes are not allowed to have a reference to their parents.
Program Input
Similar to Project 1, your application should accept a command line argument. A file path to a .cmmd file will be given to your program that contains plain text commands for your application to process. 
Note: the processing of all plain text files is the exact same. In other words, the only difference between parsing this file and a .txt file is the file extension is different. Everything else is the same.
A cmmd file will look similar to this:
 
Insert X Y L W
Insert a rectangle into the quadtree as the specified X and Y coordinates with the specified length and width. If there is already a rectangle at the specified position, your program should terminate, and you should print a message saying, “You can not double insert at a position.”
Find X Y
Prints the rectangle at the specified X and Y positions. Printing a rectangle should result in:
Rectangle at [X], [Y]: [L]x[W] 
For example, one rectangle may result in:
	Rectangle at (10.00, 10.00): 5.00x5.00
If a rectangle is not found at the specified XY coordinates, your program should terminate, and you should print a message saying, “Nothing is at [X], [Y].”
Delete X Y
Deletes the rectangle at the specified XY coordinates. If a rectangle is not found at the specified XY coordinates, your program should terminate, and you should print a message saying, “Nothing to delete at [X], [Y].”
Note: if you delete rectangles from your tree and total number of rectangles in an internal node’s children fall below the threshold, it should revert back into a leaf node. That is to say, a tree should be able to revert back to a single empty leaf node if all the rectangles are deleted.
Update X Y L W
Updates the length and width of the rectangle at the specified XY coordinates. If a rectangle is not found at the specified XY coordinates, your program should terminate, and you should print a message saying, “Nothing to update at [X], [Y].” Note that updating the length and width of a rectangle will never move the rectangle to another node. It is the length and width relative to the bottom left corner.
Dump
Prints the entire quadtree. For each level of the tree (the head is at level 0, its children are at level 1, grandchildren at level 2, etc.), you should begin each line with an extra tab. For example:
 
Note:
•	The order of printed children does not matter as long as they’re under the correct parent.
•	The order of printed rectangles does not matter as long as they’re under the correct node.
•	Each node prints its space, which is the exact same as printing a rectangle. You can take advantage of that.
Project Submission
To submit your assignment, submit a GitHub link to your project. The master branch will be graded unless the link points to a specific branch. There are unlimited attempts before the project's due date. You’re expected to use them to get feedback regarding progress.
Additional Notes
Extra credit will be given for:
•	Good project documentation.
o	For every function, you should document what the function does, the arguments (if they exist), exceptions that can be thrown (if any), and the return value (if there is one) using Javadoc. 
•	Including functioning test cases for your code.
o	Tests should be done using JUnit test cases in Eclipse.
Project Grading
Grading will be broken down as follows:
Task	Points
Insert	20 points
Find	20 points
Delete	20 points
Update	20 points
Dump	20 points
Testing	25 points (bonus)
Documentation	25 points (bonus)
