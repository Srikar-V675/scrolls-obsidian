---
date: 2024-12-06
tags:
  - zettel
  - data-science
  - blog
status: literature
publish: true
---
# The Game of Chance: A Blog Post on Probability and Statistics

## 1. Introduction-The Loss of an F1 Race Due to the Sun

![[probability & statistics blog--.png]]

I'm sure most of you have encountered **[probability](https://en.wikipedia.org/wiki/Probability)** and **[statistics](https://en.wikipedia.org/wiki/Statistics)** in your daily lives, often without even realizing it.

As a huge fan of **Formula 1 racing**, I vividly recall a race I watched some time ago. While I can't remember the exact location of the event, I can clearly picture the unfolding drama. The race was progressing smoothly, with sunny and clear weather for the first 10 laps. Most teams had equipped their cars with **soft** or **medium tires**—perfect for these conditions. But, as is often the case in F1, things took an unexpected turn. The weather quickly shifted, and light rain began to drizzle. Many teams, fearing that the forecasted rain would intensify, made the decision to pit and switch to **rain tires**. However, some teams chose to stay out, betting that the drizzle would soon subside.

As the race continued, the rain stopped, and the weather cleared. The teams that had pitted for rain tires found themselves at a disadvantage. They had to pit again to switch back to regular tires, while the teams that had kept their original tires gained positions and, ultimately, won the race. This outcome highlights the importance of **probability**. Had the rain not stopped, those who didn’t switch to rain tires would have been the ones to lose.

In this race, as in many real-life scenarios, the outcome was uncertain, but the decisions were based on **probability**. Understanding how to assess probabilities can help us make more informed predictions and better decisions.

In this blog post, we’ll dive into the fundamentals of **Probability** and **Statistics**. To make the journey more enjoyable, I’ve also included an _interactive game_ for you at the end. Ready to learn more about the role of probability and statistics? Let’s get started!

## 2. Real-Life Examples

Just like the scenario I described earlier, **probability** and **statistics** are at play in many aspects of our daily lives. Here are a few examples:

- **Cricket**: When watching a match, you’ll often hear terms like **run rate**, **average score needed per over**, or even predictions about the **probability** of a team winning or the game ending in a draw. These are all applications of **statistics** and **probability** that help us understand the dynamics of the game.
- **Weather Forecasts**: Imagine you're deciding whether to carry an umbrella. You check the weather forecast, which tells you the likelihood of rain. This is another common use of **probability**, as the forecast is based on statistical models that estimate the chances of rain.
- **Health Risk Assessments**: After a health check-up, you may receive information about your risk of developing conditions like **diabetes**. These results are based on statistical models that assess your risk based on factors like age, lifestyle, and family history.

These are just a few real-life examples where **probability** and **statistics** influence our decisions and predictions.

## 3. Fundamental Concepts

**Probability** is the measure of the likelihood of an event occurring or not occurring. It helps us quantify the uncertainties tied to various events we encounter, like tossing a coin or drawing a card from a deck.

**Statistics**, on the other hand, is the field that deals with the **collection**, **analysis**, **interpretation**, **presentation**, and **organization** of data. It allows us to uncover meaningful insights from the data we gather, helping us make informed decisions.

![[probability & statistics blog.png|500]]

The image above humorously illustrates that "happy Jerry" is essentially the complement of "sad Jerry" (i.e., **1 - sad Jerry**).

### Key Terms:

- **Sample Space**: The list of all possible outcomes of an experiment.
- **Event**: Refers to a specific outcome or a set of outcomes in an experiment.

### 3.1 Probability Axioms

**Axioms** are self-evident principles or assumptions that are accepted as true without proof, serving as the foundation for further reasoning. In probability theory, the **probability axioms** are fundamental assumptions accepted by the community.

1. **Non-negativity**: The probability of any event is always a non-negative number. 
$$P(E) \geq 0$$
2. **Normalization**: The sum of the probabilities of all possible events that can occur is always equal to 1.
3. **Additivity**: For any number of disjoint sets (events that cannot happen simultaneously), the probability of one of these events occurring is equal to the sum of their individual probabilities.  
$$P(A∪B)=P(A)+P(B)$$

### 3.2 Disjoint Sets

As we mentioned earlier, **disjoint sets** are events that can never occur simultaneously. A simple example is in cricket: you cannot **hit a six** and **get out** on the same ball. These events are mutually exclusive, meaning the occurrence of one event excludes the occurrence of the other.

### 3.3 Random Variables 

A **random variable** is a variable that contains all the possible outcomes of an experiment, along with the associated probabilities of these outcomes occurring. Unlike the **sample space**, which only lists the possible outcomes, random variables also specify the likelihood of each outcome.

For example, the sample space of tossing a coin would be [head, tail], while the random variable would be {**head**: 0.5, **tail**: 0.5}, indicating that each outcome has a probability of 0.5.

There are two types of random variables:

