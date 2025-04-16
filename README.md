# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

Add your answers to this markdown file.


//


Name: Kane Kriz

Start Date: 11 Feb 2025

Feedback Request 1: 12 Feb 2025


//


Feedback Request 2: 13 April 2025


//



Response 1: 


**Reason 1: Disregard for lower terms**

The first issue with asymptotic analysis being potentially misleading is due to a fundamental part of asymptotic analysis as a whole.

Asymptotic analysis focuses upon the highest order and most important term in regards to performance.

However, smaller order terms still make an impact in realistic scenarios without notably large (asymptotic) input sizes.

In varying situations, these smaller order terms still can make a difference to the overall performance and runtime, though with asymptotic analysis, they are intentionally ignored.

// Below section is the remnanats of the now scrapped second reason that just ended up being too similar to the first every time
// ...kept them as they still have relevance to reason 1 but you can disregard them.

In actuality, real world performance has the potential to vary dramatically due to more nuanced factors that are disregarded when simply considering asymptotics and shared highest order.

Two algorithms could have the exact same asymptoptic runtime but behave with notable variation relative to one another in practice.

Asymptotic analysis could give off the impression that these two algorithms sharing the same listed asymptotic runtime should be running near identical in common applications, but this is not (often) the case.





**Reason 2: **


Asymptotic analysis could be potentially misleading as it assumes basic operations such as traditional compares to act in constant O(1) time.

For instance, consdier comparisons between high bit integers and comparisons between low bit integers.

A similar scenario can be considered when thinking about comparisons between short length strings and comparisons between long length strings.

In asymptotic analysis, these basic operations are assumed to be performed in constant time.

However, these comparisons still increase in required work and thus runtime as their size / complexity increases.

By treating these operations as constants within asymptotic analysis, further differences between expectations and real world runtime can occur.






**Reason 3: Defined Case Types being Restrictive, Non Informative Regarding differing likelihood of best and worst cases potentially occuring**


A third misleading issue about asymptotic analysis is that one of three scenarios are always considered: worst case, average case, or best case scenario.

Two of those three definitions entirely ignore to address possible liklehood of them occuring, being that of the best case and worst case complexity of an implementation.

Real world inputs often fall outside these sharp definitions of best, middle, and worst case categories. (though still remaining between the best case and worst case)

This leads to performance that in many cases will not match theoretical calculations seen with asymptotics as closely as it is often made out or assumed to be.

Real world normal usage of implementations can perform in input size ranges where lower order terms have a high sway over the experienced runtime.

An algorithm's worst case asymptotic bound might not reflect usually experienced behavior, as the worst case scenario may be difficult to encounter in practical usage of the implementation.

Consider two algorithms that each have worst case Θ(n^2) complexity.

One algorithm could have a worst case that only occurs if an input list is reverse sorted, for instance, so one possible input scenario where a worst case is experienced.

The other O(n^2) implementation may have a worst case that is shared among a large proportion of possible input lists. 

These differences in likelyhood (and thus relevance of worst case bounds, as an example) to standard use cases can vary widely between implementations that on paper share the same complexity as one another.

Of course, this would be a bad implementation, but it gives an example of how consulting asymptotic bounds alone do not show some necessary context and could be misleading when observed directly.





//





Response 2:


First I want to review the behavior of a binary search tree (in the hope that it will make thinking about the problem easier in my mind).

In a binary search tree, assuming full and proper balanced form of the tree, each search of the sorted tree about halves the remaining search area for the element,
following either the right or left child depending on whether or not the desired value is greater than or less than the element currently being checked.

This resultant "halving" of the remaining portions of the tree to search gives the search functionality of a binary search tree to have a run time complexity of O(logn). 

With what we know about the asymptotic complexity of search in a binary search tree, and my above mental review of the basic functionality of a binary search tree, 
I would say that finding the same element in a search of a tree of 10000 elements could be computed as follows.

log(n), with n as 1000 is provided to take 5 seconds as described in the problem details. In this case a theoretic log base is not explicitly given or pointed towards being used.

However, a ratio to compare the 5 seconds to a theoretical asymptotic prediction for the 10000 element example can still be made.

Consider log10(1000) = 3, log10(10000) = 4. (This could also be seen with log base 2, more relevant with computer science, yet the number 3 and 4 are prettier to look at and work with).

