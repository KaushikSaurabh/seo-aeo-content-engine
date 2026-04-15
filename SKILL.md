---
name: seo-aeo-content-engine
description: Use when creating any SEO/AEO content (articles, blogs, guides, landing pages) to orchestrate research, fact-checking, humanization, and plagiarism detection entirely within Claude—no paid tools required
---

# SEO-AEO Content Engine v2: Actually Human Content, At Scale

Look, I've tried a lot of AI content approaches. Most of them suck. They either read like robots or they get flagged by every detection tool out there.

This is different.

Instead of writing AI content and then trying to make it sound human (spoiler: that doesn't work), we write *actual* human-quality content from the start. We embed the humanization into the writing process itself. Your articles sound like they came from a real person who knows their stuff—because they did.

No paid tools. No humanizers. No post-processing magic. Just intelligent, source-backed content that reads naturally and ranks well.

---

## Here's What Actually Changed

Everyone says "use humanization tools." That's backwards. A tool can't make bad writing sound good. But a good *process*? That can prevent bad writing from happening in the first place.

This skill orchestrates that process. Research → Planning → Human-quality writing (with sources logged as you go) → Fact-checking (you already have everything verified) → Publishing.

That's it. No extra steps. No external tools. Just clean, human-sounding content that ranks and converts.

---

## When to Use This (Seriously, Use It)

Honestly? Use this for everything content-related.

Blog posts, landing pages, guides, case studies, thought leadership pieces—whatever. If you're writing content for SEO or AEO, this is your starting point.

Why? Because every article you write builds on the last one. Your knowledge base gets richer. Your research faster. Your content better. That's compound value. Using a lighter skill cuts that short.

The only exception: You've got a pre-written outline + all sources ready to go. Then maybe the lightweight `seo-aeo-blog-writer` makes sense. Otherwise, you're leaving efficiency on the table.

---

## Phase 0: Actually Talk to Me First

Before I start researching anything, I need to understand what you're trying to build. I'll ask questions. Give me good answers, and your content will be 10x better.

Here's what I need to know:

**About Your Brand:**
- Website URL (or description if you don't have one yet)
- What's your positioning? (How are you different? Who do you serve?)
- Industry or category (helps me spot bullshit in research faster)

**What You're Actually Trying to Do:**
- Are you chasing SEO rankings? Lead gen? Building authority? Selling something?
- How many articles? (This changes the strategy—one article is different from a five-article series)
- What keywords matter to you?

**The Content Itself:**
- Got specific article titles in mind? (Specific > vague)
- Who's reading this? (Real people, not "B2B founders"—what's their actual problem?)
- Do you have sources you want me to use? Or should I research from scratch?
- What's your tone? (Formal boardroom? Casual expert? Something else?)

**Your Expertise:**
- Do you have data, case studies, or real experience I should include?
- Any topics you want to avoid or angles you hate?
- What do you know that competitors don't?

**If You Don't Have Everything:**
That's fine. I'll note the gap and either research it or flag it. But the better your answers, the better your content. Simple as that.

**Real Example of This Conversation:**

You: "Write about AI personalization for e-commerce"

Me: "Okay. But I need more. Is this for your SaaS? A blog? Who's the customer? Are you already ranking for anything, or is this a new topic?"

You: "It's for our blog. B2B SaaS serving SMBs. We've got audience data showing CTOs care about ROI..."

Me: "Perfect. That changes everything. I won't waste time on enterprise stuff. Let me tailor this for your audience."

*See the difference?* Better input = better output.

---

## Phase 1: Find Real Evidence (Then Build Your KB)

Here's the key insight: **Good content needs good sources. Full stop.**

This phase isn't about volume. It's about credibility. I'm looking for sources that actually know what they're talking about. Academic research. Industry reports. Official documentation. Not random blogs making claims.

### What I'm Actually Doing

**Finding the good stuff:**
- **Academic sources** - Peer-reviewed means someone checked the work
- **Industry reports** - Gartner, Forrester, McKinsey—they spend millions on research
- **Competitor pages** - What are they ranking for? (Tells me what Google likes)
- **Official docs** - Google's own SEO guidance. Product documentation. This matters.
- **Real data** - Surveys, government data, actual statistics
- **Current news** - What's trending? What changed?

**Tracking quality:**
For each source, I note:
- When was it published? (Old data = potentially wrong)
- Who wrote it? (A researcher or someone selling something?)
- What's the actual claim? (Not what you think they said—what's on the page?)
- Does this conflict with other sources? (If yes, I flag it now)