1. **Discrete Random Variables**: These have a finite number of possible outcomes. For example, when rolling a die, the sample space has 6 possible outcomes (1, 2, 3, 4, 5, 6).
2. **Continuous Random Variables**: These have an infinite number of possible outcomes. For example, consider the sample space of all humans who are taller than 150 cm. Since height can vary continuously, there are infinitely many possible values within that range.

### 3.4 Gamblers Fallacy 

**Gambler's Fallacy** is an interesting principle that suggests a person might believe they can predict the outcome of an event based on past results, even before conducting the experiment. This belief arises from the misconception that past events influence future outcomes, even when the events are independent.

For example, a doctor might believe a patient has cancer based on their medical reports, even before conducting any tests. This conclusion could be influenced by previous cases where a similar patient was diagnosed with cancer, leading the doctor to make an assumption based on past data rather than the current evidence.

### 3.5 Measures of Central Tendency

**Measures of Central Tendency** are fundamental statistical tools used to identify the central point in an _ordered_ dataset. These measures help summarize a set of data by giving us a single value that represents the dataset as a whole. 

The primary measures of central tendency include the **mean**, **median**, and **mode**.

#### 3.5.1 Mean 

The **mean** is the average of the values in a dataset. It represents the value that is most common or typical in the data.

- **Sample Mean:** The mean calculated from a subset of the entire data.
$$\bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i$$
- **Population Mean:** The mean calculated from all the subsets of the entire dataset.
$$\mu = \frac{1}{N} \sum_{i=1}^{N} X_i$$

The mean is easily influenced by **outliers**, since extreme values can significantly alter the average.

#### 3.5.2 Median 

The **median** is the middle value of a dataset when ordered from least to greatest. It is a more robust measure of central tendency, as it is not as heavily influenced by outliers.

$$M =  \begin{cases}  x{\left[\frac{n+1}{2}\right]} & \text{if } n \text{ is odd} \\  \frac{x{\left[\frac{n}{2}\right]} + x{\left[\frac{n}{2} + 1\right]}}{2} & \text{if } n \text{ is even} \end{cases}$$

Where:
- $n$ is number of observations
- $X$ is the ordered data values

#### 3.5.3 Mode 

The **mode** is the most frequently occurring element in the dataset. For example, in a group of people, if most people say their favorite animal is a dog, then "dog" is the mode.

However, the mode doesn't always represent the central point of the dataset, particularly in cases where:

- There are **two modes** (bimodal distribution),
- The mode is an **outlier**.

![[proabability and statistics blog-1.excalidraw.svg|700]]

### 3.6 Quantiles 

**Quantiles** refer to dividing a dataset into equal subgroups, which allows us to analyze the distribution or spread of the data and detect outliers. Quantiles help to summarize data by breaking it into parts that provide insights into its overall pattern.

The most commonly used quantiles are **quartiles**, **deciles**, and **percentiles**.

- **Quartiles:** Quartiles divide the dataset into 4 equal parts, with each division called a _quartile_.

![[probability & statistics blog-2.excalidraw.svg|700]]

- **Deciles:** These divide the dataset into 10 equal parts, providing a finer breakdown of the distribution.
- **Percentiles:** Percentiles split the dataset into 100 equal parts, offering a detailed view of the data's distribution.

### 3.7 Variance 

**Variance** measures how much the data is spread out from the mean, or the common value, of the dataset. It provides an indication of the dispersion or variability in the data.

Variance is calculated as the average of the squared differences between each data point and the mean. It is also the square of the **standard deviation**.

Mathematically, the variance of a dataset is given by:

$$\sigma^2 = \frac{1}{N} \sum_{i=1}^{N} (x_i - \mu)^2$$

Where:
- $\sigma^2$ is the variance,
- $x_i​$ is each individual data point,
- $\mu$ is the mean of the dataset,
- $N$ is the total number of data points.

### 3.8 Standard Deviation

**Standard deviation** is closely related to variance, as they both measure how much the data is spread out from the mean. However, while variance represents the spread in squared units, the standard deviation provides a measure in the same units as the data.

Standard deviation is simply the square root of **variance**:

$$\sigma = \sqrt{V(X)} = \sqrt{\sigma^2}$$

Where:
- $\sigma$ is the standard deviation,
- $\sigma^2$ is the variance.

Since variance squares the differences, the unit of variance is also squared. To retain the original unit of measurement, we take the square root, which gives us the **standard deviation**. This makes the standard deviation a more intuitive measure, especially when interpreting data in real-world contexts.

### 3.9 Covariance 

**Covariance** measures the relationship between two datasets or variables, indicating how they change together. More specifically, it describes whether two variables tend to increase or decrease in tandem, essentially showing the direction of the relationship.

The formula for covariance is:

$$cov(X, Y) = \frac{1}{N} \sum_{i=1}^{N} (x_i - \mu{x}).(y_i - \mu{y})$$

