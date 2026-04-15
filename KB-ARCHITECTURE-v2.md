# Knowledge Base Architecture v2: Brand-Wide + Common KB

**Updated:** April 2026
**Change:** From topic-specific KB to brand-wide KB + shared common KB

---

## The Problem (v1)

```
Old approach:
  client_acme/research/personalization/ (Topic 1)
  client_acme/research/blockchain/ (Topic 2)
  client_acme/research/ecommerce/ (Topic 3)

Issues:
  ✗ Research scattered by topic
  ✗ Can't reuse source about "customer behavior" across topics
  ✗ Brand voice duplicated in each topic folder
  ✗ Common patterns (humanization, fact-checking) reinvented per client
  ✗ No way to share insights across clients
```

---

## The Solution (v2): Two-Tier Architecture

### Tier 1: Brand-Wide Knowledge Base

**Purpose:** Persistent storage for one brand/client across ALL articles

```
client_acmeecommerce/ (ONE namespace per brand, no topics)
│
├── meta/ (BRAND IDENTITY - SHARED BY ALL ARTICLES)
│   ├── brand_voice.json
│   │   └── tone, vocabulary, personality, writing style
│   ├── positioning.json
│   │   └── UVP, core message, differentiators
│   ├── target_audience.json
│   │   └── psychographics, pain points, decision drivers
│   └── content_guidelines.json
│       └── restrictions, approved terminology, topics to avoid
│
├── research/ (ACCUMULATING RESEARCH - SHARED ACROSS ALL TOPICS)
│   ├── sources.json
│   │   └── All sources EVER used (deduplicated, never deleted)
│   ├── claims.json
│   │   └── All verified claims by topic/category
│   ├── statistics.json
│   │   └── All metrics with dates and sources
│   ├── industry_trends.json
│   │   └── Trends specific to brand's industry
│   └── competitor_insights.json
│       └── What competitors cover (gaps for us)
│
├── expertise/ (BRAND-SPECIFIC KNOWLEDGE)
│   ├── case_studies.json
│   │   └── Acme's own data, results, examples
│   ├── methodologies.json
│   │   └── How Acme does things differently
│   ├── proprietary_data.json
│   │   └── Unique statistics/findings only Acme has
│   └── lessons_learned.json
│       └── What works for this brand, what doesn't
│
└── performance/ (BRAND-LEVEL METRICS)
    ├── articles.json
    │   └── All articles written, with metadata
    ├── keyword_rankings.json
    │   └── Current rankings across all topics
    ├── successful_patterns.json
    │   └── What drives ranking/engagement for this brand
    └── gap_analysis.json
        └── Untapped keyword opportunities
```

### Tier 2: Common Knowledge Base (Shared Across All Brands)

**Purpose:** Reusable patterns, methodologies, and templates for all clients

```
common_kb/ (READ-ONLY, SHARED BY ALL BRANDS)
│
├── humanization/ (REUSABLE PATTERNS)
│   ├── sentence_structures.json
│   │   └── Varied length patterns (short→medium→long→fragment)
│   ├── personal_voice_markers.json
│   │   └── I-statements, opinions, emotional language
│   ├── specific_example_patterns.json
│   │   └── How to create real, credible examples
│   └── expertise_signals.json
│       └── Process details, common mistakes, insights
│
├── fact_checking/ (UNIVERSAL METHODOLOGIES)
│   ├── credible_sources.json
│   │   └── Ranked by reliability (academic→reports→official)
│   ├── outdated_data_detection.json
│   │   └── How to spot old/irrelevant statistics
│   ├── hallucination_patterns.json
│   │   └── Common false claim patterns to watch for
│   └── contradiction_resolution.json
│       └── How to handle conflicting data sources
│
├── plagiarism_prevention/ (UNIVERSAL TECHNIQUES)
│   ├── restructuring_patterns.json
│   │   └── How to rephrase without copying
│   ├── original_framing_examples.json
│   │   └── Different angles on same topic
│   └── semantic_variation.json
│       └── Alternative vocabulary choices
│
├── industry_knowledge/ (GENERAL TRENDS)
│   ├── seo_guidelines.json
│   │   └── Latest Google ranking signals
│   ├── aeo_best_practices.json
│   │   └── AI extraction optimization
│   ├── tech_trends.json
│   │   └── Emerging technologies, frameworks
│   └── marketing_trends.json
│       └── Industry-wide patterns
│
├── schema_patterns/ (REUSABLE TEMPLATES)
│   ├── faq_schema.json
│   │   └── FAQ structure pattern
│   ├── article_schema.json
│   │   └── Article schema pattern
│   ├── organization_schema.json
│   │   └── Company info pattern
│   └── breadcrumb_schema.json
│       └── Navigation structure pattern
│
├── brand_voice_samples/ (REFERENCE LIBRARY)
│   ├── formal_tone.md (Examples)
│   ├── conversational_tone.md (Examples)
│   ├── technical_tone.md (Examples)
│   └── emotional_tone.md (Examples)
│
└── keyword_research/ (SHARED KEYWORDS)
    ├── trending_keywords.json
    │   └── High-volume keywords by industry
    ├── long_tail_patterns.json
    │   └── Long-tail keyword structures
    └── intent_categories.json
        └── Keyword intent classifications
```

