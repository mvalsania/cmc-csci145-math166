# Exams

## Midterm 2

<img width=400px src=img/2024fall-midterm2.png />

Common bad habits:

1. bad "pronunciation"
    1. $\mathcal X$ is pronounced "script X" or "mathcal X" (used to represent a dataset)

        $\chi$ is pronounced "chi"/"kai" (not used in this class)

1. not technically correct language
    1. Incorrect: In sample error smaller than generalization error means **most likely** overfitting.

        > **NOTE:**
        > This is true by definition.
        > So it is not "most likely" true or "reliably" true.
        > It does not "tend to" be true.

        Correct: A large VC dimension compared to the number of data points means we are **most likely** overfitting.

    1. Incorrect: We are underfitting, so we should use a **better** hypothesis classs.

        > **NOTE:**
        > The "no free lunch theorem" states that for every hypothesis class, there exists a data distribution that the hypothesis class cannot learn.

        Correct: We are underfitting, so we should use a hypothesis class with a **higher VC dimension**.

    1. Incorrect: $d_{VC} = \Theta(d), d=100 \implies d_{VC} = \Theta(100)$

       Correct: $d_{VC} = \Theta(d), d=100 \implies d_{VC} \approx 100$

Common concepts people misunderstood:

1. $N = 10•d_{VC}$ is only a guideline, not a theorem

    Only relationship between $E_{in}$ and generalization error determines whether you are over/underfitting.

1. $d_{VC} \uparrow$ does not guarantee $E_{in} \downarrow$;

    Only the subset relationship guarantees a relation between in sample error.

1. Hoeffding bound on $|E_{test} - E_{out}|$ does not depend on VC dimension

    Only $|E_{in} - E_{out}|$ depends on VC dimension

1. Universal approximation theorem states does not state that $d_{VC} \to \infty \implies E_{in} \to 0$.

    For example, convex sets had infinite VC dimension but not guaranteed to have 0 in sample error.

## Midterm 1

<img width=400px src=img/2024fall-midterm1.png />

Why oral exams?
1. Mimic technical interviews
1. Teach the [hidden curriculum](https://en.wikipedia.org/wiki/Hidden_curriculum) of how to succeed in a machine learning career

Common bad habits:
1. bad "pronunciation"
    1. $\epsilon$ is "epsilon" not "ee"

        (in our particular case, "error" or "residual" would be appropriate)
    1. $\mathbb x^{(k)}$ is NOT "x to the kth power"
    1. $\bar P$ is "P bar", $P'$ is "P prime", and $\hat P$ is "P hat"
1. not technically correct language
    1. Incorrect: $\alpha$ is a **random** value

        Correct: $\alpha$ is an **arbitrary** value

    1. Incorrect: Matrix multiplication is $O(n^3)$

        Correct: **The runtime** of matrix multiplication is $O(n^3)$

        Incorrect: $P$ is $O(n)$

        Correct: **The number of non zeros** of $P$ is $O(n)$

    1. Incorrect: $\bar {\bar P}$ is **defined** to have top eigenvalue 1

        Correct: $\bar {\bar P}$ is **defined** to be $\alpha \bar P + (1-\alpha) \mathbb e^T \mathbb v$.

        Correct: One **property** of $\bar {\bar P}$ is that it has top eigenvalue 1.

    1. Incorrect: The power method **helps us calculate** the top eigenvector.

        Correct: The power method **calculates** the top eigenvector.

    1. Incorrect: $O(n^3)$ grows **exponentially**
    
        Correct: $O(n^3)$ grows **polynomially**; $O(3^n)$ grows exponentially
1. No points removed for these mistakes
    1. but they are very annoying
    1. you will not pass a technical interview with these mistakes

Grading rubric:
1. 32 points
    
    16 points for initial explanation of PM/EAPM

    1. Not explaining that PM/EAPM calculates the top eigenvector, which is the pagerank

        You should:
        1. always describe an algorithm's WHAT/WHY before HOW
        1. start big picture; then go into details

    1. Not knowing / being able to derive the runtimes    

        The runtime per iteration is not enough; you needed the overall runtime, for example:

        $O\bigg(\frac{\log \epsilon}{\log \alpha} \text{nnz}(P)\bigg)$

    1. Not knowing typical values / ranges for all values in the formula and **why they are typical**

        For example:

        1. $\epsilon \in [10^{-3}, 10^{-6}]$ and google used $10^{-6}$

            why?
            1. we don't care about exact values of eigenvector, just the ranking of values
            1. $\epsilon$ smaller results in too slow convergence
        1. $\text{nnz}(P) = O(n)$

            why?
            1. true in the web domain only

                (people commonly said true of all sparse matrices, which is wrong)
            1. because each webpage has only small number of links

        1. RECALL: I can't cover all these small details in class
            1. you have to do the reading to get all these details and an A in the course
            1. class time is like "preparation" for understanding the reading, not an "alternative" to the reading

    1. Not being able to discuss how changing the value of a hyperparameter changes the runtime / accuracy

        1. Most people got $\epsilon$ and $n$, many people missed $\alpha$

    1. Not being able to discuss why the PM/EAPM converges to the top eigenvector

        1. Lots of ways to explain this that resulted in full credit

        1. Needed to somehow mention the eigenvalues / eigenvectors of $\bar{\bar P}$

    1. Not explaining how the runtimes of matrix multiplication (sparse vs dense) affect the algorithm's overall runtime

    8 points for question from Notes 1

    1. Not knowing the definitions of $P$, $\bar P$, $\bar {\bar P}$. 

    1. Not knowing the definitions of stochastic, irreducible, primitive

    1. Incorrect example/counterexample (usually due to an incorrect definition)

    8 points for question from Notes 2

    1. Not being able to explain the random surfer model

    1. Incorrect example/counterexample (usually due to an incorrect definition)

1. Bigger picture mistakes:
    1. Most "low grades" were due to a "mismatch of expectations"

        My expectation: You demonstrate knowledge sufficient to get hired at FAANG.

    1. Answer questions at the "right level"
        1. This requires a good "aesthetics"
           
           Explain interesting things, gloss over boring things

        1. Very common to answer "too low level"

            <img width=400px src=img/midterm1-toomuch.png />

            For the runtime of an equation, don't show me all the detailed arithmetic; just show me the runtime

            <img width=400px src=img/midterm1-justright.png />

            It's not "wrong" to be too low level, it just takes up time on "trivial" concepts that won't get you points

            (or won't get you hired)

        1. If you're "too high level", it's very easy for me to ask follow up questions for more detail
        
    1. Remember: oral exam / interview is "choose your own adventure"

        1. You are responsible for demonstrating the knowledge

        1. If you know something, say it!

    1. USE THE WHITEBOARD EFFECTIVELY

        If you don't put things on the board, I can't:
        1. understand what you mean and give you credit
        1. ask follow up questions

        This requires practice!

Recall:
1. Final grade will replace midterm grade if better.

Extra Credit:
1. You may earn +1 points ec for each letter grade below A.

    (B can get +1, C +2, D +3, F +4.)

1. You get 1 point of extra credit for each hour you spend whiteboarding problems with another student in this class.

   1. Do it in pairs, alternating who is writing on the whiteboard and who is listening / asking questions.

   1. Two students will both get 1 point of EC for the same hour.

   1. Each point must be with a different student. 

1. To claim the EC, send me an email with the names of the students and a short (1-2 sentence) explanation of what you covered.