Where:
- $X$ and $Y$ are the two variables,
- $x_i$ and $y_i$​ are individual data points,
- $\mu_x$ and $\mu_y$​ are the means of $X$ and $Y$, respectively.

While covariance tells us whether two variables move in the same direction (positive covariance) or in opposite directions (negative covariance), it does **not** provide information about the strength of their relationship. For this, we need to look at **correlation**.

![[probability & statistics blog-3.excalidraw.svg|700]]

## 4. Can you Win the Race? - Interactive Activity

![[probability & statistics blog---.png|500]]

In this game, you'll explore the role of probability in decision-making by choosing a pit stop strategy and calculating your race outcome based on probabilities. Can you make the right call and win the race?

### 4.1 Scenario Setup

Imagine you’re in an F1 race, and you’re in **3rd place** with just **3 laps remaining**. It's time to decide whether to make a pit stop and which tire strategy to go for. Your options are:

- **Soft Tires (Aggressive Strategy)**:  
    A high-risk, high-reward choice. You have a 70% chance of moving up to 1st place, but there’s also a 30% chance you could drop to 4th.
- **Medium Tires (Balanced Strategy)**:  
    A moderate approach. You have a 50% chance of moving up to 2nd, and a 50% chance of staying in 3rd.
- **Hard Tires (Conservative Strategy)**:  
    A safe bet. There’s a 90% chance you’ll maintain your 3rd-place position, but only a 10% chance of dropping to 4th.

### 4.2 How to Play

1. **Step 1: Choose Your Strategy**  
    Choose one of the three tire strategies: **Soft**, **Medium**, or **Hard**. Each strategy has different probabilities for your race outcome.
2. **Step 2: Simulate the Outcome**  
    To simulate the results, roll a six-sided die (or use a random number generator between 1 and 6) and refer to the chart below to see what happens based on your roll:

|**Roll**|**Soft Tires Outcome**|**Medium Tires Outcome**|**Hard Tires Outcome**|
|---|---|---|---|
|**1**|Gain 2 positions (Win)|Gain 1 position (2nd)|Maintain position (3rd)|
|**2**|Gain 2 positions (Win)|Gain 1 position (2nd)|Maintain position (3rd)|
|**3**|Gain 2 positions (Win)|Gain 1 position (2nd)|Maintain position (3rd)|
|**4**|Gain 2 positions (Win)|Maintain position (3rd)|Maintain position (3rd)|
|**5**|Lose 1 position (4th)|Maintain position (3rd)|Maintain position (3rd)|
|**6**|Lose 1 position (4th)|Maintain position (3rd)|Lose 1 position (4th)|

3. **Step 3: Record Your Results**  
    After each race, write down the strategy you chose, the number you rolled, and your final position. Here’s a table to help you keep track:

| **Race Attempt** | **Chosen Strategy** | **Roll** | **Final Position** |
| ---------------- | ------------------- | -------- | ------------------ |
| 1                | Soft Tires          | 3        | 1st (Win)          |
| 2                | Medium Tires        | 6        | 3rd                |
| 3                | Hard Tires          | 5        | 3rd                |

### 4.3 Analysis Questions for You

- Which strategy gave you the best outcomes?
- Did your observed outcomes match the probabilities?
- What would you choose if you had only one attempt left?

## 5. Conclusion

In this blog post, we've explored the fundamental concepts of **probability** and **statistics**, including their practical applications in real life. From the basics of probability axioms and disjoint sets to more advanced concepts like variance, standard deviation, covariance, and quantiles, we've seen how these concepts help us make informed decisions and understand the data around us.

Whether it's deciding the best tire strategy in an F1 race, predicting the likelihood of rain, or analyzing trends in sports and health, probability and statistics are tools we use daily, often without realizing it. By gaining a deeper understanding of these principles, we can better navigate the uncertainty of the world and make smarter, more data-driven choices.

We also explored a fun, interactive F1 strategy game to demonstrate how probability influences decision-making in dynamic situations. I hope it helped solidify the concepts and made the learning experience more engaging!

Remember, while the future may always carry a degree of uncertainty, **probability** and **statistics** allow us to make more accurate predictions and better understand the world. Keep practicing these principles, and you'll see how they play a crucial role in almost every decision-making process, whether in your personal life or in the professional realm.

If you would like to go deeper and learn more advanced topics then you can take a look at the mind map below for the advanced topics you would want to learn next. 

![[probability-mindmap.excalidraw.svg]]

## 6. References

- Course notes
- [Probability and Statistics in Everyday Life. | by Shubhranshu Arya | Medium](https://medium.com/@shubhranshuarya/probability-and-statistics-in-everyday-life-22f0ab78965a)
- [Probability - Wikipedia](https://en.wikipedia.org/wiki/Probability)
- [Statistics - Wikipedia](https://en.wikipedia.org/wiki/Statistics)
- [Probability axioms - Wikipedia](https://en.wikipedia.org/wiki/Probability_axioms)
- ChatGPT
- Perplexity