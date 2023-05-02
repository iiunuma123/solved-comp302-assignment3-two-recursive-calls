Download Link: https://assignmentchef.com/product/solved-comp302-assignment3-two-recursive-calls
<br>
<strong>We will test to see that you made two recursive calls in Q4, so you cannot just implement insertion sort. You cannot use any built-in sorting function.</strong>

Q1.Write a function common that takes a pair of lists and forms a new list containing a <em>unique </em>copy of each element that occurs in both lists. Here is the type, as echoed by the interpreter, and an example. val common : ’a list * ’a list -&gt; ’a list = &lt;fun&gt;

# let l1 = [1;3;2;4;1;5;6;3];; val l1 : int list = [1; 3; 2; 4; 1; 5; 6; 3]

# let l2 = [3;9;8;2;11;21;3];; val l2 : int list = [3; 9; 8; 2; 11; 21; 3]

# common (l1,l2);;

– : int list = [3; 2]

It does not matter if the final list is sorted or not. The input lists are not necessarily sorted. Indeed it should work on lists even when there is no notion of ordering the elements in the lists. You may find List.mem and List.filter useful.

The following three questions are about merge sort. The mergesort algorithm is a recursive algorithm for sorting lists which runs in time <em>O</em>(<em>n</em>log<em>n</em>). The items in the list must have an order relation defined on them, otherwise sorting does not make sense, of course.

The idea is as follows: the given list <em>l </em>is split into two equal (if the length of <em>l </em>is odd then one of the “halves” is one item longer than the other) lists <em>l</em><sub>1 </sub>and <em>l</em><sub>2</sub>. These lists are sorted recursively and then the results are merged back to give a single sorted list. Code this in OCaml. Your algorithm can use <em>&lt; </em>as a comparison operator. Your code <em>must </em>have a function split that produces a pair of lists, a function merge that merges <em>sorted </em>lists and a function mergesort that implements the overall algorithm. For testing only use integer lists.

Q2. In this question you will implement split with the following type:

val split : ’a list -&gt; ’a list * ’a list = &lt;fun&gt;

# split [1;3;2;4;5;6;9;11;17;13;12];;

<ul>

 <li>: int list * int list = ([1; 2; 5; 9; 17; 12], [3; 4; 6; 11; 13])</li>

</ul>

Q3.  In this question you will implement the merge algorithm. The inputs are <em>sorted </em>lists.

val merge : ’a list * ’a list -&gt; ’a list = &lt;fun&gt;

# let l3 = [1; 3; 5; 7; 9];; val l3 : int list = [1; 3; 5; 7; 9] # let l4 = [2; 4; 6; 8];; val l4 : int list = [2; 4; 6; 8]

# merge (l3,l4);;

<ul>

 <li>: int list = [1; 2; 3; 4; 5; 6; 7; 8; 9]</li>

</ul>

Q4. Finally we complete the mergesort algorithm. Here is the type and an example.

val mergesort : ’a list -&gt; ’a list = &lt;fun&gt;

# mergesort [10;2;8;5;1;4;3;9;7;6];;

<ul>

 <li>: int list = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]</li>

</ul>

# mergesort [1;3;2;4;1;2;5;3];;

<ul>

 <li>: int list = [1; 1; 2; 2; 3; 3; 4; 5]</li>

</ul>

Q5. [0 points] This question is for your spiritual growth only. Do not think it will give you extra credit or help you learn the material better. It will however stretch your brain in other directions. Do not attempt it if you have not yet finished the required homework. Do not submit a solution; please talk to me if you have solved it. Do not worry about it if you don’t understand the question.

How many comparisons are <em>required </em>to find the largest member of a list of <em>n </em>elements? [Easy] How many are required to find the largest <em>and </em>the smallest. [Not so easy] Here “required” means that in the worst case you will <em>have to do </em>that many comparisons. Can you find the smallest and the largest with fewer than 2<em>n </em>− 3 comparisons? Note that we are interested in exact counts; not just in <em>O</em>(·) estimates. Can you <em>prove </em>your claims