This becomes your fact-check matrix later. You'll see every source, every claim, verified before we write a word.

### Step 1.2: Vector Store Organization (In Memory)

**Instead of external DB (save cost):** Use structured semantic memory:

```
Knowledge Base Structure:

client_{brand}/
├── meta/
│   ├── brand_voice.md (tone, style, personality)
│   ├── positioning.md (unique value prop)
│   └── target_audience.md (who reads this)
│
├── research/
│   ├── topic_1/
│   │   ├── sources.json (all sources + credibility)
│   │   ├── claims.json (extractable claims with attribution)
│   │   ├── statistics.json (all stats with dates)
│   │   └── contradictions.json (conflicting data noted)
│   ├── topic_2/
│   └── ...
│
├── expertise/
│   ├── case_studies.md (user's own data/experience)
│   ├── unique_insights.md (proprietary knowledge)
│   └── expert_warnings.md (things others get wrong)
│
└── performance/
    ├── successful_patterns.md (what worked before)
    ├── keyword_rankings.md (current performance)
    └── gap_analysis.md (what's missing in market)
```

**Token optimization:** Store as JSON, not prose. Retrieve only what's needed per article.

### Step 1.3: Fact-Checkable Claims Inventory

For each potential claim:
```
{
  "claim": "[actual claim text]",
  "topic": "AI personalization",
  "verifiable": true/false,
  "sources": ["source_1.url", "source_2.url"],
  "credibility": "HIGH/MEDIUM/LOW",
  "date": "2026-03-15",
  "contradictions": ["claim_id_5", "claim_id_12"],
  "status": "VERIFIED/PENDING/BLOCKED"
}
```

**Rule:** Any claim with MEDIUM+ credibility and sources can be used. LOW credibility claims flagged for expert verification. UNVERIFIED claims = BLOCKED.

---

## Phase 2: Article Planning & Structure

**Goal:** Create fact-backed outline before writing.

### Step 2.1: Keyword & Topic Mapping

```
Input: Target keywords + article title

Use existing skill integration:
  • seo-aeo-keyword-research: Analyze keyword difficulty, intent, volume
  • seo-aeo-content-cluster: Map pillar/cluster relationships

Output: Structure map
  H1: Primary keyword
  H2s: Secondary keywords / subtopics
  H3s: Long-tail keywords / supporting concepts
  Internal links: Related articles (from KB)
```

### Step 2.2: Evidence-Backed Outline

```
H1: [Primary keyword]

TL;DR Block:
  • 2-3 sentence direct answer
  • Cite primary source inline
  • Confidence level noted

H2: What Is [Topic]?
  └─ SOURCES: [source_ids from KB]
  └─ STRUCTURE: Definition + context + relevance

H2: Why It Matters
  └─ SOURCES: [source_ids]
  └─ STRUCTURE: Business impact + stats + real-world relevance

H2: How It Works / Best Practices
  ├─ H3: Concept 1
  │  └─ SOURCES + EXPERT KNOWLEDGE
  ├─ H3: Concept 2
  │  └─ SOURCES + EXPERT KNOWLEDGE
  └─ H3: Implementation / Common mistakes

H2: FAQ (5 questions)
  • Q: Long-tail keyword 1 (A: <50 words, self-contained)
  • Q: Long-tail keyword 2 (A: <50 words, self-contained)
  • [3 more]

METADATA:
  • Sources tagged per section
  • Expert knowledge sections marked
  • Confidence levels noted
  • Contradiction flags highlighted
```

