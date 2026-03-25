# Imperial College London ML AI Capstone-Project
# NON-TECHNICAL EXPLANATION OF YOUR PROJECT
🧠 Black-Box Optimisation Capstone Project

The goal of this project is to apply skills learnt in this programme to real-world projects.
This project explores algorithms for black-box optimization—learning how to tune parameters efficiently when the function itself is hidden. The goal is to build practical skills for hyperparameter tuning and real-world ML challenges.
Tech Stack: Python, Jupyter Notebooks, NumPy, Pandas, Scipy, Scikit-learn, Matplotlib.

What is this challenge about?
This capstone project simulates a real-world optimisation challenge inspired by Bayesian optimisation competitions.
The goal is simple to describe but difficult to solve:
We are required to find the maximum value of eight unknown functions. We are not given the equations, graphs, or internal details of these functions. They are treated as black boxes — we can only submit input values (guesses) and observe the output (the result).

This setup reflects many real-world machine learning and engineering problems where:
-Testing is expensive
-Experiments are time-consuming
-Data is limited
-The internal system is unknown

What makes it challenging?
For each of the eight unknown functions, we start with only a small amount of initial data, We are allowed a limited number of evaluations where each new guess must be chosen strategically. Every evaluation counts because we don’t know what the function looks like, we must balance through:
Exploration – testing new areas to learn more
Exploitation – refining areas that already look promising

There is no perfect solution expected. The emphasis is on:
Thoughtful experimentation, learning from results, adapting strategies over time demonstrating a clear reasoning process.

The Project demonstrates the following skills and techniques:
-Structured problem-solving
-Intelligent trial-and-error
-Transparent decision-making
-Clear reflection on results

It mirrors how optimisation is done in practice — where uncertainty, limited information, and iterative improvement are the norm.

# DATA
The data used in this project is provided as part of the capstone challenge materials. It comprises eight distinct datasets, each corresponding to a separate black-box optimisation task. These tasks represent objective functions with input dimensionalities ranging from 2 to 8.

For each function, the dataset includes:

Input matrix (.npy format): Each row represents a previously evaluated point in the parameter space, with dimensionality specific to the task (2D–8D).
Output vector (.npy format): A one-dimensional array containing the scalar objective values associated with each input point.

Each dataset is initialised with ten observations, which serve as seed data for guiding the optimisation process.

The data is synthetic, but designed to reflect realistic optimisation scenarios such as hyperparameter tuning, chemical process optimisation, and resource allocation. As such, it incorporates key characteristics including noise, non-linearity, and the presence of local optima.

Datasets are loaded and explored using Python’s NumPy library (e.g., np.load()), and additional data points are generated iteratively by querying the black-box functions through the capstone project submission portal.

Data Source:
Capstone Project: Black-Box Optimisation — provided via the programme learning platform (internal course material; not publicly available).

# MODEL
🔍 Optimisation Approach: Bayesian Optimisation with Gaussian Process
Overview

For this project, I used Bayesian Optimisation with a Gaussian Process (GP) to search for the maximum of each unknown function.

This approach is designed for problems where:
The function is unknown, evaluations are expensive or limited where we need to make the most of every single query rather than randomly guessing inputs, this method builds a smart prediction model that improves over time.

# HYPERPARAMETER OPTIMSATION
What principle or heuristic did you use to decide on each query point?
For my first submission, I used a Gaussian Process (GP)–based Bayesian optimisation strategy for all eight functions. My overall aim was to balance exploitation (sampling where the GP predicts high values) and exploration (sampling where uncertainty is high).

For the 2D and 3D functions, I chose lower exploration values so the surrogate model could form a stable foundation. For the higher-dimensional functions, I increased exploration to help the GP probe uncertain regions more effectively.

Overall, my decisions were guided by choosing points that offered the best trade-off between high predicted output and high uncertainty.

 

Which functions were most challenging to query, and why? What extra information would have helped?
The higher-dimensional functions (6–8) were the most difficult. Their large input spaces and limited initial data make it hard for the GP to model uncertainty accurately. With only ten initial observations, it becomes challenging to identify promising areas early on.

More initial data or some domain knowledge about likely parameter ranges would have made the search more efficient and allowed the GP to guide exploration with more confidence.

Lower-dimensional functions were easier to work with such as functions 2-4. Having two queries per round made it possible to try both low and moderate values, encouraging useful exploration and reducing the chance of missing isolated peaks.

 

How will you adjust your strategy in future rounds?
For future rounds as more data becomes available I plan to adjust how I balance exploration and exploitation. As the GP model becomes better trained, I will gradually move from exploration toward exploitation to refine values.

For high-dimensional functions, I will generate near the current best point and in nearby unexplored regions to avoid local optima.

I also plan to use more concrete rules—such as detecting stagnation, monitoring uncertainty levels, checking surrogate model performance, or switching between acquisition functions (e.g., EI and UCB). If a function appears noisy, I may add repeated evaluations.

Since one new data point will be obtained each week, I will track the GP’s UCB and EI values over time to make more informed decisions.

In summary, my current submission relied on a principled mix of exploration and exploitation, guided by the GP model. Higher-dimensional functions were the most challenging due to limited initial data and large search spaces.

# RESULTS
A summary of the results and what I have learnt from the model will be written up closer to the end of the programme

<img width="750" height="446" alt="image" src="https://github.com/user-attachments/assets/71938141-6713-4fca-a0e0-8e3f1f992f4c" />


# (OPTIONAL: CONTACT DETAILS)
https://github.com/Shazmin-dev/Capstone-Project

