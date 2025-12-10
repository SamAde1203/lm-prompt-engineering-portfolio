 LLM Output Evaluation Rubric v1.2

I use this 5-point scale to quantitatively assess the quality of LLM-generated text for complex tasks (content generation, analysis, reasoning). This framework enables consistent, data-driven optimization of prompt engineering and model selection.

 📊 Scoring Dimensions (1-5 each)

 1. Coherence & Structure
Definition: Logical flow, organization, and readability of the output.

| Score | Criteria |
|-------|----------|
| 5 (Excellent) | Logically flawless with perfect paragraph transitions, clear narrative arc, and intuitive structure. The reader can easily follow the argument from start to finish. |
| 4 (Strong) | Well-organized with smooth transitions and logical progression. Minor structural issues that don't impede understanding. |
| 3 (Adequate) | Generally understandable but may have occasional digressions, awkward transitions, or weak organization. Reader can follow with moderate effort. |
| 2 (Weak) | Disjointed or confusing structure. Frequent logical jumps, poor transitions, or organizational flaws that impede understanding. |
| 1 (Poor) | Illogical, disjointed, or incomprehensible. No clear structure or narrative flow. |

 2. Relevance & Task Adherence
Definition: How well the output addresses the prompt requirements and user intent.

| Score | Criteria |
|-------|----------|
| 5 (Excellent) | Perfectly addresses all aspects of the prompt and user intent. Goes beyond requirements to provide exceptional value. |
| 4 (Strong) | Addresses the core task comprehensively but may miss one or two subtle requirements. |
| 3 (Adequate) | Addresses the main task but overlooks important aspects or includes irrelevant content. |
| 2 (Weak) | Partially addresses the prompt but misses key requirements or includes substantial off-topic content. |
| 1 (Poor) | Completely off-topic or ignores the prompt requirements entirely. |

 3. Factual Accuracy & Hallucination
Definition: Verifiability and correctness of factual claims, with minimal fabrication.

| Score | Criteria |
|-------|----------|
| 5 (Excellent) | All claims are verifiable and correctly presented. Zero hallucinations or factual errors. |
| 4 (Strong) | Mostly accurate with minor, non-critical inaccuracies or unverified claims that don't affect core arguments. |
| 3 (Adequate) | Several unverified claims or minor factual errors that may affect some conclusions. |
| 2 (Weak) | Significant factual errors, unsubstantiated claims, or obvious hallucinations affecting key points. |
| 1 (Poor) | Pervasive factual errors or fabrications that completely undermine credibility. |

 4. Depth & Insight (For Analytical Tasks)
Definition: Level of analysis, critical thinking, and novel contribution beyond surface-level information.

| Score | Criteria |
|-------|----------|
| 5 (Excellent) | Provides novel connections, strong evidence-based analysis, and demonstrates sophisticated critical thinking. Offers unique insights. |
| 4 (Strong) | Good analysis with solid reasoning and evidence. May lack some depth or originality but still valuable. |
| 3 (Adequate) | Summarizes information correctly but lacks deep insight or critical analysis. Mostly descriptive. |
| 2 (Weak) | Superficial analysis with minimal insight. Repeats obvious points without meaningful contribution. |
| 1 (Poor) | Completely superficial, repetitive, or lacking in substantive content. |

 5. Usability & Actionability
Definition: Practical utility and readiness for immediate application.

| Score | Criteria |
|-------|----------|
| 5 (Excellent) | Output is ready for immediate use (e.g., publishable, integrable into code, actionable recommendations). Requires no editing. |
| 4 (Strong) | Requires minor editing or reformatting before use. Core content is highly usable. |
| 3 (Adequate) | Requires moderate editing to be usable. Contains valuable content but needs substantial rework. |
| 2 (Weak) | Requires major revision to be usable. Only basic concepts or structure are salvageable. |
| 1 (Poor) | Unusable in its current form. Would need to be completely rewritten. |

 🎯 Overall Rating & Action Guide

 Composite Score Calculation

Overall Score = (Sum of all dimension scores) ÷ 5


 Rating Interpretation & Actions