---

## Token Efficiency: How It Compounds

### Article 1: "AI Personalization Basics"

```
Load Brand KB:
  • brand_voice.json (Acme's tone) - 150 tokens
  • positioning.json (Acme's message) - 50 tokens

Load Common KB:
  • humanization patterns - 100 tokens
  • fact-checking methodologies - 100 tokens

Research NEW:
  • Gather 12 sources on personalization - 400 tokens

Store in Brand KB:
  • Store in client_acmeecommerce/research/ - (stored, not in memory)

TOTAL: ~800 tokens for Article 1
```

### Article 2: "Advanced Personalization" (Different Angle)

```
Load Brand KB (FROM CACHE):
  • brand_voice.json - 0 tokens (already in memory)
  • positioning.json - 0 tokens (already in memory)

Load Common KB (FROM CACHE):
  • humanization patterns - 0 tokens (already in memory)
  • fact-checking methodologies - 0 tokens (already in memory)

Reuse from Brand KB:
  • 8 sources from Article 1 research - 100 tokens
  • Competitor insights - 50 tokens

Research NEW:
  • 4 new sources for "advanced" angle - 200 tokens

Store in Brand KB:
  • Merge new sources with existing - (stored, not in memory)

TOTAL: ~350 tokens for Article 2

SAVINGS: 56% vs Article 1
```

### Article 3: "Personalization Implementation"

```
Load (FROM CACHE):
  • Brand KB meta - 0 tokens
  • Common KB patterns - 0 tokens

Reuse from Brand KB:
  • 12 sources from Articles 1-2 - 150 tokens
  • Industry trends (already captured) - 50 tokens

Research NEW:
  • 2 implementation-specific sources - 80 tokens

Store in Brand KB:
  • Update research section - (stored)

TOTAL: ~280 tokens for Article 3

SAVINGS: 65% vs Article 1
```

### Article 5: Maximum Efficiency

```
Load (FROM CACHE):
  • Brand KB meta - 0 tokens
  • Common KB patterns - 0 tokens

Reuse from Brand KB:
  • 14+ accumulated sources - 100 tokens
  • Industry trends, competitor insights - 50 tokens

Research NEW:
  • 1-2 entirely new sources only - 50 tokens

TOTAL: ~200 tokens for Article 5

SAVINGS: 75% vs Article 1
```

---

## Comparison: Old vs New Architecture

### v1: Topic-Specific KB

```
Article 1: Personalization
  ├── research/personalization/sources.json
  ├── research/personalization/claims.json
  └── research/personalization/statistics.json

Article 2: Blockchain (Different Topic)
  ├── research/blockchain/sources.json
  ├── research/blockchain/claims.json
  └── research/blockchain/statistics.json

Article 3: Ecommerce Trends (Different Topic)
  ├── research/ecommerce/sources.json
  ├── research/ecommerce/claims.json
  └── research/ecommerce/statistics.json

Problem: Brand voice duplicated 3 times, humanization reinvented 3 times
```