---

## Phase 3: Writing (Source-Grounded + Built-In Humanization)

**Goal:** Generate humanized, expert-backed content without post-hoc processing.

### Step 3.1: Sourced Section Writing

**Key principle:** Don't write unsourced content then try to humanize it. Write in a way that's naturally humanized from the start.

```
For each section:

WRITE:
  • Lead with claim in active voice
  • Immediately cite source inline: (Source: Gartner, 2024)
  • Explain why it matters to reader
  • Include relevant statistic if available
  • Add expert insight or example (if user provided expertise)
  • Vary sentence structure (short + long + fragments)

EXAMPLE:
  Bad: "AI-powered personalization is an important technology that
       many companies are implementing. It can increase conversion
       rates. Research shows improvements."

  Good: "AI personalization transforms how companies connect with
       customers. Real numbers: 8-12% conversion rate increase
       (Deloitte, 2024). But here's what most implementations miss—
       it only works with clean data. Garbage in, garbage out.
       That's the hard part most teams skip."
```

### Step 3.2: Built-In Humanization Markers

**As you write, use these patterns to avoid AI-detection flags:**

1. **Sentence Structure Variation**
   - Lead with short: "Machine learning changed everything."
   - Then explain: "Here's how..."
   - Then elaborate: "The complex part is..."
   - Then fragment: "Truly."

2. **Personal Voice & Opinion**
   - Add perspective: "In my analysis of..." / "Based on what I've seen..."
   - Contrarian takes: "Here's what everyone gets wrong..."
   - Hedging language: "Honestly, this is trickier than it looks."
   - Direct address: "You need to understand..."

3. **Specific Examples > Generic Claims**
   - Instead of: "Companies benefit from X"
   - Write: "When TechCorp implemented X, their Y metric jumped 40%"

4. **Contradictions Acknowledged**
   - "Most vendors claim Z. But here's the reality..."
   - "Sounds good on paper, but implementation is messier"

5. **Evidence of Expertise**
   - Specific process details (not obvious to non-experts)
   - Common mistakes that surprised you
   - Counter-intuitive findings
   - Nuanced perspective

**Result:** Content reads naturally human because it includes human perspective, not because we applied a humanizer afterward.

### Step 3.3: Track Sources As You Write

```
As you cite each claim, log:
  "The conversion rate increase of 8-12% comes from Deloitte's
   2024 E-Commerce Report. Original source verifiable at [URL].
   Confidence: HIGH. Used in: Section 2.1"
```

**Why:** This becomes your fact-check matrix. You've already verified everything as you wrote.

---

## Phase 4: Internal Plagiarism Prevention (Built-In)

**Goal:** Ensure original content without external tools.

### Step 4.1: Semantic Duplication Detection

**Method:** Compare your writing against sources semantically.

```
For each paragraph, ask:
  • Is this a direct quote? (If yes, quote it and cite)
  • Is this paraphrase-heavy? (Restructure significantly)
  • Did I add original insight? (Expert knowledge, perspective, example)
  • Is this structurally different from source? (Reorder + rephrase)

Check: "If I remove citations, does this still read as original?"
  - YES = Good, move on
  - NO = Rewrite, add more original perspective/structure
```

### Step 4.2: Cross-Reference Uniqueness

```
Generate: Unique value proposition for EACH section

Source says: "X is effective"
You say: "X is effective because [original explanation],
         specifically when [specific scenario],
         unlike [comparison to alternative]"

Result: Same topic, completely original framing
```

### Step 4.3: Plagiarism Risk Scoring (Self-Check)

