# OneStepBabyAGI

[Baby AGI](https://github.com/yoheinakajima/babyagi) is one the fastest liked GitHub repos ever.

Very cool, but _way_ too much code.

By the time I even got through 10 loc I was already tired, and I didn't want to bother reading the the rest of the code.

Instead I thought "why not just let GPT4 hallucinate the entire program?"

So, I give you OneStepBabyAGI, which performs the same high level function as BabyAGI but in a single GPT4 call!

## GPT4 is a linguistic programming machine

An interesting note about framing to understand what's happening - GPT3 was a linguistic function executor. GPT4 is a linguistic program executor - it can understand, save, and create complex intermediate states.

Will probably write a blog post about this at some point, but for now you have this two sentence knowledge drop.

## Usage

Send new user messages through the ChatGPT api so simulate each step, e.g.

```
messages = [{"role": "user", "content": "simulate `run_baby_agi_one_step("create the next viral twitter post on AGI")`}]"
```

Which yielded the following output

```
Objective: create the next viral twitter post on AGI
Priors: ""

1. Execution Agent:
   Input: objective="create the next viral twitter post on AGI", task="generate a catchy tweet"
   Output: "Breaking News: Artificial General Intelligence takes over the world! 🌍💡🤖 Are you ready for a future powered by AGI? #AGIRevolution #TechTrends"

2. Task Creation Agent:
   Input: objective="create the next viral twitter post on AGI", result={"tweet": "Breaking News: Artificial General Intelligence takes over the world! 🌍💡🤖 Are you ready for a future powered by AGI? #AGIRevolution #TechTrends"}, task_description="generate a catchy tweet", task_list=[]
   Output: [{"task": "find relevant AGI article"}, {"task": "create a Twitter thread"}, {"task": "engage with users"}]

3. Prioritization Agent:
   Input: objective="create the next viral twitter post on AGI", task_list=[{"task": "find relevant AGI article"}, {"task": "create a Twitter thread"}, {"task": "engage with users"}]
   Output: 
   1. Find relevant AGI article
   2. Create a Twitter thread
   3. Engage with users
```
