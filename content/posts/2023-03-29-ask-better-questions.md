---
title: Ask better questions
slug: ask-better-questions
date: 2023-03-29
draft: true
excerpt: If you are working on the wrong problem, the quality of even the best neural networks, probabilistic and gradient boosted models would be useless. However, in data science, it is assumed that the problem being worked on is always clear. It is not.
---

In his post **[Tukey, Design Thinking, and Better Questions](https://simplystatistics.org/posts/2019-04-17-tukey-design-thinking-and-better-questions/)**, *[Roger Peng](https://twitter.com/rdpeng)* points to the importance of asking better questions as a data scientist.

The best neural networks, probabilistic and gradient boosted models are worthless, if you are working on the *wrong problem.*

But in data science the problem should always be clear, right?
Quite the opposite. Let's consider the following scenario:

🛳️

A port needs you to **predict how the water levels rise** when the tide rolls in, to ensure that the planned loading dock won't get flodded. You get access to a ton of data on the water level during peak flood. You add more data on the daily weather, day of the year and number of ships in the port, and use these as your features. You regress the current water-level on yesterdays water-level and these additional data. **The model turns out great!** It predicts the water levels very precisely in your test data. You are *very***confident** in your results.

*Within the first week after construction the new loading dock gets flooded. Your model's prediction was way off – Where did it go wrong?*

The theme of the post gives away what the answer to this riddle might be: Somehow, this is about the **question** you did (or did not) ask yourself when working on this project. 

In fact, it is about a **buried question**. 🍃

While we often treat our models as separate entities, they always go together with a question. The tricky part? Models still give an answer to their associated question, even though you might not be aware of their question.

Problems arise when your own and your model's questions do not align. You take a **correct answer to a different question** as the (most likely wrong) answer to **your question**. 

In the scenario above, we try to predict if the water-level will rise above the harbour wall and flood the loading dock. An associated question could be: "How likely is it, that the water will rise higher than the harbour wall next week?".

However, our model answers a different question, namely: "What is our best guess for next week's water-level?".

These questions sound similar. But, the former asks about an extreme event (water rising so high, that it floods the loading dock), while our model answers a question about a "typical" water-level on a day like tomorrow.

Our true question, and the question our model answers are not aligned. No matter how precise we are, we are shooting at the wrong target. Asking the correct (or at least a *better*) question is crucial.

Where do you need to ask better questions? 
Which questions are *buried* in your work?
