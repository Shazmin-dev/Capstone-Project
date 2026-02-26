# Imperial College London ML AI Capstone-Project
# NON-TECHNICAL EXPLANATION OF YOUR PROJECT
🧠 Black-Box Optimisation Capstone Project
What is this challenge about?

This capstone project simulates a real-world optimisation challenge inspired by Bayesian optimisation competitions.
The goal is simple to describe but difficult to solve:

We are required to find the maximum value of eight unknown functions. We are not given the equations, graphs, or internal details of these functions. They are treated as black boxes — we can only submit input values (guesses) and observe the output (the result).

Why is this important?

This setup reflects many real-world machine learning and engineering problems where:
Testing is expensive
Experiments are time-consuming
Data is limited
The internal system is unknown

Examples include:

Detecting radiation levels safely
Tuning robot control systems
Discovering effective drug compounds
Optimising industrial processes

In these situations, we cannot try every possible option. Instead, we must make carefully chosen, intelligent guesses.

What makes it challenging?

For each of the eight unknown functions:

We start with only a small amount of initial data
We are allowed a limited number of evaluations
Each new guess must be chosen strategically
Every evaluation counts because we don’t know what the function looks like, we must balance:

Exploration – testing new areas to learn more
Exploitation – refining areas that already look promising

There is no perfect solution expected. The emphasis is on:
Thoughtful experimentation, learning from results, adapting strategies over time demonstrating a clear reasoning process.

What this project demonstrates

This capstone is less about “winning” and more about showing:

Structured problem-solving
Intelligent trial-and-error
Transparent decision-making
Clear reflection on results

It mirrors how optimisation is done in practice — where uncertainty, limited information, and iterative improvement are the norm.

# DATA
A summary of the data you’re using, remembering to include where you got it and any relevant citations.

# MODEL
🔍 Optimisation Approach: Bayesian Optimisation with Gaussian Process
Overview

For this project, I used Bayesian Optimisation with a Gaussian Process (GP) to search for the maximum of each unknown function.

This approach is designed for problems where:
The function is unknown, evaluations are expensive or limited where we need to make the most of every single query rather than randomly guessing inputs, this method builds a smart prediction model that improves over time.

# HYPERPARAMETER OPTIMSATION
Description of which hyperparameters you have and how you chose to optimise them.

# RESULTS
A summary of your results and what you can learn from your model

# (OPTIONAL: CONTACT DETAILS)
If you are planning on making your github repo public you may wish to include some contact information such as a link to your twitter or an email address.

