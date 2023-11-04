<h1>ExpNo 4 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name: BASKARAN  V</h3>
<h3>Register Number:212222230020</h3>
<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


# Algorithm:
Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.
 
Loop until a solution is found or there are no new operators left to be applied in current state:

Select an operator that has not yet been applied to the current state and apply it to produce a new state

Evaluate the new state:
  
if it is a goal state, then return it and quit
if it is not a goal state but better than current state then make new state as current state
if it is not better than current state then continue in the loop
  
Steps Applied:
## Step-1
 Generate Random String of the length equal to the given String
## Step-2
 Mutate the randomized string each character at a time
## Step-3
 Evaluate the fitness function or Heuristic Function
## Step-4:
 Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.
# PROGRAM
```
import random
import string
def generate_random_solution(answer):
    l=len(answer)
    return [random.choice(string.printable) for _ in range(l)]
def evaluate(solution,answer):
    #print(solution)
    target=list(answer)
    diff=0
    for i in range(len(target)):
        s=solution[i]
        t=target[i]
        diff +=abs(ord(s)-ord(t))
    return diff
def mutate_solution(solution):
    ind=random.randint(0,len(solution)-1)
    solution[ind]=random.choice(string.printable)
    return solution
def SimpleHillClimbing():
    answer="Shoaib"
    best=generate_random_solution(answer)
    best_score=evaluate(best,answer)
    while True:
        print("Score:",best_score," Solution : ","".join(best))
        if best_score==0:
            break
        new_solution=mutate_solution(list(best))
        score=evaluate(new_solution,answer)
        if score<best_score:
            best=new_solution
            best_score=score
#answer="Artificial Intelligence"
#print(generate_random_solution(answer))
#solution=generate_random_solution(answer)
#print(evaluate(solution,answer))
SimpleHillClimbing()
```

# Sample Input and Output
# Sample String: baskaran

# Output:
![Screenshot 2023-11-05 012558](https://github.com/BaskaranV15/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/118703522/2c3937d1-0502-42f3-bf62-2e12dbf74ca1)
# Result
Thus, the implementation of Simple Hill Climbing Algorithm and Generating a String by Mutating a Single Character at each iteration is successfully executed.
