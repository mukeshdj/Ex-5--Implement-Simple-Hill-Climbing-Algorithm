<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name: MUKESH S   </h3>
<h3>Register Number:    2305002016         </h3>
<h2> AIM: </h2>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> THEORY: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


## ALGORITHM:
 
Step 1- Read the target string from the user.

Step 2- Generate a random initial solution of the same length as the target.

Step 3- Calculate the score (difference) between the current solution and the target.

Step 4- Repeat the following steps until the score becomes zero:
a. Display the current score and solution.
b. Mutate one random character in the current solution to create a new solution.
c. Calculate the score of the new solution.
d. If the new solution has a lower score, replace the old one.

Step 5- When the score becomes zero, stop the process.

Step 6- Print the final solution as the target string.

## PROGRAM:
```python
import random, string

def hill_climb():
    target = input("Enter the target string: ")
    sol = [random.choice(string.printable) for _ in target]
    score = lambda s: sum(abs(ord(a)-ord(b)) for a,b in zip(s, target))
    best, best_score = sol, score(sol)

    while best_score:
        print(best_score, "".join(best))
        new = best.copy()
        new[random.randrange(len(new))] = random.choice(string.printable)
        new_score = score(new)
        if new_score < best_score:
            best, best_score = new, new_score

    print("Final:", "".join(best))

hill_climb()
```

<hr>
<h2>Sample Input and Output</h2>
<h3>Sample String:</h3> Hello
<h3>Output:</h3>
<img width="1234" height="455" alt="image" src="https://github.com/user-attachments/assets/315892ca-7be1-4595-81a3-4b04a340cc2b" />
.<br>
.<br>
.<br>
<img width="1053" height="662" alt="image" src="https://github.com/user-attachments/assets/2b2e6739-3908-4cab-a758-995268edacaa" />



## RESULT:

Thus the program to Implement Simple Hill Climbing Algorithm has been executed successfully.