The ratio between these two expressions can be used to assume a theoretical runtime for the 10000 element example.

5 seconds * (4/3) = 20/3 seconds = 6.6666666... seconds.

Therefore, using the ratio between two log expressions with the known n values, and applying the shown ratio between them, 
we can assume the runtime of the 10000 element example to be 6.66666667 seconds.





//





Response 3:


A first example of something that could cause this to be the case is if the objects stored within the trees are compared in a way that requires large amounts of work, a scenario that could occur as explained below.

Lets say that rather than the elements within the tree being expressed as logical true / false or simple numerical values, that the tree's elements are made up of strings or a more complex type instead.

An implementation could attempt to compare the strings character by character.

These string compares could be assumed to take linear time, growing based upon the length of the compared strings.

Let's say that these strings are very long and vary at most by a couple characters at the end of their respective stored string.

Then, the compares between the two strings would have to waste time runing across all prior letters before this discovered difference between the two strings.

This process of comparing the contents of the strings could certainly create the runtime increasing concerns based on input size as expressed in the problem.

This is the case as all the problem specified was that the elements within the binary search tree increased by 10x, from 1000 to 10000.

No guarantee was made regarding the consistency or similarity of potential elements that the binary tree may house.

Let's say that the original 1000 elements (strings in this scenario) from the 1000 element tree were preserved into the 10000 element tree.

The remaining 9000 elements could be strings of any arbitrary length per the details of the problem.

These linear work string compares between the elements of the binary search tree could certainly contribute such a notable increase in required time to run, due to the imported elements into the tree not being guaranteed to be of any particular string length.






Additionally, no two machines are exactly alike, and most times, even the same machine will not run near exactly the same runtime as it may have prior. 

If burdened with other processes or perhaps even something like thermal throttling from handling a heavy workload for a while,
a machine may (unfortunately) decide to slow down to a great degree relative to its prior recorded performance in handling a certain process or program.




A third example of something that could cause that to be the case could be a potential poor implementation of checks and particular case handling.

This of course would have to not respond well to increases of input size beyond a certain degree.

For instance, with the transition of 1000 elements at 5 seconds into 10000 elements at 100 seconds, the time increase is extremely notable and characteristic of a problem occuring with the implementation (or machine, as covered) outlined in the problem.

Perhaps these checks and case handling implementations are made in an inefficient manner that rather than having a minimal effect on runtime (or potentially even memory complexity somehow, returning back to the above considered potential hardware causes),
they are at least partially responsible for this great increase in runtime observed.

These checks could manage to be implemented in a manner (i.e. some theoretical duplicate check with a poor actual implementation) that leads to something such as an n!-esque complexity for the check.

This inefficient check manner may not have had obvious runtime consequences for the input size of 1000, but once the input size was multiplied by 10 for the 10000 input size, these flaws became a significantly more notable and damaging problem to the runtime.

This could be assumed to have great consequences towards the runtime of the implementation, potentially to the degree outlined in the problem.




//


Plagiarism Acknowledgement: I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.


Citations:
Reviewed with course material as well as these two Cornell lecture pages, helping with some visualization and understanding of some assorted complexities and runtimes:

“Lecture 16: Introduction to Asymptotic Analysis.” www.cs.cornell.edu, Cornell University, www.cs.cornell.edu/courses/cs312/2004fa/lectures/lecture16.htm.

“Asymptotic Complexity.” www.cs.cornell.edu, Cornell University, www.cs.cornell.edu/courses/cs3110/2012sp/lectures/lec19-asymp/review.html.

https://cs.stackexchange.com/questions/50370/what-set-of-primitive-operations-are-assumed-to-be-constant-time-in-complexity-a


//


Not super relevant, but read a few excerpts from this University of Toronto research, but the vast vast majority of its content is way way too advanced for the level of analysis I am at.
Stil was cool to at least comprehend an ounce of it, ha.
Reid, N. “Asymptotics and the Theory of Inference.” The Annals of Statistics, vol. 31, no. 6, 1 Dec. 2003, www.utstat.utoronto.ca/reid/research/wald.pdf, https://doi.org/10.1214/aos/1074290325. Accessed 11 Feb. 2025.
