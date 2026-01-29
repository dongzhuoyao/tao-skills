---
name: tao-deepresearch
description: Deep research for AI/ML research. Use when analyzing arxiv papers, conducting literature reviews, finding influential papers, identifying research trends, or exploring implementations. Handles LaTeX source analysis, web search for papers, and GitHub code discovery.
argument-hint: [topic]
allowed-tools: Read, Grep, Glob, WebSearch, WebFetch, Bash(gh *)
---

# Tao Deep Research

Conduct comprehensive AI/ML research by analyzing provided materials and searching for related literature.

## Arguments

- `$ARGUMENTS[0]` - Research topic or question
- `--depth` - Research depth: `quick` (overview), `medium` (detailed), `thorough` (comprehensive)
  - **Default: `thorough`**
- `--focus` - Research focus: `methods` (algorithms/techniques), `experiments` (benchmarks/results), `theory` (foundations/proofs)
  - **Default: `methods`**

When no arguments are provided, use `depth=thorough` and `focus=methods`.

## Input Types

The user may provide:
1. **LaTeX source** from arxiv papers (analyze the "Related Works" section as starting point)
2. **Code** for implementation context
3. **Topic description** for open-ended research

## Research Workflow

### Step 1: Analyze Provided Materials
If LaTeX source is provided:
- Parse the "Related Works" or "Related Work" section
- Extract cited papers, authors, and key themes
- Identify the research area and subfields
- Note any code repositories mentioned

If code is provided:
- Identify the methods/models implemented
- Check for paper references in comments or README

### Step 2: Search for Related Literature
Use web search to find:
- Recent papers on the identified topics (prioritize last 2 years)
- Highly-cited foundational papers
- Survey papers for comprehensive coverage
- Arxiv preprints for cutting-edge work

Search queries should include:
- Key method names and algorithms
- Problem domain keywords
- Author names from seminal works

### Step 3: Fetch and Analyze Papers
For important papers found:
- Fetch arxiv abstracts and metadata
- Identify citation counts and influence (when available)
- Note publication venues (NeurIPS, ICML, ICLR, ACL, CVPR, etc.)
- Track chronological development

### Step 4: Search for Implementations
Search GitHub for:
- Official implementations of key papers
- Popular reimplementations with high stars
- Relevant libraries and frameworks
- Benchmark repositories

### Step 5: Synthesize Findings
Analyze the collected information to identify:
- Evolution of methods over time
- Current state-of-the-art approaches
- Emerging trends and directions
- Open problems and challenges

## Output Format

Generate a structured research report with these sections:

### Key Papers
List the most important papers with:
- Title, authors, year, venue
- Arxiv link (if available)
- Brief description of contribution
- Relative influence/importance

Format:
```
**[Paper Title]** (Year)
Authors: [Names]
Venue: [Conference/Journal] | [arxiv:XXXX.XXXXX](https://arxiv.org/abs/XXXX.XXXXX)
Contribution: [1-2 sentence summary]
```

### Methods/Approaches Overview
- Categorize methods by type/approach
- Explain key techniques and innovations
- Compare strengths and limitations
- Note computational requirements

### Timeline/Trends Analysis
- Chronological development of the field
- Key breakthroughs and when they occurred
- Current dominant approaches
- Emerging directions and recent shifts

### Open Problems/Future Directions
- Unsolved challenges in the field
- Limitations of current methods
- Promising research directions
- Potential applications

### Code/Implementation References
- Official repositories with links
- Popular frameworks and libraries
- Benchmark datasets and evaluation code
- Format: `[Repo Name](GitHub URL) - Brief description (stars if notable)`

## Depth Levels

**Quick** (5-10 papers):
- Focus on most influential recent papers
- Brief overview of methods
- Key trends only

**Medium** (15-25 papers):
- Comprehensive coverage of recent work
- Detailed methods comparison
- Full trend analysis

**Thorough** (30+ papers):
- Exhaustive literature review
- Historical context and evolution
- Deep technical analysis
- Multiple subcategories explored

## Focus Areas

**Methods**: Prioritize algorithmic innovations, architectural designs, training techniques
**Experiments**: Prioritize benchmarks, datasets, evaluation metrics, empirical results
**Theory**: Prioritize mathematical foundations, convergence proofs, theoretical guarantees

## Example Usage

```
/tao-deepresearch "GRPO training for reasoning models" --depth thorough --focus methods
```

```
/tao-deepresearch "efficient attention mechanisms" --depth quick
```

When LaTeX is provided:
```
User: [pastes LaTeX source]
/tao-deepresearch --depth medium --focus experiments
```

## Research Best Practices

1. **Recency**: Prioritize papers from the last 2 years for current state-of-the-art
2. **Influence**: Weight highly-cited papers and papers from top venues
3. **Diversity**: Include different approaches and perspectives
4. **Verification**: Cross-reference claims across multiple sources
5. **Completeness**: Cover both foundational work and recent advances
