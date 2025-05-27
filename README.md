# CSCI-3110-Project-7-Heaps-solution

Download Here: [CSCI 3110 Project 7: Heaps solution](https://jarviscodinghub.com/assignment/project-7-heaps-solution/)

For Custom/Original Work email jarviscodinghub@gmail.com/whatsapp +1(541)423-7793

File(s) to be submitted: proj7.cpp, priorityqueue.h, card.h, card.cpp, makefile
Above files must be uploaded individually.
Submit only above files.

Objectives: 1) Implement a class template; 2) Implement and use a priority queue; 3) Overload comparison
operators in custom classes; 4) Implement and use a custom comparator in a class template.

Overview:
Write a class template that can be used to instantiate both min and max priority queues. The single class will use
a custom comparator to enqueue and dequeue items from a binary heap. Modify custom classes and manage
objects of the class using min and max priority queues instantiated from the class template.

Project description:
The program should have a class template that is the implementation of a priority queue. The implementation must be
based on building and maintaining heaps based on “highest priorities”, which may be minimum values or maximum
values, depending on the priority queue type.

A single enqueue and a single dequeue function will use a custom
comparator to add and remove items from both types of priority queues. The correct functioning of the priority queues
will be demonstrated by storing instances of a custom class.

Requirements:
1. Your program must be split into 4 files. There will be a class template, a separate interface and implementation file
for a custom class, and a driver file.

The requirements for these are specified below:
a) The PriorityQueue class template– This class represents a priority queue implemented using a binary heap. It has
two type parameters: 1) The type of the element stored in the heap (Card in this case); 2) A comparator class type.

 Note: There are known difficulties instantiating C++ class templates that have both a declaration (.h) and
implementation (.cpp) file. In light of this fact the class template must be implemented in a single file which
must be named priorityqueue.h

 The class must be named PriorityQueue
 You should implement the following member functions in the class
o A constructor – Resizes the vector representing the heap to hold 50 items. – Note: This (vector) size
represents the maximum number of elements in the heap (in this case it is more of an allocated
capacity value).

You will have to maintain a size variable that holds the actual number of elements in
the heap at any one time, as part of your implementation.
o dequeue (void) – Removes the highest priority item. Does not return it.
o enqueue (void) – Takes one parameter: the item to be enqueued. Enqueues the item and places it in
the proper heap order.

o heapUp (private, void) – Takes an index parameter and heaps the item up based on its priority.
o heapDown (private, void) – Takes an index parameter and heaps item down based on its priority.
o empty (boolean) – Returns true if queue is empty, and false otherwise
o print (void) – Displays the items in the heap, from index 0 through number of elements minus 1.
 Comparators – There will be two class template comparators each of which takes a type parameter.

One of
the comparators is used to compare if items are less than or equal to (<=), and the other to compare if they’re greater than or equal to (>=). Each of these classes will have a single, public, bool function that
returns the result of the above comparisons for two objects of the same type. This function must have the
same name in both class templates.

These classes will be used in the declaration of the priority queues (i.e.,
as type parameters), and will be defined in the file priorityqueue.h, outside of the PriorityQueue class
template. The handout (Fig 1.24) on the course calendar is an example of a custom comparator class. This
example must be converted to a class template so that it can be used with any custom class (i.e. so that it
does not compare only strings).

b) The Card class – This class will be a modified version of the Card class used in Project 4, and will be used to
demonstrate the generic nature of the priority queue (its ability to store objects of any type).
 Both the interface file (card.h) and the implementation file (card.cpp) from that project will be used
 The following changes are to be made to the Card class

o The <= and >= operators must be overloaded
o The order (lowest to highest by cardFace) will be Ace, 2, 3, 4, 5, 6, 7, 8, 9, 10, Jack, Queen, King. The
cardFace values of these cards are set to 1 through 13 respectively.
o The ostream << overload must be modified to output cardFace (instead of pointValue, as used in
Project 4). The data member pointValue will NOT be used in this project

