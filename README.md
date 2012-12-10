CS 6601 Learning Portfolio, by Justin Permar

This page is my learning summary of Georgia Tech's Artificial Intelligence course, CS 6601, taken in Fall 2012. This page is logically divided into three parts: 1) Reading and Assignments, 2) Mini-projects, and 3) Course Recommendation.

1) Reading and Assignments

In the course, we completed 8 assignments on the foundations of AI, after reading the relevant material in the textbook.

The assigned reading covered over 900 pages of the "blue book" (Russell, Norvig. Artificial Intelligence: A Modern Approach, Third Edition. http://aima.cs.berkeley.edu/). I learned a great deal from the reading and assignments because it was all new to me. The philosophical underpinnings of modern AI are rationality, vaguely defined as seeking a "best outcome" given goals and knowledge of the world. The first major category of techniques used by a rational agent is search. Search is a fundamental tool designed to solve anything that can be formally represented as a "problem", defined (in part) by an initial state, a state transition model, and one or more goal states. Search is also the basis of more advanced AI techniques, such as simulated annealing, genetic algorithms, two-player zero-sum games (including games with chance), and constraint satisfaction problems. A key lesson from this portion of the course is the need to manage the size of a search space. It is very easy to encounter exponential growth in search spaces, which quickly leads to intractable problems.

The next major topic in the course is propositional and first-order logic, used to represent knowledge in rational agents. A key idea behind using logic is to enable entailment of new facts from existing knowledge, resulting in a learning capability for agents able to sense their environment. Combining search and logic naturally leads to a planning activity: devising a plan (of actions) in order to achieve goals. At this point, the course takes a significant turn by confronting reality: rational agents typically have imperfect knowledge and much of the time the world is only partially observable.

Thus, we enter the world of stochastic techniques which are designed primarily to handle uncertainty. The remainder of the assignment covered probability, and the critically important and pervasive Bayes' rule, which is the basis for Bayesian networks and probabilistic inference. Adding a time component to probabilistic inference leads to the need for Markov assumptions, briefly summarized as the simplifying assumption that the current state depends only on the prior state (for a first-order Markov process) and a related sensor Markov assumption, whereby  observations depend only on the current state. Markov assumptions leads to an extraordinarily powerful (and complex) technique of Hidden Markov Models, used to simulate a hidden state that is revealed only by observations (produced as a result of being in the hidden state). The observations can be used to recover the hidden sequence of state transitions by calculating the Viterbi path. By combining these techniques, a rational agent can make decisions in complex environments: those with non-deterministic actions and partial observability, formulated as partially-observable markov decision processes (POMDPs).

In the last section of the course, we covered learning, defined as the ability to increase future performance on tasks. Learning is a critical technique because of the complexity inherent in tasks that humans find quite basic: for example, how would you program a computer to recognize faces? Learning provides a valuable approach that suggests not solving the problem directly but by indirectly teaching a program to learn faces via techniques of unsupervised and supervised learning. We covered the basics of decision trees, neural networks, k-nearest neighbors, and support vector machines as tools to learn from data. The last two forms of learning we covered were learning probabilistic models (HMMs and Bayes nets) from data and learning policies that guide the agent on what to do in the absence of explicit �directions�.

Having learned the basics of all those topics from the reading, the assignments forced me to put theory into practice in order to understand why the algorithms presented in the book actually work and to understand the assumptions underlying the theory. For example, what are the implications of a negative step cost for search? What are the criteria for an admissible search heuristic? We answered these questions for our search assignment. The second assignment touched on the observation I stated above about search: it can quickly lead to computationally intractable search spaces. What are effective ways to prune the search spaces in the context of a two-player zero-sum games? These questions were answered in our second assignment. The third assignment covered logic. Because the purpose of logic is knowledge representation, the assignments focused on representing rules and familiar knowledge using first-order logic, and proving statements using resolution. The fourth assignment tested our knowledge of 1) deterministic planning by creating a sequence of actions in PDDL that lead from an initial world state to a goal state and 2) probabilistic inference using Bayesian networks. The fifth assignment focused on Hidden Markov Models, specifically using the Viterbi algorithm to recover the sequence of hidden states using a probabilistic model of observations and state transitions (i.e., HMMs). The sixth assignment, Learning, focused in on two common and powerful techniques for learning from data: learning decision trees from a data set via information gain and designing a neural network for XOR, which taught me exactly how neural networks can learn: by modifying weights on linked units, each of which implements a threshold functions. The seventh assignment focused on reinforcement learning by using POMDPs to determine how an agent can learn its location in a stochastic, partially observable world. The eighth assignment covered natural language processing, specifically n-grams and perplexity of n-gram models, the tradeoff between precision and recall inherent in information retrieval, and the basics of grammar representations (specifically, probabilistic context-free grammars).

