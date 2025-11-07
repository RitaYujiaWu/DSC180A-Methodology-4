---
layout: default
title: Home
---

# Rita Yujia Wu
UCSD Email: yuw172@ucsd.edu

Section: A08  
Mentor: Zhiting Hu/Kun Zhou

---

**What is the most interesting topic covered in your domain this quarter?**  
How far we can scale test-time computation (more rollouts, better planners/verifiers, recovery strategies) to push GUI agents at inference time without altering weights? It’s interesting because it promises immediate gains on real interfaces (Android/desktop/web) while sidestepping long, expensive retraining cycles.

**Describe a potential investigation you would like to pursue for your Quarter 2 Project.**  
Examine inference-time scaling for a GUI agent methodically by varying the planning depth, the rollout budget, and a basic verifier (such as goal-condition checks or UI state differences) across a limited set of tasks. Then, track the number of irreversible errors, the time to completion, and the success rate. I might compare (a) greedy single-trajectory, (b) top-k branching with pruning, and (c) retry-with-recovery (return to a safe screen, then resume) after packaging the tests in Docker for reproducibility.

**What is a potential change you’d make to the approach taken in your current Quarter 1 Project?**  
Make the project container-first by including deterministic seeds/snapshots for repeating user interface states along with a pinned Docker image and files that can be used to run the emulator, agent server, and evaluator with a single command. This resolves "works on my machine," expedites the onboarding of team members, and provides plug-and-play functionality for ablations (various inference budgets/planners).

**What other techniques would you be interested in using in your project?**  
- Search and Planning: lightweight MCTS, beam search over action sequences, or best-first search with a verifier's guidance.
- Recovery Heuristics: hysteresis to prevent oscillation and basic safe-state identification (such as familiar home/login screens).
- Data Leverage (lightweight): after we've perfected the Dockerized evaluation harness, employ behavior cloning or DAgger-style corrections after logging successful traces.
- Tool-calling: improved user interface state hashing/diffing and organized logs to show the benefits and drawbacks of additional inference budget.
