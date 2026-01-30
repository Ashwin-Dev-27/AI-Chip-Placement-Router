# 🤖 AI-Powered Chip Floorplanning Router

> A Reinforcement Learning (Q-Learning) agent that autonomously routes connections on a simulated VLSI chip grid, avoiding obstacles and optimizing for minimal wire length.

## 📌 Overview
Modern chip design involves routing billions of wires while adhering to strict Design Rule Checks (DRC). This project implements a **Mini-AlphaChip** approach, using an RL agent to learn spatial constraints and find the optimal path without human intervention.

Unlike traditional pathfinding (Dijkstra/A*), this agent learns the environment through trial and error, building a **Q-Table** that maps states to optimal actions.

## 📸 Results
**1. The Learned Path (18 Steps - Mathematical Optimum)**
The agent successfully navigated around the "Macro Block" (obstacle) to connect the Source (Green) to the Target (Red) with zero slack.


**2. The "Brain" (Q-Table Heatmap)**
Visualization of the Q-Values. Brighter areas represent high-confidence paths learned by the agent.


## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Algorithm:** Q-Learning (Reinforcement Learning)
* **Libraries:** NumPy (Physics), Matplotlib/Seaborn (Visualization)
* **Concepts:** Manhattan Geometry, Bellman Equation, State-Space Search

## 🧠 How It Works
1.  **Environment:** A 10x10 Grid representing a silicon layer.
2.  **Agent:** Starts with zero knowledge. Uses `Epsilon-Greedy` strategy to balance exploration vs. exploitation.
3.  **Reward System:**
    * **+100:** Reached Target.
    * **-10:** Hit Obstacle (DRC Violation).
    * **-1:** Step Cost (Incentivizes shortest path).
4.  **Outcome:** After 500 episodes, the agent converges on the optimal Manhattan Distance path.
