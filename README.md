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




(

I added the bolded titles in to better separate the reasoning of the issues from one another as in the original feedback request they were kind of bleeding into one another and making it hard to follow my reasoning.
Also to make it more evident that reason 2 is not the same as reason 1, which was one of the outlined issues from the edits requested.

Thank you.

)




Response 1: 


**Disregard for lower terms**

The first issue with asymptotic analysis being potentially misleading is due to a fundamental part of asymptotic analysis as a whole.

Asymptotic analysis focuses upon the highest order and most important term in regards to performance.

However, smaller order terms still make an impact in realistic scenarios without notably large (asymptotic) input sizes.

In varying situations, these smaller order terms still can make a difference to the overall performance and runtime, though with asymptotic analysis, they are intentionally ignored.






**Oversimplified Algorithm groupings by highest order terms**

Another potential issue with asymptotic analysis is that it groups algorithms only by their highest order terms.

This varies from the first provided reason as this considers the grouping by highest order terms as not harmful through the ignorance of lower order values, but due to oversimplification of grouping algorithms by these highest order terms.

This could give the impression that two algorithms that have the same asymptotic complexity in common will perform similarly.

In actuality, real world performance has the potential to vary dramatically due to more nuanced factors that are disregarded when simply considering asymptotics and shared highest order.

The primary issue is that asymptotic analysis describes behavior as n grows extremely large, but practical inputs exist at limited scales, such as the mentioned 1,000 or 10,000 elements within the exercise/problem description.

At these sizes, lower order terms (which are ignored at large in asymptotic analysis) can significantly impact an algorithm's performance.





**Defined Case Types being Restrictive**

A third misleading issue about asymptotic analysis is that one of three scenarios are always considered: worst case, average case, or best case scenario.

Real world inputs often fall outside these best, middle, and worst case categories.

This leads to performance that in many cases will not match theoretical calculations seen with asymptotics as closely as it is often made out or assumed to be.






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


This could be the case, despite the fact that reasoning using the asymptotic complexity suggests a different time for various potential reasons altering the runtime than what was anticipated when using asymptotics.

The discrepancy could stem from the tree’s balance.

If elements were inserted in sorted order, the search tree gains the functionality similar to a linked list, turning a complexity O(log n) search into O(n). 

The loss of logarithmic scaling in favor of linear asymptotic scaling could certainly cause such an increase upon moving to the larger sort of 10000 elements.




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


//


Not super relevant, but read a few excerpts from this University of Toronto research, but the vast vast majority of its content is way way too advanced for the level of analysis I am at.
Stil was cool to at least comprehend an ounce of it, ha.
Reid, N. “Asymptotics and the Theory of Inference.” The Annals of Statistics, vol. 31, no. 6, 1 Dec. 2003, www.utstat.utoronto.ca/reid/research/wald.pdf, https://doi.org/10.1214/aos/1074290325. Accessed 11 Feb. 2025.
