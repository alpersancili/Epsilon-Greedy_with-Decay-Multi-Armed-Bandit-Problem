# Epsilon-Greedy_with-Decay-Multi-Armed-Bandit-Problem
This project implements the Epsilon-Greedy algorithm with decaying epsilon to solve the Multi-Armed Bandit problem. The goal of this algorithm is to balance exploration and exploitation (leveraging arms. By using an epsilon decay, the exploration rate decreases over time, allowing the agent to focus more on exploitation as it gains experience.

PROBLEM OVERVIEW

In the Multi-Armed Bandit problem, an agent is faced with a set of arms (or actions), each associated with an unknown probability distribution of rewards. The agent's objective is to maximize its cumulative reward by pulling the arms based on the estimated rewards from previous actions. The challenge lies in balancing between exploration (trying less-known arms) and exploitation (choosing the arm with the highest expected reward).

ALGORITHM: EPSILON-GREEDY WITH DECAY

The Epsilon-Greedy algorithm works by selecting actions (arms) based on a trade-off between exploration and exploitation:
Exploration: With probability epsilon, a random arm is selected.
Exploitation: With probability 1 - epsilon, the arm with the highest estimated reward is selected.
Over time, the exploration rate (epsilon) decays, meaning that the agent gradually shifts from exploration to exploitation as it learns more about the arms. This helps to maximize long-term rewards.

KEY FEATURES

1.Epsilon Decay: The exploration rate (epsilon) starts high and decays over time, allowing the agent to explore more in the beginning and exploit learned rewards in the later stages.
2.Multi-Simulation Analysis: The algorithm is run across multiple simulations (1000 in this case) to gather average results and minimize the effect of randomness.
3.Performance Evaluation: The performance is evaluated using:
  -Average estimated rewards for each arm.
  -Average count of how often each arm is pulled.
  -Cumulative reward accumulated over time.
  -Regret: The difference between the optimal reward (always pulling the best arm) and the agent's actual reward.
  
PARAMETERS

num_arms: Number of arms (actions) in the bandit problem (set to 3 in this implementation).
num_plays: Number of total plays (or trials) in each simulation (set to 1000).
initial_epsilon: Initial value of epsilon, representing the exploration probability at the start (set to 1.0).
decay_rate: The rate at which epsilon decays after each action (set to 0.99).
true_reward_probs: The true probabilities of success for each arm (set to [0.2, 0.5, 0.7]).

RESULTS

The script outputs the following statistics:
Average Estimated Rewards: The average estimated reward for each arm across all simulations. This helps assess how well the agent has learned the true reward probabilities of each arm.
Average Counts: The average number of times each arm was pulled.
Final Cumulative Reward: The cumulative reward after all plays in the simulation.
Average Regret: The regret is calculated as the difference between the optimal cumulative reward (always pulling the best arm) and the agent's cumulative reward.
Difference Between True and Estimated Values: A comparison of the true reward probabilities and the agent’s estimated values for each arm.

VISUALIZATION

Cumulative Reward Plot: A graph showing the average cumulative reward over time. It demonstrates how the agent’s total reward evolves as it learns.
Regret Plot: A graph showing the regret over time, which highlights how well the agent is converging toward the optimal policy.