c) A driver, or client, file that
 Must be named proj7.cpp
 Must read a file named pqseed.txt which contains a single integer (to be used as the random number seed)
 Must set the random number seed prior to shuffling the cards.

 Instantiates both a min priority queue and a max priority queue, using the PriorityQueue template
 Instantiates two arrays of 13 Card objects each. Note: you may not use the Deck class from Project 4.
o One array will have the 13 cards of the Spades suit, and the other will have 13 Hearts cards
o Each of these is a standard C++ array (not a vector, or any other class from the STL)
o The Cards must be placed into each Card array in face value order – from Ace to King – in elements 0
through 12 respectively

 Each card array must be shuffled using the following statement (your code must #include )
std::random_shuffle(std::begin(heartsDeck), std::end(heartsDeck)); // heartsDeck is an array name

Note: The Spades array must be shuffled first, followed by the Hearts array
 Enqueues the 13 Spades cards (in order from array indices 0 through12) into the max priority queue,
displaying the heap’s contents after each enqueue
 Dequeues each card individually from the max priority queue until it is empty – displays the heap’s contents
after each dequeue
 Enqueues the 13 Hearts cards (in order from array indices 0 through12) into the min priority queue,
displaying the heap’s contents after each enqueue

 Dequeues each card individually from the min priority queue until it is empty – displays the heap’s contents
after each dequeue
Note: Must use all functions specified above, to the greatest extent possible.

2. Sample output:
a) This output shows program execution with min and max heaps storing objects of the Card class – It was run on
the ranger system using random seed 1000 (read from file pqseed.txt).
b) The top line does not need to be displayed by your code. It is there to describe the output.

3. Test your program – Use different random seeds to test the program.
4. Code comments – Add the following comments to your code:
 A section at the top of the source file(s) with the following identifying information:
Your Name
CSCI 3110-00X (your section #)
Project #X
Due: mm/dd/yy

 Below your name add comments in each file that give an overview of the program or class.
 Place a one or two line comment above each function that summarizes the workings of the function.

5. Rubric
Requirements Points Off
Card: Has default constructor for use in Card array deck declaration -3
Card: Has two parameter constructor (cardFace and suit) to initialize each card in array -8
Card: Required comparison operators correctly overloaded as specified -5 (per op)
Card: ostream << correctly overloaded to display required output (see sample) -10

Comparator: Declared/implemented in priorityqueue.h, outside of that class’ definition -5
Comparator: Two class templates (one max, one min) with one type parameter (custom class) -5
Comparator: Each has commonly named public function to perform comparisons -5
PriorityQueue: Declared/implemented in full in priorityqueue.h -5
PriorityQueue: Class template with two type parameters: comparator and custom class -5
PriorityQueue: Constructor resizes heap vector to 50 elements -5

PriorityQueue: empty: returns true if the heap is empty, and false otherwise -5
PriorityQueue: enqueue: Enqueues an element and restore heap order property if required -10
PriorityQueue: dequeue: Dequeues highest priority element (and restores heap order property) -10
PriorityQueue: heapUp: Heaps an element up as far as it should be -10
PriorityQueue: heapDown: Heaps an element down as far as it should be -10
PriorityQueue: print: Outputs heap’s contents from index 0 to index size minus 1 -5
PriorityQueue: Maintains heap size in a variable, and updates at enqueue/dequeue -5

main: Input filename as specified -5
main: Data correctly read from file -5
main: Random number seed set as specified -5
main: Array decks instantiated (one Spades, one Hearts) as specified (order of cards) -10
main: Decks shuffled in the order specified -5

main: Cards enqueued in index order (into each priority queue) – Spades: max; Hearts: min -10
main: Cards dequeued in priority order (from each priority queue) -10
main: Uses the empty function to determine when the priority queues are empty -5 (per queue)
main: Invokes function to display heaps contents (in index order) after each enqueue/dequeue -5 (per queue)
main: Output closely matches specification (perfect spacing not required) -10
general: Does not compile (on ranger using Linux g++ compiler, and the provided makefile) -25
general: Runtime crash -25
general: Other TBD
