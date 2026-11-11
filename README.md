# CliffWalking-RL: SARSA vs Q-Learning

## Overview

This project implements and compares two popular Tabular Reinforcement Learning algorithms — **SARSA and Q-Learning** — using Gymnasium's `CliffWalking-v1` environment.

The objective is to train an intelligent agent to navigate a grid-based environment, moving from the starting position to the goal while avoiding the dangerous cliff. The agent learns through trial and error by receiving rewards and penalties for its actions.

This project demonstrates the differences between **On-Policy and Off-Policy Temporal Difference (TD) Learning** algorithms.

## Environment

The project uses Gymnasium's `CliffWalking-v1` environment.

- The agent starts at the bottom-left corner of the grid.
- The goal is located at the bottom-right corner.
- A dangerous cliff lies between the starting position and the goal.
- Stepping onto the cliff results in a reward of **-100** and sends the agent back to the starting position.
- Each normal movement gives a reward of **-1**.
- Reaching the goal terminates the episode.

The objective is to learn a strategy that maximizes cumulative rewards while avoiding the cliff.

## Algorithms Implemented

### 1. SARSA (State-Action-Reward-State-Action)

SARSA is an **On-Policy Temporal Difference Learning** algorithm.

It updates the Q-value using the next action actually selected by the current epsilon-greedy policy.

**Update Rule:**

Q(s, a) ← Q(s, a) + α [r + γQ(s', a') - Q(s, a)]

### 2. Q-Learning

Q-Learning is an **Off-Policy Temporal Difference Learning** algorithm.

It updates the Q-value using the maximum estimated Q-value among all possible actions in the next state, regardless of which action the agent actually selects.

**Update Rule:**

Q(s, a) ← Q(s, a) + α [r + γ max Q(s', a') - Q(s, a)]

## Exploration Strategy

Both algorithms use an **Epsilon-Greedy Policy** to balance exploration and exploitation.

- **Exploration:** The agent selects a random action to discover new paths.
- **Exploitation:** The agent selects the action with the highest estimated Q-value.
- **Epsilon Decay:** The exploration rate gradually decreases during training, allowing the agent to rely more on its learned knowledge.

## Technologies Used

- Python
- Jupyter Notebook
- NumPy
- Gymnasium
- Reinforcement Learning
- Tabular Temporal Difference Learning

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/poojagyadav/CliffWalking-RL.git
```

### 2. Navigate to the Project Directory

```bash
cd CliffWalking-RL
```

### 3. Install Required Dependencies

```bash
pip install numpy gymnasium notebook
```

## Running the Project

The project is implemented using Jupyter Notebook.

### Method 1: Using Jupyter Notebook

1. Open Command Prompt or PowerShell.
2. Navigate to the project directory:

```bash
cd CliffWalking-RL
```

3. Launch Jupyter Notebook:

```bash
jupyter notebook
```

4. Your browser will open automatically.
5. Locate and click on `sarsa.ipynb`.
6. Select the appropriate Python kernel.
7. Execute the cells using `Shift + Enter` or click **Run All**.

### Method 2: Using VS Code

1. Open VS Code.
2. Open the `CliffWalking-RL` project folder.
3. Locate and open `sarsa.ipynb`.
4. Select a Python kernel.
5. Run the notebook cells using **Run All** or `Shift + Enter`.

**Note:** If Jupyter Notebook is not installed, run:

```bash
pip install notebook
```

## SARSA vs Q-Learning

| Feature | SARSA | Q-Learning |
|---|---|---|
| Learning Type | On-Policy | Off-Policy |
| Update Strategy | Uses the next selected action | Uses the maximum next-state Q-value |
| Learning Behaviour | Considers the current exploration policy | Learns the greedy optimal policy |
| Cliff Behaviour | Generally learns a safer path | Generally learns a shorter, riskier path |

## Expected Outcome

After training, both algorithms learn to navigate from the starting position to the goal.

- **SARSA** generally learns a safer route because it considers the possibility of exploratory actions.
- **Q-Learning** generally learns the shortest route near the cliff because it updates using the maximum estimated future reward.

The comparison highlights how different Q-value update strategies influence the agent's learning behaviour and path selection.

## Learning Objectives

- Understand the fundamentals of Reinforcement Learning.
- Implement SARSA and Q-Learning.
- Understand the difference between On-Policy and Off-Policy learning.
- Apply the Epsilon-Greedy exploration strategy.
- Compare learning behaviour and cumulative rewards.
- Understand how an agent learns a policy through interaction with an environment.

## Conclusion

This project demonstrates the implementation and comparison of SARSA and Q-Learning in a grid-based reinforcement learning environment. By analyzing both algorithms, it illustrates how different learning strategies affect exploration, decision-making, and the agent's ability to reach the goal while avoiding the cliff.

## Project Structure

```text
CliffWalking-RL/
│
├── sarsa.ipynb
├── README.md
└── 
```



