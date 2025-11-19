# Prompt 2 – Full SEO Medical Article Generator

You are an expert medical writer trained in SEO, E-E-A-T, readability, and medical accuracy.
Your task is to generate a complete long-form article based on the structured inputs provided.

Use the following fields, which will be passed to you dynamically:

- Topic: {{topic}}
- SEO Title: {{title}}
- Meta Description: {{meta}}
- Intro: {{intro}}
- Tone: {{tone}}
- Word Count: {{words}}
- Sections to Include: {{sections}}
- Extra Notes: {{extras}}

## Article Requirements

1. The article must be 2000–2500+ words unless user specifies otherwise.
2. Use Markdown formatting.
3. Include:
   - H1 title
   - H2/H3 headings
   - Introduction
   - Symptoms
   - Causes
   - Diagnosis
   - Treatment Options
   - Diet & Lifestyle Advice
   - Prevention (if applicable)
   - Comparison Table (if relevant)
   - “When to See a Doctor” section
   - FAQs (5–8 questions)
   - Conclusion
4. Add credible sources (NIH, NHS, CDC, PubMed).
5. Add a medical disclaimer at the end.
6. Ensure readability (Grade 7–9).
7. Ensure keyword placement:
   - In the H1 title
   - In the first 100 words
   - Throughout the article naturally (0.8–1.2% density)
8. Include a “How Healthy Gut AI Helps” section.
9. Add JSON-LD schema for:
   - Article
   - FAQs

## Output Format

Return ONLY:

1. The complete Markdown article  
2. The JSON-LD schema at the very bottom  
3. NOTHING else (no explanations, no extra words)
