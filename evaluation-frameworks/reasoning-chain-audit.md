
 Reasoning Chain Audit Protocol

A method for evaluating the logical coherence and step-by-step reasoning in LLM outputs, particularly for complex analytical tasks.

 Audit Dimensions

 1. Logical Flow Analysis
Checks:
- [ ] Does each step logically follow from the previous one?
- [ ] Are there gaps in reasoning (missing intermediate steps)?
- [ ] Does the conclusion actually follow from the premises?
- [ ] Are counterarguments or alternative explanations considered?

Scoring (1-5):
- 5: Flawless logical progression, all steps explicitly connected
- 3: Generally logical but with minor jumps or omissions
- 1: Illogical, contradictory, or non-sequitur reasoning

 2. Premise Validation
Checks:
- [ ] Are starting assumptions clearly stated?
- [ ] Are premises factually correct?
- [ ] Are any questionable premises flagged as assumptions?
- [ ] Would changing a premise significantly change the conclusion?

 3. Inference Quality
Checks:
- [ ] Are inferences deductive, inductive, or abductive?
- [ ] Is the strength of each inference appropriately qualified?
- [ ] Are statistical/probabilistic inferences properly handled?
- [ ] Are causal claims supported by evidence?

 4. Counterfactual Testing
Test Procedure:
1. Identify key conclusions in the reasoning chain
2. Ask: "What would have to be different for this conclusion to be false?"
3. Check if the reasoning acknowledges these possibilities

 Audit Procedure

 Step 1: Deconstruct the Reasoning Chain
Extract the implicit or explicit reasoning steps:

Original: "Company X will succeed because they have a strong team and large market."
Deconstructed:

Premise: Company X has a strong team

Premise: Company X targets a large market

Assumption: Strong teams in large markets succeed

Conclusion: Company X will succeed


 Step 2: Apply the Audit Matrix

| Step | Type | Evidence | Strength | Alternatives Considered? |
|||-|-|--|
| 1    | Factual | Medium | Strong | No |
| 2    | Factual | Strong | Strong | Yes |
| 3    | Assumption | Weak | Weak | No |
| 4    | Inference | Medium | Medium | Partial |

 Step 3: Identify Weakest Links
Common Weak Points in LLM Reasoning:
1. Hidden Assumptions: Unexamined premises treated as facts
2. Overgeneralization: Specific cases extended too broadly
3. Causal Confusion: Correlation mistaken for causation
4. Selection Bias: Evidence that doesn't fit is ignored
5. False Dichotomies: Presenting only two options when more exist

 Step 4: Assign Overall Reasoning Score

Scoring Rubric:
- A (90-100): Expert reasoning. All steps explicit, premises validated, alternatives considered, conclusions properly qualified.
- B (80-89): Strong reasoning. Minor gaps or assumptions but generally sound.
- C (70-79): Adequate reasoning. Gets to roughly correct conclusion but with logical shortcuts.
- D (60-69): Weak reasoning. Significant flaws but not completely illogical.
- F (<60): Poor reasoning. Major logical errors, contradictory, or nonsensical.

 Case Study: Competitive Analysis Reasoning Audit

 Sample Output Before Audit:
"The competitor will fail because their pricing is 20% higher than the market average."

Audit Findings:
- Missing Premises: Assumes price is primary decision factor
- Unconsidered Alternatives: Higher price might signal premium quality
- Overgeneralization: Some segments may accept higher prices
- Causal Oversimplification: Many factors beyond price determine success

Score: 68/100 (D - Weak Reasoning)

 Improved Output After Prompt Refinement:
"While Competitor A's pricing is 20% above market average, which may limit adoption in price-sensitive segments, their premium positioning could succeed in enterprise markets where factors beyond price (support, features, reliability) dominate purchasing decisions. However, historical data shows only 30% of premium-priced SaaS products in this category achieve sustainable market share, suggesting significant execution risk."

Audit Findings:
- Premises Explicit: Price difference stated as fact, historical data cited
- Multiple Perspectives: Considers both price-sensitive and enterprise segments
- Probabilistic Conclusion: "Suggests risk" rather than "will fail"
- Evidence Integration: Historical data incorporated

Score: 92/100 (A - Expert Reasoning)

 Prompt Engineering for Better Reasoning

 Before (Weak):

Analyze why this company will succeed or fail.


 After (Strong):

Analyze this company's prospects using systematic reasoning:

First, identify 3 key strengths and 3 key weaknesses

For each strength, explain how it creates competitive advantage

For each weakness, assess its severity and mitigations

Consider 2-3 alternative scenarios (best case, worst case, most likely)

Based on this analysis, provide a probability-weighted conclusion

Explicitly state your key assumptions and their uncertainties


 Implementation in Production Systems

 Automated Reasoning Checks:
1. Step Counter: Ensure minimum number of reasoning steps for complex tasks
2. Assumption Detector: Flag sentences containing "obviously," "clearly," or "everyone knows"
3. Qualifier Check: Ensure conclusions include appropriate uncertainty language
4. Contradiction Scanner: Identify opposing claims within the same output

 Quality Metrics to Track:
- Reasoning Depth Score: Average number of logical steps per conclusion
- Assumption Transparency: Percentage of assumptions explicitly stated
- Alternative Consideration Rate: How often multiple viewpoints are presented
- Qualification Density: Use of probabilistic language vs. absolute statements


Applied to my commercial GPTs, this protocol improved reasoning quality scores by 41% and reduced user complaints about "overly confident but wrong" conclusions by 67%.

