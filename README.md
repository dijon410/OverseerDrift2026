## Inspiration
Our inspiration was Greenblatt et al. (2025) and the ControlArena platform. In the article, the researchers introduced the idea of control evaluations, where a stressed environment assumes that an AI might be trying to subvert oversight. In addition to this, we wanted to prove that reward hacking was a significant negative consequence of reinforcement learning from AI feedback or RLAIF. We wanted Overseer Drift to simulate realistic scenarios of agents implementing this issue in real time. 

## What it does
Simulates real-time agent manipulation and reward hack consequence using 4 agents. Two worker agents collaborate to solve a task such as a mathematical proof. One monitor agent evaluates these worker agents using an evolving scoring policy. This policy, however, can be shifted due to critiques from the worker agents. This action implements the reward hacking phase, where agents learn to exploit the weaknesses of other agents. Our final agent is an unbiased, independent agent that provides a stable benchmark for true proof accuracy. These 4 agents, along with the environment, provide researchers a sandbox to study reward hacking. 

## How we built it
For the frontend, we used React with Vite to create the main user interface and Recharts for all data visualizations. For the backend, we used Python with FastAPI to handle API calls and the turn-based agent system, with Anthropic's Claude Sonnet as the underlying model powering all four agents.
We used Snowflake to log all experiment telemetry, storing round-by-round scores, policy drift events, agent critiques, and proof steps in a persistent audit database.

## Challenges we ran into
A key challenge that we ran into was deciding between and shifting between two projects that were similar. Our first idea was a simulation where multiple agents collaborated with each other on a single project, and one was assigned the role of the saboteur, giving us the ability to analyze agents' behavior in mitigating and identifying this saboteur. We decided to discard this idea, however, because we believed that the reward hack aspect that we were trying to prove was not being shown by the analysis done on this project. Therefore, we decided to shift our project to what we have now, the worker manipulation project that analyzes the reward hack problem through analysis of the monitor agent. 

## Accomplishments that we're proud of
We are proud of our ability to adapt from a project that we had discarded to a project with a new concept but the same ideals. It was very brave of us to make that shift deep into the competition, regardless of all the progress that we had made so far. Along with this, we are also proud of getting multiple API agents to stay on track and not dissolve into utter chaos. We had cleverly implemented the turn-by-turn basis in addition to the scoring basis to create a smoothly flowing project. 

## What we learned
We learned that in AI safety, reward hacking is a large issue, especially in agent-to-agent collaboration, which is difficult to mitigate. Before, we did not know that agents of higher authority could be influenced by lower agents. In addition, we learned that the use of an independent, unbiased agent is the best way to mitigate reward hacking between monitors and worker agents, so that there is a specific fixed criterion that they can also fall back on. 

## What's next for Overseer Drift
Right now, we feel that Overseer Drift is a sandbox for researchers studying the field of reward hacking. We want to generalize this simulation to specification gaming, monitor degradation, and collusion risks so agent-to-agent collaboration can be tested before failures show up in real-world projects. We also want to move beyond a sandbox toward a continuous monitoring system — one that runs indefinitely and surfaces alignment failures automatically as they emerge.
