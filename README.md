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
First I want to review the behavior of a binary search tree (in the hope that it will make thinking about the problem easier).
In a binary search tree, assuming full and proper balanced form of the tree, each search of the sorted tree about halves the remaining search area for the element,
following either the right or left child depending on whether or not the desired value is greater than or less than the element currently being checked.

With what we know about the asymptotic complexity of search in a binary search tree, and my above mental review of the basic functionality of a binary search tree, I would say that finding the same element in a search of a tree of 10000 elements would be found as follows:

RESPONSE NOT DONE YET

//

Response 3:
This could be the case, despite the fact that reasoning using the asymptotic complexity suggests a different time for various potential reasons altering the runtime than
what was anticipated when using asymptotics.

RESPONSE NOT DONE YET

//

Plagiarism Acknowledgement: I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

Citations:
Reviewed with course material as well as:

[https://www.cs.cornell.edu/courses/cs312/2004fa/lectures/lecture16.htm](url)
“Lecture 16: Introduction to Asymptotic Analysis.” Www.cs.cornell.edu, Cornell University, www.cs.cornell.edu/courses/cs312/2004fa/lectures/lecture16.htm.

Read a few excerpts from this University of Toronto research, but the vast vast majority of its content is way too advanced for the level of analysis I am at.
Stil was cool to at least comprehend an ounce of it, ha.
[https://www.utstat.utoronto.ca/reid/research/wald.pdf](url)
Reid, N. “Asymptotics and the Theory of Inference.” The Annals of Statistics, vol. 31, no. 6, 1 Dec. 2003, www.utstat.utoronto.ca/reid/research/wald.pdf, https://doi.org/10.1214/aos/1074290325. Accessed 11 Feb. 2025.
