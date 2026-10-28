<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name: ABIRAMI A          </h3>
<h3>Register Number: 212224040010      </h3>
<H3>Date: 26.10.26</H3>

<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
<p>
<ol>
 <li> Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.</li> 
<li>Loop until a solution is found or there are no new operators left to be applied in current state:
<ul><li>Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
<li>Evaluate the new state:
  <ul>
<li>if it is a goal state, then return it and quit</li>
<li>if it is not a goal state but better than current state then make new state as current state</li>
<li>if it is not better than current state then continue in the loop</li>
    </ul>
</li>
</ul>
</li>
</ol>

</p>
<hr>
<h3> Steps Applied:</h3>
<h3>Step-1</h3>
<p> Generate Random String of the length equal to the given String</p>
<h3>Step-2</h3>
<p>Mutate the randomized string each character at a time</p>
<h3>Step-3</h3>
<p> Evaluate the fitness function or Heuristic Function</p>
<h3>Step-4:</h3>
<p> Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.</p>

<hr>
<h2>Sample Input and Output</h2>
<h2>Sample String:</h2> Artificial Intelligence
<h2>Output:</h2>
Score: 643  Solution :  8RzF:oG ]%;CPORRMe!zGvk<br>
Score: 609  Solution :  8RzF:oG ]%;CPqRRMe!zGvk<br>
Score: 604  Solution :  8RzF:oG ]%;CPqRRMe!zGqk<br>
Score: 594  Solution :  8RzF:oG ]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
....................................................<br>
..................................................<br>
................................................<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 0  Solution :  Artificial Intelligence<br>

## Program:
```
import random
import string

def generate_random_solution(answer):
    l = len(answer)
    return [random.choice(string.printable) for _ in range(l)]

def evaluate(solution, answer):
    print(solution)
    target = list(answer)
    diff = 0

    for i in range(len(target)):
        s = solution[i]
        t = target[i]

        diff += abs(ord(s) - ord(t))

    return diff

def mutate_solution(solution):
    ind = random.randint(0, len(solution) - 1)
    solution[ind] = random.choice(string.printable)
    return solution



def SimpleHillClimbing():
    answer = input("Enter the String:")

    best = generate_random_solution(answer)
    best_score = evaluate(best, answer)

    while True:
        print("Score:", best_score, " Solution:", "".join(best))

        if best_score == 0:
            print("\nTarget String Found!")
            break

        new_solution = mutate_solution(list(best))
        score = evaluate(new_solution, answer)

        if score < best_score:
            best = new_solution
            best_score = score

SimpleHillClimbing()
```
## Output:

<img width="1143" height="856" alt="image" src="https://github.com/user-attachments/assets/ba51a894-3809-40c7-8780-3fde6d72ca1b" />

<img width="1172" height="846" alt="image" src="https://github.com/user-attachments/assets/682c7de4-7878-460a-a684-68e7c6d6e8c6" />

<img width="1157" height="816" alt="image" src="https://github.com/user-attachments/assets/de4baba6-7f7e-4de1-9900-3c4bfa9b8e02" />

<img width="1167" height="837" alt="image" src="https://github.com/user-attachments/assets/30dc8ab5-afc3-4dec-85a5-0572dec2148a" />

<img width="1161" height="833" alt="image" src="https://github.com/user-attachments/assets/13122dd4-d0ca-423e-82e4-bc5f300d9948" />

## Result:
   Thus the program to implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration is executed successfully.

