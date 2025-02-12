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
First feedback request: 12 Feb 2025

//

Response 1: 

The first issue with asymptotic analysis being potentially misleading is due to a fundamental characteristic of asymptotic analysis as a whole.
Asymptotic analysis focuses upon the highest order and most important term in regards to performance. 
However, smaller order terms still make an impact. In varying situations, these smaller order terms still can make a difference to the overall performance and runtime,
though with asymptotic analysis, they are however ignored at large.

Another issue with asymptotic analysis being misleading could be as there are always differences between algorithms, 
and depending on the input size,
placing them into a blanket gap based on their highest ordered term can give the impression that all performances of shared terms in asymptotic analysis will always be near the same. 
However, depending on the input size as well as the use case, sharing the same highest ordered term does not mean that high levels of similarity in regards to performance is certain.

In essence, the above two related misleading traits in regards to asymptotic analysis revolve around asymptotic analysis being used as n approaches infinity.
In actuality, inputs of less than infinity are constantly experienced, and thus must be considered in full.

A third misleading issue about asymptotic analysis is that one of three scenarios are always considered, being that of a worst case, average case, or best case scenario. 
Though of course in real life applications input data can still align with these three categories, oftentimes it does not.
An incorrect interpretation of asymptotic analysis may cause researchers or individuals to misinterpret these three categories as the only possible categories that input data can fall into.

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
This could be the case,
despite the fact that reasoning using the asymptotic complexity suggests a different time for various potential reasons altering the runtime than what was anticipated when using asymptotics.

Some potential factors that could upset this predition are alterations from expected tree balance and implementation within either sections of the binary search algoritm
or associated processes. 

Additionally, no two machines are exactly alike, and most times, even the same machine will not run near exactly the same runtime as it may have prior. 

If burdened with other processes or perhaps even something like thermal throttling from handling a heavy workload for a while,
a machine may (unfortunately) decide to slow down to a great degree relative to its prior recorded performance in handling a certain process or program.

These factors would certainly throw off the timing of a binary search algorithm's asymptotic prediction, 
though not potentially to the extreme level outlined in the details of the third part of the exercise.

//

Plagiarism Acknowledgement: I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

Citations:
Reviewed with course material as well as these two Cornell lectures:

[https://www.cs.cornell.edu/courses/cs312/2004fa/lectures/lecture16.htm](url)
“Lecture 16: Introduction to Asymptotic Analysis.” Www.cs.cornell.edu, Cornell University, www.cs.cornell.edu/courses/cs312/2004fa/lectures/lecture16.htm.

[https://www.cs.cornell.edu/courses/cs3110/2012sp/lectures/lec19-asymp/review.html](url)
“Asymptotic Complexity.” Www.cs.cornell.edu, Cornell University, www.cs.cornell.edu/courses/cs3110/2012sp/lectures/lec19-asymp/review.html.

//

Not super relevant, but read a few excerpts from this University of Toronto research, but the vast vast majority of its content is way way too advanced for the level of analysis I am at.
Stil was cool to at least comprehend an ounce of it, ha.
[https://www.utstat.utoronto.ca/reid/research/wald.pdf](url)
Reid, N. “Asymptotics and the Theory of Inference.” The Annals of Statistics, vol. 31, no. 6, 1 Dec. 2003, www.utstat.utoronto.ca/reid/research/wald.pdf, https://doi.org/10.1214/aos/1074290325. Accessed 11 Feb. 2025.
