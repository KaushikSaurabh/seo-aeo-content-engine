# SEO-AEO Content Engine: Quick Reference Checklist

## 9-Phase Workflow at a Glance

### Phase 1: Research & Data Gathering (2-3 hours)
```
[ ] Expand topic into search queries
[ ] Gather 8-12 authoritative sources
[ ] Extract key statistics with dates
[ ] Identify fact-checkable claims
[ ] Flag hallucination risks
[ ] Store in client KB (vector database)
[ ] Create content brief
```

### Phase 2: Content Planning (1-2 hours)
```
[ ] Use seo-aeo-content-cluster for topic map
[ ] Identify keywords to target
[ ] Create outline with evidence tracking
[ ] Mark "expert sections" (human-only)
[ ] Map internal links
[ ] Get outline approved
```

### Phase 3: Co-Creation (3-5 hours)
```
[ ] AI writes source-grounded draft
[ ] Each claim includes inline citations
[ ] Human expert enhances with experience
[ ] Add personal anecdotes & voice
[ ] Maintain source traceability
[ ] Flag uncertain claims for verification
```

### Phase 4: Fact-Checking (2-3 hours)
```
[ ] Create fact-check matrix for each section
[ ] Verify claims against original sources
[ ] Identify hallucinations
[ ] Update outdated information
[ ] Resolve contradictions
[ ] Get human expert sign-off
```

### Phase 5: Plagiarism Detection (30 mins)
```
[ ] Run through Copyleaks or Turnitin
[ ] Check plagiarism % (<10% target)
[ ] Review flagged sections
[ ] Verify proper attribution
[ ] Rewrite flagged unattributed content
[ ] Confirm <5% clean
```

### Phase 6: AI Detection Scan (30 mins)
```
[ ] Run through GPTZero
[ ] Run through Originality.ai
[ ] Run through Copyleaks AI Detector
[ ] Target: <15% on all scanners
[ ] If over 15%: Use humanize skill
[ ] Verify doesn't drop below Phase 4 quality
```

### Phase 7: Schema & Technical SEO (1-2 hours)
```
[ ] Use seo-aeo-schema-generator
[ ] Generate Article schema
[ ] Generate FAQ schema
[ ] Generate Organization schema
[ ] Validate against schema.org
[ ] Check Google Helpful Content alignment
[ ] Verify Mobile-first readiness
```

### Phase 8: Internal Linking (1 hour)
```
[ ] Use seo-aeo-internal-linking skill
[ ] Map to pillar article
[ ] Identify cluster articles
[ ] Determine anchor text
[ ] Check no cannibalization
[ ] Avoid orphaned content
[ ] Finalize link strategy
```

### Phase 9: Final Review (1 hour)
```
[ ] All facts verified (Phase 4 sign-off)
[ ] Plagiarism <10% (Phase 5 approval)
[ ] AI detection <15% (Phase 6 approval)
[ ] Schema valid (Phase 7)
[ ] Links strategic (Phase 8)
[ ] Tone consistent
[ ] No broken links/sources
[ ] Images optimized
[ ] Meta description written
[ ] Author/date correct
[ ] Final editor sign-off
[ ] Ready to publish
```

---

## Red Flag Quick Scan

**STOP If You See:**
- [ ] Fact-checking skipped to "save time"
- [ ] Publishing without plagiarism check
- [ ] No sources for major claims
- [ ] Client can't allocate expert review
- [ ] Using humanizer instead of human expert
- [ ] Claims without dates on trending topics
- [ ] Publishing unchanged AI-generated content

---

## Source Attribution Templates

### For Statistics:
```
"X% of companies report improvement (Source: Gartner Research Report, 2026)"
```

### For Case Studies:
```
"We increased conversions 23% through implementation (Source: Internal case study, Company Name, 2026)"
```

### For Academic Findings:
```
"Research indicates effectiveness in X scenario (Source: Smith et al., Journal Name, 2025)"
```

### For Industry Guidance:
```
"Google's latest documentation recommends X (Source: Google Official Documentation, March 2026)"
```

---

## Time Estimates

| Phase | Duration | Notes |
|-------|----------|-------|
| 1. Research | 2-3 hrs | Scales down with repeat topics |
| 2. Planning | 1-2 hrs | Faster with established client |
| 3. Co-Creation | 3-5 hrs | 60% AI, 40% expert |
| 4. Fact-Checking | 2-3 hrs | Non-negotiable time |
| 5. Plagiarism | 0.5 hrs | Automated + review |
| 6. AI Detection | 0.5 hrs | Automated + review |
| 7. Schema/SEO | 1-2 hrs | Scales with tool adoption |
| 8. Internal Linking | 1 hr | Faster with established map |
| 9. Final Review | 1 hr | Quality gate |
| **TOTAL** | **11-17 hrs** | **1.5-2 weeks per article** |

---

## Success Targets

```
Plagiarism:        < 5% (verified clean)
AI Detection:      < 15% (all detectors)
Facts Verified:    100% before publish
Sources Traced:    100% of claims
Expert Involved:   40%+ of content creation
Client Satisfaction: 90%+ first draft approval
```

---

## Skills Checklist

Before starting, confirm you have:
- [ ] `seo-aeo-blog-writer` (content structure)
- [ ] `seo-aeo-content-cluster` (topic planning)
- [ ] `seo-aeo-keyword-research` (keyword targeting)
- [ ] `seo-aeo-schema-generator` (structured data)
- [ ] `seo-aeo-content-quality-auditor` (pre-checks)
- [ ] `seo-aeo-internal-linking` (link strategy)
- [ ] `agent-memory-systems` (KB building)
- [ ] `humanize` (tone enhancement, if needed)
- [ ] `find-skills` (discover additional skills)

---

## Knowledge Base Structure

```
client_{client_id}/
├── research_{topic_id}/
│   ├── sources.md
│   ├── statistics.md
│   └── contradictions.md
├── expertise_{domain}/
│   ├── case_studies.md
│   └── expert_insights.md
├── brand_voice/
│   ├── tone_guidelines.md
│   └── examples.md
├── competitor_analysis/
└── performance_tracking/
    └── successful_articles.md
```

---

## Common Responses to Client Pushback

**"Can we skip fact-checking to go faster?"**
> No. Fact-checking catches errors before publication. Post-publication corrections damage credibility and SEO value.

**"Can AI content just pass through a humanizer?"**
> No. Humanizers produce variable quality. Expert writing produces better results. If you have expert time, use Phase 3 properly.

**"How do we know it's truly plagiarism-free?"**
> Copyleaks/Turnitin detection <5%, plus manual review of any flagged content. It's 95%+ reliable.

**"What if our expert isn't available for 2 weeks?"**
> Use the simpler `seo-aeo-blog-writer` skill. This orchestrator requires expert involvement for quality.

**"Does this guarantee rankings?"**
> No. SEO rankings depend on E-E-A-T (Experience, Expertise, Authoritativeness, Trust). This skill builds T and A. E and E depend on expert quality.

---

**Last Updated:** April 2026
**Version:** 1.0
