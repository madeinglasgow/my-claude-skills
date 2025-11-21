# Course Outline Generator - Reference Guide

## PRD Analysis Checklist

When analyzing a PRD, look for these key elements:

### Required Elements
- **Course Duration**: Total video time, activity time, overall time commitment
- **Module Structure**: Number of modules, videos per module
- **Video Format**: Length constraints, required sections
- **Pedagogical Pattern**: Often "show→explain→conceptualize" or similar
- **Example Requirements**: Coding vs. non-coding, diversity requirements
- **Assessment Structure**: Quiz questions, hands-on activities
- **Success Metrics**: Enrollment targets, completion rates, satisfaction scores

### Common PRD Patterns
- **Progressive Difficulty**: Simple → Intermediate → Advanced
- **Conceptual Building**: Foundational → Applied → Extended
- **Domain Coverage**: Technical → Business → Creative

## Resource Processing Strategy

### Official Resources Priority
1. **Core Documentation**: Architecture, concepts, implementation
2. **Getting Started Guides**: First-user experience, basic examples
3. **Best Practices**: Patterns, anti-patterns, recommendations
4. **API References**: Technical details, parameters, options

### Community Resources Value
1. **Real Metrics**: ROI, time savings, performance data
2. **War Stories**: What went wrong, lessons learned
3. **Creative Applications**: Unexpected use cases
4. **Simplifications**: Better analogies, clearer explanations
5. **Advanced Patterns**: Power user techniques

## Pedagogical Patterns

### Show → Explain → Conceptualize
1. **Show (Concrete Example)**
   - Start with something tangible and relatable
   - Should work without prior knowledge
   - Clear before/after or transformation

2. **Explain (Mechanics)**
   - How the example actually works
   - Step-by-step breakdown
   - Technical details made accessible

3. **Conceptualize (Abstract Principle)**
   - The broader lesson
   - Transferable knowledge
   - Connection to larger system

### Alternative Patterns
- **Problem → Solution → Generalization**
- **Observation → Hypothesis → Validation**
- **Current State → Desired State → Path**

## Example Selection Criteria

### Primary Example Requirements
- **Universal Relatability**: Works across cultures and backgrounds
- **Clear Value**: Obvious benefit or improvement
- **Right Complexity**: Simple enough to grasp, complex enough to be meaningful
- **Memorable**: Sticks in memory after single exposure
- **Practical**: Actually useful in real work

### Alternative Example Strategy
- **Example 1**: Different domain (if primary is coding, use business)
- **Example 2**: Different complexity (if primary is simple, show scale)
- **Both**: Must demonstrate exact same concept differently

## Enhancement Patterns

### Example Justification Template
"Why this example works: [Universal hook that everyone understands]. It perfectly demonstrates [key concept] through [specific mechanism]. The example showcases [clear transformation]. This bridges the abstract concept of [concept] to a tangible, real-world outcome that [value proposition]."

### Explain Mapping Template
"How the example demonstrates this: In the [example name] demonstration, learners witness [observable behavior]. When [trigger event], Claude [specific action]. This concrete visibility—[list specific observables]—makes the abstract concept of [concept] tangible. The [example element] literally [concrete manifestation]."

### Conceptualize Mapping Template
"How the example demonstrates this concept: The [example name] perfectly embodies [concept metaphor]. The [conceptual element] is literally visible as [concrete manifestation]. Before [event], Claude is [initial state]. The moment [trigger], we witness the transformation into [final state]. This isn't just [surface change]; it's [deep transformation]. The [key aspect] demonstrates that [fundamental truth]."

## Common Pitfalls to Avoid

### Research Phase
- ❌ Skipping "less relevant" sources
- ❌ Not tracking source attribution
- ❌ Missing non-obvious insights
- ✅ Read everything, find unexpected gems

### Creation Phase
- ❌ Deviating from PRD structure
- ❌ Adding "helpful" sections not in PRD
- ❌ Changing time allocations
- ✅ Follow PRD exactly, enhance within structure

### Enhancement Phase
- ❌ Generic justifications
- ❌ Vague concept mappings
- ❌ Repetitive alternative examples
- ✅ Specific, concrete, varied enhancements

## Quality Metrics

### Outline Completeness Score
- PRD requirements met: 100%
- All sources consulted: 100%
- All enhancements added: 100%
- Examples justified: 100%
- Mappings complete: 100%

### Pedagogical Quality Indicators
- Examples understood in <30 seconds
- Concepts stick after one reading
- Clear progression through course
- Balanced technical/non-technical
- Actionable learning outcomes

## File Organization

```
course-outline-generator/
├── SKILL.md           # Main skill definition (you are here)
├── REFERENCE.md       # This reference guide
├── EXAMPLES.md        # Sample outline sections
└── templates/         # Optional templates
    ├── module.md
    └── video.md
```

## WebFetch Prompts for Resources

### For Official Documentation
"Extract key information about [topic] including: what it is, how it works, core concepts, implementation details, best practices, common patterns, and any specific examples. Focus on foundational knowledge that would be important for teaching beginners."

### For Community Resources
"Extract practical insights about [topic] including: real-world metrics, case studies, lessons learned, creative applications, simplified explanations, advanced patterns, and any unique perspectives that differ from official documentation. Focus on experiential knowledge from practitioners."

### For Blog Posts
"Extract the main thesis, supporting arguments, concrete examples, code snippets, metrics or data, key takeaways, and any unique insights not found in official documentation. Note any warnings, pitfalls, or contrarian views."

## Final Checklist

Before delivering the outline:
- [ ] PRD requirements: 100% met
- [ ] Sources consulted: 100% visited
- [ ] Examples justified: All complete
- [ ] Concept mappings: All explicit
- [ ] Alternative examples: All provided
- [ ] Community insights: All integrated
- [ ] File saved: Proper markdown format
- [ ] Quality bar: Would you take this course?