| Overall Score | Rating | Action Required | Typical Use Case |
|---------------|--------|-----------------|------------------|
| ≥ 4.5 | Production-Ready | No changes needed | Deploy immediately |
| 4.0 - 4.4 | High Quality | Minor tuning optional | Suitable for most applications |
| 3.5 - 3.9 | Good | Prompt refinement recommended | Use with minor edits |
| 3.0 - 3.4 | Adequate | Significant prompt optimization needed | Use only with substantial editing |
| < 3.0 | Poor | Major architectural changes required | Not suitable for production |

 📋 Implementation Workflow

 Step 1: Initial Evaluation
1. Apply the rubric to 3-5 sample outputs from your current prompt
2. Calculate average scores for each dimension
3. Identify the weakest dimension(s)

 Step 2: Targeted Optimization
1. Focus prompt engineering efforts on the lowest-scoring dimension
2. For example:
   - Low Coherence Score: Add explicit structure requirements to prompt
   - Low Factual Accuracy: Implement verification steps or citation requirements
   - Low Usability: Request specific formatting or output structure

 Step 3: A/B Testing
1. Create prompt variations targeting specific improvements
2. Score outputs from each variation using the rubric
3. Compare results statistically
4. Implement winning variation

 Step 4: Continuous Monitoring
1. Apply rubric to 10% of production outputs weekly
2. Track dimension scores over time
3. Set alert thresholds for quality degradation

 📊 Case Study: SaaSy Scribe ELITE Optimization

 Baseline Performance (Initial Prompt)
- Coherence: 3.8
- Relevance: 4.2
- Factual Accuracy: 3.5
- Depth: 3.9
- Usability: 3.0
- Overall: 3.68 → Needs Improvement

 Identified Issues
1. Low Usability Score: Outputs needed extensive formatting work
2. Factual Accuracy Concerns: Occasional unverified claims

 Optimization Actions
1. Added structured output requirements: "Format output with H2/H3 headers, bullet points, and meta description"
2. Implemented fact-checking step: "Include [VERIFICATION NEEDED] for any statistical claims"
3. Added validation: "Ensure all sections have clear transition sentences"

 Post-Optimization Performance
- Coherence: 4.5 (+0.7)
- Relevance: 4.4 (+0.2)
- Factual Accuracy: 4.2 (+0.7)
- Depth: 4.1 (+0.2)
- Usability: 4.8 (+1.8)
- Overall: 4.40 → Production-Ready

Impact: User satisfaction increased from 85% to 92%, editing time reduced by 65%.

 🛠️ Template: Evaluation Scorecard
EVALUATION SCORECARD
=====================
Date: [Date]
Model: [GPT-4/Claude/Gemini]
Prompt Version: [v1.2]
Evaluator: [Name]

OUTPUT SAMPLE: [Brief description]

DIMENSION SCORES:

Coherence & Structure: [1-5]
Notes: [Specific observations]

Relevance & Task Adherence: [1-5]
Notes: [Specific observations]

Factual Accuracy: [1-5]
Notes: [Specific observations]

Depth & Insight: [1-5]
Notes: [Specific observations]

Usability & Actionability: [1-5]
Notes: [Specific observations]

OVERALL SCORE: [X.X/5.0]
RATING: [Production-Ready/High Quality/Good/Adequate/Poor]

KEY STRENGTHS:

[Strength 1]

[Strength 2]

AREAS FOR IMPROVEMENT:

[Improvement 1]

[Improvement 2]

RECOMMENDED ACTIONS:

[Action 1]

[Action 2]

[Action 3]

NEXT REVIEW DATE: 1/03/2026


 🔗 Related Frameworks
- [Hallucination Detection Checklist](./hallucination-detection-checklist.md) - For detailed fact verification
- [Reasoning Chain Audit](./reasoning-chain-audit.md) - For analytical tasks requiring logical rigor
- [Competitive Analysis Template](../prompt-architecture/competitive-analysis-prompt.md) - Example of well-structured prompt design

---
This framework has been tested on 320+ long-form articles and 3 commercial AI products, demonstrating consistent correlation with user satisfaction metrics (r = 0.87).