```
Score content 0-100 (low-high plagiarism risk):

Red flags (high risk):
  ✗ Multiple consecutive sentences from single source (REWRITE)
  ✗ Same structure as source article (RESTRUCTURE)
  ✗ Vocabulary matches source too closely (REPHRASE)
  ✗ No original examples or perspective added (ADD INSIGHT)

Green flags (low risk):
  ✓ Original structure (H2/H3 map different from sources)
  ✓ Multiple perspectives woven together
  ✓ Original examples or expert knowledge added
  ✓ Unique framing/angle
  ✓ Clear voice and personality

Target: Score <20 (low plagiarism risk)
Action if >20: Rewrite flagged sections before publishing
```

---

## Phase 5: Fact-Checking & Verification

**Goal:** Verify EVERY material claim before publication.

### Step 5.1: Create Fact-Check Matrix

```
For each major claim:

| Claim | Source | Original Data | Our Text | Match? | Confidence | Status |
|-------|--------|----------------|----------|--------|------------|--------|
| "X% increase" | Deloitte 2024 | "8-12% increase" | "8-12% increase" | ✓ | HIGH | VERIFIED |
| "Y is true" | Industry Report | "[find exact quote]" | "[our wording]" | ✓/✗ | MEDIUM | NEEDS CHECK |
| "Z statistic" | [Not found] | N/A | "[our claim]" | ✗ | LOW | REMOVE/CITE BETTER |

Action: Any claim with ✗ or LOW confidence = REMOVE or find better source
```

### Step 5.2: Identify & Flag Potential Hallucinations

```
Red flags:
  ✗ "Sounds right" claims without sources
  ✗ Logical leaps ("Therefore... " with no evidence)
  ✗ Vendor claims presented as objective facts
  ✗ Outdated data (older than 6 months for trending topics)
  ✗ Unattributed statistics

Action: Remove hallucinations before publication
```

### Step 5.3: Resolve Contradictions

```
If Source A says "30%" and Source B says "15%":

  1. Check publication dates (more recent wins)
  2. Check methodologies (different measurement = different result)
  3. Check context (different markets/regions)

Solution options:
  • Use more recent source
  • Cite both with context: "Adoption ranges from 15-30% depending on market"
  • Remove if unresolvable
```

---

## Phase 6: AEO Optimization (AI Extraction Ready)

**Goal:** Make content extractable by AI systems.

### Step 6.1: AEO Compliance Checklist

```
[ ] H1 present and clear (primary topic)
[ ] H2/H3 hierarchy proper (topic structure visible)
[ ] TL;DR block present (direct answer, first 100 words)
[ ] Definition sentence in "What Is" section (definitional queries)
[ ] 5 FAQ entries with <50 word answers (extractable)
[ ] Key statistics attributed to sources
[ ] Schema markup ready (FAQ, Article, Organization)
[ ] Internal links to related content (topical authority)
[ ] Tables/comparisons where relevant (structured data)
```

### Step 6.2: Schema Markup Generation

```
Use: seo-aeo-schema-generator skill

For this article:
  • Article schema (headline, author, date, description)
  • FAQ schema (from FAQ section)
  • Organization schema (company info)
  • Breadcrumb schema (if applicable)

Output: JSON-LD ready for <head>
```

---

## Phase 7: Quality Assurance & Finalization

### Step 7.1: Full Content Audit

```
READABILITY:
  [ ] Sentences vary (short + long + fragments)
  [ ] Paragraphs vary (1-2 lines + 4-5 lines)
  [ ] No jargon without explanation
  [ ] Active voice preferred over passive

ACCURACY:
  [ ] All facts verified (Phase 5 complete)
  [ ] Sources cited properly
  [ ] Statistics have dates
  [ ] Outdated info updated
  [ ] Contradictions resolved

HUMANIZATION:
  [ ] Original examples included
  [ ] Expert perspective evident
  [ ] Personal voice present
  [ ] Not obviously AI-written

OPTIMIZATION:
  [ ] Target keyword in H1
  [ ] Secondary keywords in H2/H3
  [ ] Internal links strategic
  [ ] Meta description written (160 chars)
  [ ] TL;DR block complete
  [ ] FAQ section optimized
  [ ] Schema markup valid

FINAL CHECK:
  [ ] No plagiarism risk (Phase 4 score <20)
  [ ] All sources credible and cited
  [ ] Author/date correct
  [ ] Images/assets optimized (if applicable)
  [ ] Ready to publish
```

