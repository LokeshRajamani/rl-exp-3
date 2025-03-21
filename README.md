# POLICY ITERATION ALGORITHM

## AIM
To develop a Python program to find the optimal policy for the given MDP using the policy iteration algorithm.

## PROBLEM STATEMENT
The aim of this experiment is to find optimal policy for the mdp using policy iteration. Policy iteration includes policy evaluation and policy improvement where evaluation function is used to find optimal value function of each state and then improvement function is used to find best policy by comparing all the action value function as well as policy.

## POLICY ITERATION ALGORITHM
#### Step1 : 
we are going to do policy evaluation of each state to get the state value function where the initial policy is defined randomly to the mdp.

#### Step2:
Once we obtain convergence in the policy evaluation then implement policy improvement where we are going to find best optimal policy until the previous and current policy are same.

## POLICY IMPROVEMENT FUNCTION
### Name: LOKESH R
### Register Number: 212222240055
```
def policy_improvement(V, P, gamma=1.0):
    Q = np.zeros((len(P), len(P[0])), dtype=np.float64)
    # Write your code here to improve the given policy
    for s in range(len(P)):
      for a in range(len(P[s])):
        for prob,next_state,reward,done in P[s][a]:
          Q[s][a]+=prob*(reward+gamma*V[next_state]*(not done))
          new_pi=lambda s:{s:a for s, a in enumerate(np.argmax(Q,axis=1))}[s]
    return new_pi
```
## POLICY ITERATION FUNCTION
### Name: LOKESH R
### Register Number: 212222240055
```
def policy_iteration(P, gamma=1.0, theta=1e-10):
   random_actions=np.random.choice(tuple(P[0].keys()),len(P))
   pi = lambda s: {s:a for s, a in enumerate(random_actions)}[s]
   while True:
    old_pi = {s:pi(s) for s in range(len(P))}
    V = policy_evaluation(pi, P,gamma,theta)
    pi = policy_improvement(V,P,gamma)
    if old_pi == {s:pi(s) for s in range(len(P))}:
      break
   return V, pi
```

## OUTPUT:
### 1. Policy, Value function and success rate for the Adversarial Policy
![Screenshot 2025-03-21 131009](https://github.com/user-attachments/assets/0059ffd6-385f-42e8-b55f-2277d2bd1879)


![Screenshot 2025-03-21 131445](https://github.com/user-attachments/assets/2613c3ab-e328-41d3-9a84-bfc202f66798)


![Screenshot 2025-03-21 131051](https://github.com/user-attachments/assets/51eeb3e7-bf50-4e42-9249-bbc657a0b741)

### 2. Policy, Value function and success rate for the Improved Policy


![Screenshot 2025-03-21 133357](https://github.com/user-attachments/assets/4610da8b-53cd-45e7-b3c8-37ec3628b775)


![Screenshot 2025-03-21 133416](https://github.com/user-attachments/assets/58524435-e78a-417b-b62a-70e28cafc76f)



![Screenshot 2025-03-21 133608](https://github.com/user-attachments/assets/106444b4-1f03-429d-a444-b5bdbf1789da)




### 3. Policy, Value function and success rate after policy iteration

![Screenshot 2025-03-21 133516](https://github.com/user-attachments/assets/3d939798-6fa8-45ab-bed7-b74c56126e40)



![Screenshot 2025-03-21 133536](https://github.com/user-attachments/assets/7fb01d6f-495a-49c0-9906-b829c89f0e53)




![Screenshot 2025-03-21 133546](https://github.com/user-attachments/assets/e25d5c7c-3dc8-4c16-a344-8f22d372536d)




## RESULT:

Thus, The Python program to find the optimal policy for the given MDP using the policy iteration algorithm is successfully executed.
