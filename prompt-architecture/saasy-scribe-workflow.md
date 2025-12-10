 Case Study: SaaSy Scribe ELITE - Multi-Stage Prompt Architecture

 Objective
Automate the entire content creation workflow for a SaaS blog post, from keyword input to a fully formatted, SEO-optimized 3,000-word article.

 The Challenge
A single prompt leads to generic, unstructured, and factually weak output. The task requires distinct phases of reasoning: research, planning, drafting, and polishing.

 My Solution: A 5-Stage Prompt Chain

 Stage 1: Strategy & Analysis
LLM Task: Analyze the primary keyword and user intent. Output a content strategy JSON.

```prompt
You are an SEO strategist. Analyze the keyword "{KEYWORD}" for a SaaS blog.
Output a JSON with: target_user_intent, secondary_keywords, content_angle, and competitor_weaknesses_to_exploit.
