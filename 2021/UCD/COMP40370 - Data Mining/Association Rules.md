---
tags: COMP40370 - Data Mining
---

# Association Rules

> Data mining seems like such a depressing field to go into..
> Reddit 100% is a biased sample, but I feel as if  a lot of data mining people get super depressed and dead inside after a short bit in the industry

## Learning Objectives
- Understand the concept of association rules
- Define and use support and confidence measures
- Assication Rules Analysis
	- Apriori Algorithm
	- FP Growth Algorithm

## WHat is Assocation Mining?

- **Association Rule Mining**
	- Finding frequent patterns, assocations, correlations, or casual structures among sets of items or objects in transcaation databases, realtionshal databases, and other informational repositories
- **Applications**
	- Basket data analysis, cross-marketing, catalog design, loss-leader analysis, clusering, classification, etc
- Examples:
	- Rule form: Body -> Head [Support, Confidence]
	- buys(x, "Pizza") -> buys(x, "beers")[0.5%. 60%]
	- major(x, "CS") ^ takes(x, "DB") -> grade(x, "A")[1%, 75%]

## Assocation Rule: Basic Concepts
- Given:
	- A set of transactions
	- Each transactions is  alist of items
- Find **all** rules that correlate the presence of one set of items with that of another set of items
	- e.g. 95% o people who purchase ready meals also purchase sort drinks
- Applications
	- **Maintenance Agreement**: What the store should do to boost Maintenance Agreement sales)
	- **Small Groceries**: (What other products should the store stock up on?)
	- **Attached mailing** in direct marketing

## Rule Measures: Support and Confidence
- Find all the rules Y -> Z with minimum confidence and support
	- support, s, probability that a transaction contains {y -> z}
	- confidence, c, conditional probability that a transaction having Y alos conains Z

## AR Mining: A Road Map
- Boolean vs quantitative associations
	- Based on the types of values handled
- Single dimension vs multiple dimensional associations
- Single level vs multiple-level analysis
- Various extensions
	- Correlation, causaliy analysis
	- Max patterns and closed itemsets
	- Constrants enforced
