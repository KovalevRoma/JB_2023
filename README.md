# Task

A programmer has an upcoming exam and only has N hours left to prepare. The textbook has M topics, each of which requires a certain amount of hours Ti for studying, and has a certain number of questions Ki that could potentially appear on the exam. Unfortunately, N hours is not enough time to completely study all the topics, but the exam task will have L questions, chosen randomly from all the questions in the textbook with an equal probability. What is the best way to use limited time to maximize the chances of getting the best possible grade?

Propose an algorithm for solving this problem and implement it in any programming language. Pay attention to the performance of the program. Cover the code with tests.


# Algorithm.
Since the questions are chosen with equal probability, the programmer needs to learn as many of them as possible. This means that we need to learn a certain number of topics so that the time spent does not exceed N, and the number of questions in these topics is maximum. 
We get a standard backpack problem, where the subjects correspond to the topics, the weight of the subject is the time spent memorizing the corresponding topic, and the cost of the subject is the number of questions in the topic.
This problem is solved in $\mathcal{O}(M \cdot N)$ using dynamic programming. Memory costs: $\mathcal{O}(M \cdot N)$.

Let's create a *table* array of size (N+1) by (M+1). The *table[i][j]* cell contains the maximum number of questions that can be learned if the programmer learns only topics from the first to j, and he has only i time. The zero row and column correspond to situations when he has no time left and no questions, respectively. After filling in the table, we will get the answer in the *table[N][M]* cell.