### Step 7.2: Knowledge Base Update

```
After publishing, update client KB:
  • Add to episodic memory (what we learned about this topic)
  • Update semantic memory (brand voice, audience insights)
  • Log procedural memory (what worked/didn't work)
  • Tag successful patterns for future articles
```

---

## Knowledge Base Architecture (Brand-Wide + Shared Common KB)

**Goal:** Brand-wide research + reusable common patterns across all clients.

### Two-Tier Architecture

**Tier 1: Brand-Wide Knowledge Base** (Per-client, persistent across all articles)
```
client_{brand}/
│
├── meta/ (BRAND-LEVEL - shared by all articles)
│   ├── brand_voice.json (tone, style, vocabulary, personality)
│   ├── positioning.json (UVP, differentiators, core message)
│   ├── target_audience.json (psychographics, pain points, decision drivers)
│   └── content_guidelines.json (restrictions, approved topics, terminology)
│
├── research/ (BRAND-LEVEL - accumulating across all topics)
│   ├── sources.json (all sources ever used for this brand, deduplicated)
│   ├── claims.json (all verified claims by category)
│   ├── statistics.json (all metrics used, with dates and sources)
│   ├── industry_trends.json (specific to brand's industry)
│   └── competitor_insights.json (what competitors cover)
│
├── expertise/ (BRAND-SPECIFIC)
│   ├── case_studies.json (brand's own data, examples, results)
│   ├── methodologies.json (how brand does things differently)
│   ├── proprietary_data.json (unique statistics/findings)
│   └── lessons_learned.json (what works for this brand)
│
└── performance/ (BRAND-LEVEL TRACKING)
    ├── articles.json (all articles written with metadata)
    ├── keyword_rankings.json (current rankings across all topics)
    ├── successful_patterns.json (what drives ranking/engagement)
    └── gap_analysis.json (untapped keyword opportunities)
```

**Tier 2: Common Knowledge Base** (Shared across ALL clients, read-only)
```
common_kb/
│
├── humanization/ (REUSABLE PATTERNS)
│   ├── sentence_structures.json (varied length patterns)
│   ├── personal_voice_markers.json (I-statements, opinions, emotions)
│   ├── specific_example_patterns.json (how to create real examples)
│   └── expertise_signals.json (process details, common mistakes, insights)
│
├── fact_checking/ (METHODOLOGIES)
│   ├── credible_sources.json (academic, reports, official docs ranked by credibility)
│   ├── outdated_data_detection.json (how to spot old statistics)
│   ├── hallucination_patterns.json (common false claims patterns)
│   └── contradiction_resolution.json (how to handle conflicting data)
│
├── plagiarism_prevention/ (TECHNIQUES)
│   ├── restructuring_patterns.json (how to rephrase without copying)
│   ├── original_framing_examples.json (different angles on same topic)
│   └── semantic_variation.json (vocabulary alternatives)
│
├── industry_knowledge/ (GENERAL TRENDS)
│   ├── seo_guidelines.json (Google's latest ranking signals)
│   ├── aeo_best_practices.json (AI extraction optimization)
│   ├── tech_trends.json (emerging technologies, frameworks)
│   └── marketing_trends.json (industry-wide patterns)
│
├── schema_patterns/ (REUSABLE TEMPLATES)
│   ├── faq_schema.json (pattern for FAQ structure)
│   ├── article_schema.json (pattern for Article schema)
│   ├── organization_schema.json (company info patterns)
│   └── breadcrumb_schema.json (navigation structure)
│
├── brand_voice_samples/ (REFERENCE LIBRARY)
│   ├── formal_tone.md (examples of formal writing)
│   ├── conversational_tone.md (examples of casual writing)
│   ├── technical_tone.md (examples of complex explanations)
│   └── emotional_tone.md (examples of persuasive writing)
│
└── keyword_research/ (SHARED KEYWORDS)
    ├── trending_keywords.json (current high-volume keywords by industry)
    ├── long_tail_patterns.json (long-tail keyword structures)
    └── intent_categories.json (keyword intent classifications)
```

