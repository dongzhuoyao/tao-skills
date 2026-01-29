# tao-skills

A collection of custom Claude Code skills for AI/ML research workflows.

## Skills

### tao-deepresearch

Deep research skill for AI/ML literature review and paper analysis.

**Usage:**
```
/tao-deepresearch "your research topic"
```

**Features:**
- Analyze arxiv LaTeX source (especially "Related Works" sections)
- Search for recent highly-influential papers
- Find GitHub implementations
- Identify research trends

**Options:**
- `--depth`: `quick` | `medium` | `thorough` (default: thorough)
- `--focus`: `methods` | `experiments` | `theory` (default: methods)

**Output:**
- Key Papers (with citations)
- Methods/Approaches Overview
- Timeline/Trends Analysis
- Open Problems/Future Directions
- Code/Implementation References

## Installation

Clone this repo and the skills will be available in Claude Code when working in this directory.

```bash
git clone git@github.com:dongzhuoyao/tao-skills.git
```

Or copy skills to your global Claude skills directory:
```bash
cp -r .claude/skills/* ~/.claude/skills/
```
