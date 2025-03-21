# abtest-mab-recommendations

**Overview**

This project applies A/B testing and Multi-Armed Bandit (MAB) strategies to the MovieLens dataset to evaluate user ratings and optimize movie recommendations. The goal is to simulate real-world decision-making in recommendation systems by:
	•	Comparing movie ratings between a control group (A) and a treatment group (B).
	•	Using an epsilon-greedy algorithm to dynamically identify the best-performing movie.

**Dataset**

We use the MovieLens 100K dataset, which consists of:
	•	100,000 ratings from 943 users on 1,682 movies
	•	Columns: user_id, item_id, rating (1-5 scale), timestamp

Dataset source: MovieLens 100K

**Project Steps**

**1. Load MovieLens Dataset**

The script loads the MovieLens dataset directly from the web into a Pandas DataFrame.

**2. Split Data into A/B Groups**

Each row (movie rating) is randomly assigned to either the control group (A) or treatment group (B) for A/B testing.

**3. Compute A/B Test Metrics**

The average movie ratings in Group A and Group B are compared, and the percentage uplift is calculated to measure the difference.

**4. Multi-Armed Bandit (Epsilon-Greedy Algorithm)**

A Multi-Armed Bandit (MAB) approach is used to dynamically select the best movie based on user ratings.
	•	Exploration: With probability epsilon, a random movie is selected.
	•	Exploitation: Otherwise, the movie with the highest observed average rating is chosen.
	•	The process runs for 1000 iterations to identify the best movie.

**Expected Output**
	•	A/B Test Results:
	•	Displays the average ratings for groups A & B.
	•	Computes percentage uplift in ratings from A to B.
	•	Multi-Armed Bandit Results:
	•	Identifies the best-performing movie dynamically over multiple iterations.