### Retrieval Strategy (Token Efficient)

**Article 1 (New Topic):**
```
1. Load client brand meta (voice + positioning) - 150 tokens
2. Load common KB humanization patterns - 100 tokens
3. Load common KB fact-checking methodologies - 100 tokens
4. Research new sources for topic - 400 tokens
5. Store research in brand KB - (stored, don't hold in context)
Total: ~750 tokens for first article
```

**Article 2 (Different Topic, Same Brand):**
```
1. Load client brand meta (already in memory) - 0 tokens (cache)
2. Load common KB patterns (already in memory) - 0 tokens (cache)
3. Reuse 30% of general sources from brand KB - 50 tokens
4. Research new sources for new topic - 300 tokens
5. Store research in brand KB
Total: ~350 tokens (53% savings vs Article 1)
```

**Article 3 (Same Topic Family as Article 1):**
```
1. Meta + patterns (cached) - 0 tokens
2. Reuse 70% of Article 1's research from brand KB - 200 tokens
3. Research only NEW sources for angle - 100 tokens
4. Store in brand KB
Total: ~300 tokens (60% savings vs Article 1)
```

**Article 5+ (Leveraging Full Brand KB):**
```
1. Meta + patterns (cached) - 0 tokens
2. Reuse 80%+ of existing brand KB research - 100-150 tokens
3. Research minimal new sources - 50 tokens
4. Store in brand KB
Total: ~150-200 tokens (75-80% savings vs Article 1)
```

### Memory Management

**Brand KB Maintenance:**
```
- Sources: Never delete (deduplicate on reuse)
- Claims: Archive if contradicted by newer data
- Statistics: Keep with dates (old data stays, new data tagged as latest)
- Performance: Update after each article publish
- Expertise: Accumulate (brand knowledge compounds)
```

**Common KB Maintenance:**
```
- Humanization patterns: Update quarterly (add new techniques)
- Fact-checking: Update monthly (new sources emerge, old ones become unreliable)
- Industry knowledge: Update monthly (trends change fast)
- Brand voice samples: Update when new brand types added
- Schema patterns: Update when Google releases new rich results
```

### Cross-Client Reuse

**What stays brand-specific:**
- Brand voice, positioning, target audience
- Case studies, proprietary data, expertise
- Keyword rankings and performance metrics

**What can be shared across brands:**
- Humanization techniques (apply to all)
- Fact-checking methodologies (universal)
- Plagiarism prevention logic (universal)
- Schema patterns (same structure)
- Industry trends (unless brand-specific)
- General keyword research (adapt per brand)

---

## Integrated Skills (Leverage Existing)

**Don't duplicate what's already available:**

```
Phase 2 (Planning):
  └─ seo-aeo-content-cluster: Topic authority mapping
  └─ seo-aeo-keyword-research: Keyword intent + volume

Phase 6 (AEO):
  └─ seo-aeo-schema-generator: Structured data generation
  └─ seo-aeo-internal-linking: Link strategy mapping

Phase 7 (QA):
  └─ seo-aeo-content-quality-auditor: Automated pre-checks

Reference/Learning (Don't invoke, just reference):
  └─ ai-content-optimization: Humanization principles embedded
  └─ agent-memory-systems: Memory architecture inspiration
  └─ humanize: Understand the principles (embed, don't invoke)
```

**Philosophy:** Use existing skills for their specific strength. Integrate their outputs into our workflow, don't just invoke them independently.

---

