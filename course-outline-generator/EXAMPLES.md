# Course Outline Generator - Examples

## Example 1: Well-Structured Video Outline

This example shows all required elements and enhancements for a single video:

```markdown
**Video 2.1: The Progressive Disclosure Architecture**
- Concrete example: Walk through PDF processing skill loading in three stages (metadata → instructions → scripts)
  - *[Source: Progressive disclosure concept from https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview; specific walkthrough is **new example for this course**]*
  - Why this example works: The PDF processing skill serves as an ideal teaching vehicle because it contains all three disclosure levels in meaningful ways that learners can visualize. At Level 1, the simple metadata ("handles PDF files") shows how Claude can scan hundreds of skills without context bloat. At Level 2, the skill instructions might include form field extraction logic and filling strategies—complex enough to justify selective loading. At Level 3, Python scripts for PDF manipulation demonstrate why execution without context entry is crucial. This progression mirrors how developers think about optimization: start broad, load details on demand, execute efficiently.
  - **Alternative example 1:** Database migration skill showing Level 1 (metadata: "handles database schema migrations"), Level 2 (migration strategies and rollback procedures), Level 3 (1000-line SQL migration scripts) - demonstrates same architecture with database operations
  - **Alternative example 2:** AWS infrastructure deployment skill with Level 1 (description: "provisions cloud resources"), Level 2 (terraform patterns), Level 3 (CloudFormation templates) - shows progressive loading for DevOps workflows
- Explain the architecture: Level 1 (metadata always loaded), Level 2 (instructions on trigger), Level 3 (resources on demand)
  - *[Source: Three-level loading model from https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview]*
  - How the example demonstrates this: The PDF processing walkthrough makes each architectural level observable through actual token usage. At Level 1, Claude starts with just metadata consuming ~20 tokens. When the user mentions "fill out this tax form," Level 2 triggers—Claude loads the full instructions adding ~300 tokens. At Level 3, scripts execute without consuming tokens. The demonstration shows actual token counts at each stage, proving how the architecture prevents context explosion.
- Conceptualize: Context window optimization through selective loading - "effectively unbounded context"
  - *[Source: "Effectively unbounded" quote from https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills]*
  - How the example demonstrates this concept: The PDF processing demonstration makes "effectively unbounded context" tangible through real numbers. With 50 skills installed, traditional loading would consume 15,000+ tokens, leaving little room for actual work. But progressive disclosure shows only 1,000 tokens used for metadata, with the PDF skill's instructions loading only when needed. The "unbounded" nature becomes clear when the skill executes a 2,000-line Python script—this code never enters the context window yet Claude can use its full functionality.
- **Community insights:**
  - Technical detail: Skills operate through a meta-tool pattern, injecting specialized instructions via hidden user messages (https://leehanchung.github.io/blogs/2025/10/26/claude-skills-deep-dive/)
  - Optimization tip: Skills carry ~1,500+ tokens overhead per turn - keep SKILL.md under 5,000 words (https://leehanchung.github.io/blogs/2025/10/26/claude-skills-deep-dive/)
  - Practical advice: "Keep your main SKILL.md file under 500 lines" - context windows are shared resources (https://dev.to/nunc/how-i-built-agent-skills-for-claude-code-oj4)
```

## Example 2: Module Header with Time Allocation

```markdown
### **Module 3: Building Your First Skills** (2 videos, ~10 min)

**Video 3.1: Creating a Simple Coding Skill - Commit Messages**
[video content...]

**Video 3.2: Non-Coding Example - Document Creation Skill**
[video content...]
```

## Example 3: Hands-On Activity with Clear Structure

```markdown
**Activity 2: Build Your First Skill** (~45 min)
- Choose a repetitive task from your workflow (coding or non-coding)
  - *[**New example for this course** - open-ended for learner personalization]*
- Create a simple single-file SKILL.md with proper frontmatter
  - *[Source: Structure from https://code.claude.com/docs/en/skills]*
- Write clear description focusing on "what" and "when"
  - *[Source: Best practice from https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices]*
- Test and iterate on description until Claude reliably activates it
  - *[**New example for this course**]*
- Refine instructions based on Claude's performance
  - *[**New example for this course**]*
```

## Example 4: Assessment Quiz Topics

```markdown
## Assessment Quiz Topics (10 questions)

1. **Model-invoked vs user-invoked distinction** - When do skills activate automatically vs requiring explicit commands? (conceptual)
2. **Progressive disclosure levels** - What loads at each stage and why? (conceptual)
3. **Description field best practices** - Given scenarios, identify effective vs ineffective descriptions (application)
4. **When to use skills vs other approaches** - Scenario-based decision making (application)
5. **YAML frontmatter requirements** - What fields are mandatory and formatting rules (technical)
```

## Example 5: Community Insights Section

```markdown
- **Community insights:**
  - Real-world case: One developer managed Oracle database with 1,048 packages by creating two focused skills, achieving 85.7% test pass rate (https://dev.to/nunc/how-i-built-agent-skills-for-claude-code-oj4)
  - ROI evidence: Five production case studies showed average ROI of 6,444% with payback periods under 3 weeks (https://www.cursor-ide.com/blog/claude-code-skills)
  - Decision framework: "Is it a utility? → Skill. Multiple reasoning steps? → Subagent" (https://dev.to/nunc/claude-code-skills-vs-subagents-when-to-use-what-4d12)
```

## Example 6: Source Summary Section

```markdown
## Example Source Summary

**Examples from Anthropic documentation:**
- Core concepts (progressive disclosure, model-invoked vs user-invoked)
- PDF form-filling as primary use case
- Commit message generator YAML example
- Directory structures and best practices

**New examples created for this course:**
- Tax form as specific PDF example
- Developer commit format comparison scenario
- Blog post outliner and report template skills
- All hands-on activity implementations

**Sources Used:**
1. https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills
2. https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview
3. https://code.claude.com/docs/en/skills
```

## Example 7: Learning Outcome Alignment

```markdown
## Learning Outcome Alignment

✓ **Identify Agent Skills Opportunities**
- Videos 1.2, 2.2 teach recognition patterns
- Quiz questions 2, 4, 7 test understanding
- Activity 1 provides hands-on exploration

✓ **Decompose Complex Tasks**
- Videos 4.1, 4.2 demonstrate decomposition
- Multi-file skills show modularity in practice
- Activity 3 requires breaking down workflows

✓ **Create Working Agent Skills**
- All activities build toward custom skill creation
- Activity 4 requires domain-specific implementation
- Videos 3.1, 3.2 provide step-by-step guidance
```

## Key Patterns to Note

### Source Attribution Pattern
- Official sources: Include full URL
- New examples: Mark as **new example for this course**
- Mixed sources: Note what's original vs. sourced

### Enhancement Layering Pattern
1. Base content (example, explain, conceptualize)
2. Source attribution
3. Justification paragraph
4. Mapping paragraphs
5. Alternative examples
6. Community insights

### Consistency Pattern
- All videos follow identical structure
- All activities include time estimates
- All examples include attribution
- All concepts include mappings

These examples demonstrate the level of detail and structure expected in a professionally-designed course outline that follows PRD specifications while incorporating multiple sources of insight.