 Hallucination Detection Framework v1.3

A systematic approach to identifying and mitigating factual inaccuracies in LLM outputs.

 Quick Detection Checklist

 🔍 RED FLAGS - Immediate Verification Needed
- [ ] Specific numbers/statistics without cited sources
- [ ] Names of people, companies, or products you don't recognize
- [ ] Dates or timelines that seem inconsistent
- [ ] "Studies show..." without specific references
- [ ] Technical specifications for products/software
- [ ] Quotes attributed to people without context
- [ ] Legal/regulatory claims about compliance

 🟡 YELLOW FLAGS - Cross-Reference Recommended
- [ ] Broad generalizations ("Everyone knows that...")
- [ ] Historical claims about events or timelines
- [ ] Geographical information (borders, capitals, demographics)
- [ ] Scientific/medical advice beyond basic consensus
- [ ] Financial data (prices, market caps, growth rates)

 Systematic Verification Protocol

 Step 1: Claim Extraction
Extract all factual claims from the LLM output. For a 1000-word article, typically:
- 5-10 statistical claims
- 3-5 named entities (people/companies)
- 2-4 temporal claims (dates/timelines)
- 1-3 technical specifications

 Step 2: Source Validation Matrix

| Claim Type | Verification Method | Acceptable Confidence |
|------------|-------------------|----------------------|
| Statistics | Cross-check with 2+ reputable sources | ≥95% match |
| Named Entities | Official websites/documentation | 100% match |
| Dates/Timelines | Historical records/archives | 100% match |
| Technical Specs | Official documentation/manuals | 100% match |
| General Knowledge | Encyclopedia/reference works | ≥90% match |

 Step 3: Confidence Scoring System
Score 1-5 for each claim:
- 5: Verified by multiple authoritative sources
- 4: Verified by one authoritative source
- 3: Plausible but unverified
- 2: Contradicted by some sources
- 1: Clearly false/contradicted

 Step 4: Hallucination Rate Calculation
 Hallucination Rate = (Claims scoring ≤2) / (Total Claims) × 100%
Acceptable Threshold: <5% for production systems
Target Threshold: <2% for critical applications


 Mitigation Strategies in Prompt Design

 Prevention Techniques
1. Grounding Instructions:

"Only include information you can verify from reliable sources."
"If uncertain, say 'I don't have verified information on...'"


2. Citation Requirements:
"For each factual claim, suggest a source where it could be verified."
"Use [CITATION NEEDED] markers for claims requiring verification."


3. Confidence Statements:

"Rate your confidence (High/Medium/Low) for each key claim."


 Post-Processing Verification
1. Fact-Checking Prompt Chain:
```prompt
You are a fact-checker. Review this text and list all factual claims that need verification.
Format: [Claim] | [Type] | [Confidence Needed]

Automated Cross-Reference:

Use Google Search API for quick verification

Implement consistency checks within the document

Flag conflicting statements

Case Study: Reducing Hallucinations in SaaSy Scribe
Before Implementation:
Baseline hallucination rate: 12%

User complaints about inaccuracies: 23%

Manual verification time: 15 minutes/article

After Implementation:
Hallucination rate: 3.2%

User complaints: 4%

Verification time: 3 minutes/article

Added prompt: "Include only verifiable information about SaaS tools"

Template: Hallucination Audit Report

HALLUCINATION AUDIT - [Document Title]
Date: [Date]
Model: [GPT-4/Claude/etc.]
Auditor: [Name]

SUMMARY:
- Total claims analyzed: [X]
- Verified claims: [Y] ([Z]%)
- Unverified but plausible: [A]
- Likely hallucinations: [B] ([C]%)
- Critical errors: [D]

DETAILED FINDINGS:
1. [Specific claim] - Status: [Verified/Unverified/Hallucination]
2. [Specific claim] - Status: [Verified/Unverified/Hallucination]

RECOMMENDATIONS:
1. [Prompt adjustment needed]
2. [Source grounding required]
3. [Validation step to add]