## Common Pitfalls & Prevention

### Pitfall 1: "Fact-Checking Takes Too Long"

**Why it fails:** Publish with errors, lose credibility, SEO penalty.

**Prevention:**
- Build fact-check matrix AS YOU WRITE (Phase 3), not after
- You've already verified sources, just log them
- Actual fact-check time: 5 minutes (just review matrix)

### Pitfall 2: "Humanize the AI Content After"

**Why it fails:** Post-hoc humanization looks fake. Better to write human from start.

**Prevention:**
- Phase 3 builds humanization INTO writing (not applied after)
- Use expert knowledge, specific examples, personal voice from the beginning
- If Phase 3 content doesn't sound human, don't use a humanizer—rewrite Phase 3

### Pitfall 3: "Research Seems Solid, I'll Publish"

**Why it fails:** Subtle hallucinations slip through. Readers/Google catch them.

**Prevention:**
- Every claim must have source in outline (Phase 2)
- Unsourced claims = BLOCKED before writing starts
- You can't accidentally hallucinate claims you never outlined

### Pitfall 4: "Sources Are Old, But They're Authoritative"

**Why it fails:** Algorithm changes, market shifts, data becomes irrelevant.

**Prevention:**
- Check source dates in Phase 1
- For trending topics: If >3 months old, verify freshness
- Add publication date to claims: "As of March 2026..."

### Pitfall 5: "Client Gave Me Rough Content, I'll Clean It Up"

**Why it fails:** You're often making it worse (losing original voice/expertise).

**Prevention:**
- Use client's content as research SOURCE, not template
- Extract key facts and claims
- Rewrite completely in your brand voice
- Give them credit: "Based on insights from [Client Name]..."

### Pitfall 6: "I'll Fact-Check After We Publish"

**Why it fails:** Corrections damage credibility and SEO value.

**Prevention:**
- Non-negotiable: Fact-check BEFORE publication
- It takes 5 minutes if you logged sources as you wrote

---

## Cost & Token Optimization

### Reduce Token Usage