From the reading and assignments alone, I learned the conceptual and mathematical underpinnings of modern AI. The early readings provided much background information on the rationale for using and applying the presented techniques. Later in the book, that rationale mostly disappeared. In particular, what I felt was missing from the book was an integrative approach that tackles systems design design by incorporating multiple AI techniques. The assignments effectively picked up where the reading left off. Because reading provides only a small fraction of the information on a topic, the assignments fill the gap to actively apply the techniques to problems. The assignments were extraordinarily effective at providing me with an in-depth understanding of each section of the course.

2) Course Content: Mini-projects

There were two mini-projects in which I chose to research a problem that was supposed to be relevant to my your future career. For each of these two projects, I proposed a solution, implemented it, and described it in a mini-conference paper.

I completed two projects, one on search in two-player zero-sum games, and other on gesture recognition. In the first project, I learned the details of minimax search and alpha-beta pruning by writing code for the problem statement and search routines. Additionally, I learned about Schaeffer�s history heuristic as a generally applicable search optimization technique. The key lesson I learned was the impact of exponential growth of a search space on the feasibility of search. Quite simply, exponentially growing search spaces are a nightmare for computational tractability. With the first project, I confirmed my ability to 1) understand the concepts and algorithms presented in the book and 2) write code from scratch to implement the algorithms.

My goal for the second project was to formulate and tackle a problem that I didn�t know how to solve. I chose gesture recognition primarily because it is a �hard problem� (an inverse perception problem). The approach I took in the end was to tackle the problem directly by taking an approach based on the visual similarity between the user�s gesture and the gesture library. This project taught me a few lessons, recounted in our paper: 1) user studies may need to involve training the user as much as the system; after all, computers are flawless at consistent reproduction of actions, but people demonstrate significant variance, and 2) because we don�t understand �basic� human operations such as perception, it is nearly impossible to directly code an approach. The primary lesson is to use an indirect approach, such as hidden markov models, or to take an alternative approach of training a system to to tell you which features matter (given a set of potentially relevant features).

Here are links to my two mini-project papers.

Mini-project 1: https://github.com/jpermar/gt6601learningportfolio/blob/master/papers/paper1.pdf

Mini-project 2: https://github.com/jpermar/gt6601learningportfolio/blob/master/papers/paper2.pdf

3) Course Recommendation

The course is advertised as being "doable" by someone who has not previously taken an AI course. As someone in that position, I can confirm that is true. Having said that, some things are easier said than done, so I would recommend taking an introductory AI course before this one, for two reasons. First, you may be able to avoid spending three or more days per week on this course, and second, you will likely absorb more information from the lectures, which are quite advanced. Note that if you have spent significant time tackling complex problems "on the job", that will also help you learn the advanced lecture material.

The reason to take this course is that it is taught by Dr. Thad Starner. First, he is an extraordinarily capable researcher with an impressive career. There is simply no comparison between reading the book on your own and learning the concepts and techniques presented in the lectures. During lecture, Thad provides his own perspective on the techniques, which typically differs from the book material. The shifted perspective significantly aids comprehension.

More importantly, however, the lectures contain content that is out of scope for the book. Thad introduces the students to the field of artificial intelligence, providing information. At a high level, I have two take-aways from the lectures regarding the field of AI: 1) a key insight into AI learning techniques is that they can be used when humans themselves don't understand how we work, and 2) in the future, combining "stochastic" approaches with "symbolic" approaches will prove to be a very powerful method for a systems-based approach to artificial intelligence, fundamentally fusing the researcher's intuition and creativity with the computer's ability to learn patterns in enormous data sets.