### v2: Brand-Wide + Common KB

```
Brand KB (Shared):
  ├── meta/brand_voice.json (ONCE, reused by all articles)
  ├── research/sources.json (ALL sources, deduplicated)
  └── research/claims.json (ALL verified claims)

Common KB (Shared across brands):
  ├── humanization/ (ONE set of patterns for all)
  ├── fact_checking/ (ONE methodology for all)
  └── ...

Result:
  • Brand voice stored once, reused always
  • Common patterns stored once, shared across 100s of brands
  • Research accumulates (each article adds to source pool)
```

---

## Retrieval Strategy (Token Optimized)

### Phase 1: Research

**For Article 1 on new topic:**
```
1. Load brand meta (voice, positioning) - 150 tokens
2. Load common KB patterns (shared by all) - 100 tokens
3. Research new sources - 400 tokens
4. Store in brand KB (don't hold in context)
Total: ~650 tokens
```

**For Article 2 on related/different topic:**
```
1. Meta + patterns already cached - 0 tokens
2. Reuse 70% of research from brand KB - 100 tokens
3. Research new sources only - 200 tokens
4. Store in brand KB
Total: ~300 tokens (54% savings)
```

**For Article 5 with full brand KB:**
```
1. Meta + patterns cached - 0 tokens
2. Reuse 80%+ of brand KB research - 100 tokens
3. Research only gaps - 50 tokens
4. Store in brand KB
Total: ~150 tokens (77% savings)
```

---

## Real Example: Acme E-Commerce

### After 5 Articles:

**Brand KB contains:**
- Acme's brand voice (ONE definition, used in all 5 articles)
- 18 deduplicated sources on e-commerce personalization
- 40+ verified claims tagged by topic
- 25+ statistics with dates
- Case studies from Acme's own implementations
- Successful patterns that drive rankings

**Common KB contains:**
- Humanization patterns (used by all Acme's competitors too)
- Fact-checking standards (same for healthcare brand, finance brand)
- Schema patterns (same across industries)

**Next Article Request:**
```
User: "Write about 'E-commerce personalization for mobile'"

I load:
  • Acme's brand voice (0 tokens - cached)
  • Common humanization patterns (0 tokens - cached)
  • Acme's existing 18 sources (100 tokens)
  • Mobile-specific new research (80 tokens)

Total: ~180 tokens

I store:
  • Merge mobile insights into Acme's brand KB
  • Now have even richer knowledge for Article 6

COMPOUND EFFECT: Each article makes next article cheaper
```

---

## Key Benefits

### For Each Brand:
✅ Brand voice consistent across all articles
✅ Research accumulates (never wasted)
✅ Sources deduplicated (no redundant storage)
✅ 75%+ token savings by Article 5
✅ Expertise grows over time

### Across All Brands:
✅ Common patterns shared (no reinvention)
✅ Humanization techniques proven across 100s of articles
✅ Fact-checking standards universal
✅ Schema patterns reusable

### For Your Costs:
✅ No vector DB costs (JSON in memory)
✅ No plagiarism tool costs (built-in)
✅ No AI detection costs (built-in)
✅ Compound token savings (53% savings by Article 5)

---

## Implementation

**When you write first article for Brand A:**
```
→ Create: client_brandA/meta/ (voice, positioning)
→ Load: common_kb/ (shared patterns)
→ Research & store in: client_brandA/research/
→ When Article 2 comes: Reuse brand meta + common KB + accumulated research
```

**When you write first article for Brand B:**
```
→ Create: client_brandB/meta/ (different voice, positioning)
→ Load: common_kb/ (SAME humanization patterns, fact-checking, schemas)
→ Research & store in: client_brandB/research/
→ Note: Some general knowledge might be reusable (industry trends)
```

---

## Summary

**v1:** Topic-based = Isolated research, duplicated patterns
**v2:** Brand-based + Shared = Accumulated research, shared patterns

**Result:**
- 75% token savings by Article 5
- Zero external tool costs (built-in)
- Compound efficiency (each article makes next cheaper)
- Knowledge reusable across clients

**This is the final optimization: architecture matters as much as code.**