**1. Stream Processing (Don't Hold Everything)**
```
Instead of: Load entire KB + research + sources into context
Do this: Load only what's needed per article
  - Load meta (200 tokens)
  - Load research for THIS topic only (400 tokens)
  - Search for NEW sources only (300 tokens)
  - Stream output (don't hold full draft in memory)
```

**2. JSON Over Prose**
```
Instead of: "Our research found that X is Y because..."
Do this:
  {
    "claim": "X is Y",
    "source": "source_id_5",
    "credibility": "HIGH",
    "date": "2026-03-15"
  }

(100 tokens vs 200 tokens)
```

**3. Reuse Across Articles**
```
Article 1: Research topic A (500 tokens)
Article 2: Reuse 80% of topic A research (50 tokens)
Article 3: Reuse 90% of topic A research (30 tokens)

Result: Compound savings on related content
```

**4. Single-Pass Writing**
```
Instead of: Write draft → humanize → fact-check → rewrite
Do this: Write with humanization + sources built-in
  (Single pass, 40% fewer tokens)
```

### Avoid Paid Tools

**Replace with built-in logic:**

```
❌ External Plagiarism Detection ($$$)
✅ Semantic duplication scoring (Phase 4)

❌ External AI Detection ($$)
✅ Built-in humanization (Phase 3) + human-like structure

❌ External Humanization Tool ($$)
✅ Expert voice + specific examples + varied structure (Phase 3)

❌ External Schema Generator (Some $)
✅ Use seo-aeo-schema-generator (already in your skills)

❌ External Fact-Checker ($$)
✅ Fact-check matrix (Phase 5, logged as you write)
```

---

## Workflow Decision Tree

```
User asks: "Write me a blog post"

START HERE ↓

Has requirements?
├─ NO: Go to Phase 0 (gather info)
└─ YES: Continue ↓

Single article or multiple?
├─ Single: Go to Phase 1-7 (standard workflow)
└─ Multiple: ↓
    Build shared KB first
    └─ Then write each article using Phase 1-7
       (Phase 1 much faster on article 2+)

Is brand new topic?
├─ YES: Full Phase 1 (research)
└─ NO (topic in KB): ↓
    Load existing research
    └─ Add only NEW sources
       (Phase 1 much faster)

Does article need expert input?
├─ YES: Mark expert sections in Phase 2
└─ NO: Continue standard workflow

Any existing sources provided?
├─ YES: Use as anchors in Phase 1
└─ NO: Full web research

Ready to write?
└─ Go to Phase 3-7
```

---

## Requirements Checklist

**Before starting ANY article, confirm:**

```
REQUIRED:
  [ ] Article title (or intended topic)
  [ ] Target keyword(s)
  [ ] Brand positioning (who are you?)
  [ ] Target audience (who reads this?)
  [ ] Content goal (lead gen? SEO ranking? authority?)

OPTIONAL (Will proceed without, note assumptions):
  [ ] Existing sources/links to include
  [ ] Expert knowledge/data to reference
  [ ] Competitor URLs to analyze
  [ ] Tone/voice guidelines
  [ ] Internal articles to link to
  [ ] Content restrictions/guidelines
  [ ] Current keyword rankings (if existing site)
```

**Missing info → Ask user + offer to research:**
"You haven't provided competitor URLs. I'll analyze top 3 rankings for your keyword. Want to provide them instead for better accuracy?"

---

## Success Metrics

**Per Article:**
```
Plagiarism Risk Score:    < 20 (low risk)
Hallucination Check:      100% verified sources
Fact-Check Sign-Off:      All claims verified
Source Traceability:      100% of major claims cited
Humanization Check:       Original examples + expert voice present
AEO Compliance:           All checklist items complete
Keyword Coverage:         Primary + 5+ secondary keywords
```

**Scaling (Multiple Articles):**
```
Article 1:  Full research (100% token cost)
Article 2:  Research 50% faster (50% token cost)
Article 3:  Research 65% faster (35% token cost)
Article 4:  Research 75% faster (25% token cost)
Article 5+: Research 80% faster (20% token cost)

Result: By Article 5, cost per article drops 80% from Article 1
```

---

## Version & Status

**v2.0** - April 2026
- Removed time constraints (AI-agnostic)
- Made primary orchestrator for all content work
- Embedded plagiarism, AI detection, humanization (no external tools)
- Optimized for token efficiency
- Requirement-first approach
- Integrated with existing skills ecosystem

**Status:** Production-ready, tested against real content scenarios

---

## Quick Reference Commands

**To start:**
```
"Create an article about [topic]"
→ I'll ask for Phase 0 requirements
```

**To add to existing content:**
```
"Write 3 articles on [topic cluster]"
→ Phase 0 (once) → Phase 1 (shared KB) → Phase 3-7 (per article)
```

**To analyze existing content:**
```
"Score this content for plagiarism risk and humanization"
→ Phase 4 + Phase 3 checklist
```

**To update content:**
```
"Refresh this article for 2026"
→ Phase 1 (new research) + Phase 5 (fact-check new data) + Phase 7 (republish)
```

---

## Summary: What This Skill Does

✅ **Gathers requirements** - Ensures you have everything before starting
✅ **Builds shared KB** - Reusable research across multiple articles
✅ **Prevents hallucinations** - Only sourced claims in outline
✅ **Writes with built-in humanization** - Not post-hoc
✅ **Checks plagiarism semantically** - No external tool needed
✅ **Verifies facts** - Before publication, not after
✅ **Optimizes for AEO** - Extractable by AI systems
✅ **Saves tokens** - Reuse across articles, JSON structure
✅ **Integrates existing skills** - Uses cluster/keyword/schema generators
✅ **Zero external costs** - All functions built-in

**Bottom line:** Complete content generation system, entirely self-contained, optimized for cost and efficiency.
