# POLICY ITERATION ALGORITHM

## AIM
To develop a Python program to find the optimal policy for the given MDP using the policy iteration algorithm.

## PROBLEM STATEMENT
The task is to develop and use a policy iteration algorithm to solve a grid-based environment (gym-walk), where the agent learns the optimal sequence of actions to maximize its probability of reaching the goal state and achieving the highest cumulative reward.


## POLICY ITERATION ALGORITHM
Step 1: Start with a random policy and an arbitrary value function.

Step 2: Compute the value function for the current policy.

Step 3: Update the policy to be greedy with respect to the current value function.

Step 4: Repeat evaluation and improvement until the policy stabilizes.

Step 5: The final policy is optimal and provides the best actions for each state.


## POLICY IMPROVEMENT FUNCTION
### Name: LOKESH R
### Register Number: 212222240055
```python
def policy_improvement(V, P, gamma=1.0):
    Q = np.zeros((len(P), len(P[0])), dtype=np.float64)
    for s in range(len(P)):
      for a in range(len(P[s])):
        for prob, next_state,reward, done in P[s][a]:
          Q[s][a]+= prob*(reward+gamma*V[next_state]*(not done))
          new_pi = lambda s: {s:a for s, a in enumerate(np.argmax(Q, axis=1))}[s]

    return new_pi
```
## POLICY ITERATION FUNCTION
### Name: LOKESH R
### Register Number: 212222240055
```python
def policy_improvement(V, P, gamma=1.0):
    Q = np.zeros((len(P), len(P[0])), dtype=np.float64)
    for s in range(len(P)):
      for a in range(len(P[s])):
        for prob, next_state,reward, done in P[s][a]:
          Q[s][a]+= prob*(reward+gamma*V[next_state]*(not done))
          new_pi = lambda s: {s:a for s, a in enumerate(np.argmax(Q, axis=1))}[s]

    return new_pi
```

## OUTPUT:
### 1. Policy, Value function and success rate for the Adversarial Policy


![Screenshot 2025-03-19 114437](https://github.com/user-attachments/assets/838241f4-e7b9-4b21-806d-a3e84d34ae22)




![Screenshot 2025-03-19 114321](https://github.com/user-attachments/assets/41287b50-9182-424c-a9dc-d6c76d6b2910)


### 2. Policy, Value function and success rate for the Improved Policy

![Screenshot 2025-03-19 114157](https://github.com/user-attachments/assets/2b897bb7-2314-4ff5-87ca-fc379efadf76)


![Screenshot 2025-03-19 114130](https://github.com/user-attachments/assets/7d1be6c1-0f15-4e63-b249-92d82ea56523)



![Screenshot 2025-03-19 114052](https://github.com/user-attachments/assets/d3aed615-1430-4b1f-af53-4d742c04e72b)



### 3. Policy, Value function and success rate after policy iteration
![Screenshot 2025-03-19 113927](https://github.com/user-attachments/assets/05962171-6679-41e1-a2c4-3475a37d2b3c)





![Screenshot 2025-03-19 114002](https://github.com/user-attachments/assets/60068c66-cc9f-4b85-99bb-5d9c0eb67d49)



## RESULT:
Thus, the program to iterate Policy improvement and evaluation is implemented successfully
