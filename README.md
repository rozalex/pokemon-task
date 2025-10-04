# 🏠 Senior Frontend Developer – Architectural Code Review Challenge

## 🎯 Objective
This task evaluates your **architectural judgment, prioritization, and decision-making** - not just coding ability. You'll review an existing codebase, identify issues, prioritize them, and implement strategic refactoring.

---

## 📋 Scenario

A junior developer built a Pokémon Dashboard with 2 widgets using the [Pokémon API](https://pokeapi.co/). The code is in production with 5,000 users. It works, but the team has concerns about:
- Performance issues reported by users on slower connections
- Difficulty adding new features (last change took 3 days)
- High bug rate (8 issues in the last month)
- Unclear data flow making debugging difficult

**Your mission:** Perform a senior-level code review and strategic refactoring.

---

## 🤖 AI Tool Usage Policy

**AI usage is valid and encouraged** for this challenge. We recognize that modern development often involves leveraging AI tools, and we want to understand how you use them effectively.

**Required Documentation:**
In your submission, please include a section (either in ANALYSIS.md or create AI_USAGE.md) that details:

- **Which AI tools did you use?** (e.g., ChatGPT, Claude, GitHub Copilot, Cursor, etc.)
- **How did you use them?** Be specific:
  - Code generation vs. debugging vs. explanation vs. architecture advice
  - What prompts or approaches worked well?
  - What prompts or approaches didn't work?
- **What value did they provide?** 
  - Time saved on specific tasks
  - Quality improvements
  - Learning or understanding gained
- **What did you do yourself?** 
  - Critical thinking and decision-making
  - Code review and validation
  - Architectural choices

**Attaching Your AI Prompts:**
Please include your AI conversation history/prompts in one of these ways:
- Export chat transcripts as text or markdown files (e.g., `ai-prompts/chatgpt-session-1.md`)
- Take screenshots of key prompt exchanges and save them in an `ai-prompts/` folder
- Copy-paste important prompts and responses into your AI_USAGE.md document
- For GitHub Copilot: Document the contexts where you used it and example completions

**Why we ask:** We're interested in understanding your AI collaboration skills - how you leverage these tools effectively while maintaining judgment and critical thinking. This is a valuable modern engineering skill, and seeing your actual prompts helps us understand your thought process.

---

## 🚀 Quick Start

### Installation

```bash
# Install dependencies
npm install

# Start development server
npm run dev
```

The app will open at `http://localhost:5173`

### Run Tests

```bash
npm test
```

---

## 📁 Project Structure

```
pokemon-dashboard-challenge/
├── src/
│   ├── components/
│   │   ├── PokemonList.tsx       # Widget showing pokemon grid
│   │   └── PokemonDetails.tsx    # Widget showing pokemon details
│   ├── App.tsx                    # Main application component
│   ├── main.tsx                   # Entry point
│   └── index.css                  # Global styles
├── ANALYSIS_TEMPLATE.md           # Template for your analysis
└── package.json
```

---

## 🔍 Part 1: Architectural Analysis

Create an **ANALYSIS.md** document with the following sections:

### 1. Issue Identification
Identify **6-8 architectural/design issues**. For each:
- **Location:** File name and line numbers
- **Category:** Performance / Architecture / Maintainability / Testing / UX
- **Description:** What's wrong and why
- **Impact:** Real-world consequences (e.g., "causes unnecessary re-renders affecting mobile users")

**Example format:**
```markdown
### Issue #1: Prop Drilling Hell
- **Location:** App.tsx lines 15-45, all components
- **Category:** Architecture, Maintainability
- **Description:** State and callbacks passed through 3+ component levels
- **Impact:** 
  - Adding new features requires changing 5+ files
  - Difficult to test components in isolation
  - High coupling between unrelated components
```

### 2. Prioritization Matrix
Classify each issue:
- **P0 (Blocker):** Must fix before next release (e.g., security, critical bugs)
- **P1 (High):** Significantly impacts users or development velocity
- **P2 (Medium):** Technical debt that should be addressed
- **P3 (Low):** Nice-to-have improvements

Create a table showing:
| Issue | Priority | Effort | User Impact | Dev Impact |
|-------|----------|--------|-------------|------------|
| #1    | P1       | M      | Medium      | High       |

**Justify your top 3 priorities** - explain WHY these matter most.

### 3. Solution Proposals
For your **top 3 priority issues**, provide:

**For each issue:**
- **Option A:** [Approach 1] 
  - Pros: ...
  - Cons: ...
  - Effort: S/M/L
- **Option B:** [Approach 2]
  - Pros: ...
  - Cons: ...
  - Effort: S/M/L
- **Option C (Optional):** [Approach 3]

**Your Recommendation:** Which option and why?

**What you're NOT fixing:** List the lower-priority issues you're deferring and explain why.

---

## 🛠️ Part 2: Strategic Refactoring

Based on your analysis in Part 1, choose **ONE** of your top priority issues to refactor. This should be one of the high-impact problems you identified and prioritized.

**Your refactoring should:**
- Address a significant architectural or design issue from your analysis
- Demonstrate your implementation skills and architectural judgment
- Show measurable improvement (performance, maintainability, or testability)
- Include justification for your chosen approach over alternatives

**Requirements for your refactoring:**
- ✅ Keep existing functionality working
- ✅ Add 2-3 tests demonstrating improvement
- ✅ Update TypeScript types as needed
- ✅ Document your changes with code comments

---

## 📝 Part 3: Architecture Document

Create **ARCHITECTURE.md** with:

### 1. Changes Summary
- What you fixed and why
- What you chose NOT to fix and why
- Any assumptions or trade-offs made

### 2. Scaling Considerations
Answer these:
- **10 widgets:** How would your architecture handle 10 widgets? What would need to change?
- **100 widgets:** What breaks at 100 widgets? How would you redesign?
- **Real-time data:** If widgets needed live updates (WebSocket), what changes?

### 3. Production Readiness
- **Monitoring:** What metrics would you track? What tools would you use? How would you implement them?
- **Error handling:** What's your strategy for handling API failures? What tools or patterns would you use?
- **Performance:** How would you ensure the app stays fast? What tools would you use to measure performance? What metrics matter most?
- **Rollback:** If your changes cause issues, how do you rollback? What deployment strategy would you recommend?

---

## 📦 Deliverables

**Submission Method:** Share a link to a GitHub repository containing your work.

Your repository should include:

```
pokemon-dashboard-refactored/
├── ANALYSIS.md          # Your issue analysis & prioritization
├── ARCHITECTURE.md      # Architecture decisions & scaling thoughts
├── CHANGES.md          # Summary of what you changed
├── src/
│   ├── [your refactored code]
│   └── [your tests]
└── README.md           # How to run your code
```

**Repository Setup:**
- Make your repository public or grant access to the reviewers
- Include a clear README.md with setup and run instructions
- Ensure all dependencies are properly listed in package.json
- Add a .gitignore file to exclude node_modules and build artifacts

---

## 🎯 Evaluation Criteria

We're evaluating:

### ❌ NOT Primarily Evaluating:
- Perfect code (we know time is limited)
- Complete feature implementation
- Fixing every issue identified

### ✅ Primarily Evaluating:
- **Judgment:** Did you identify the right problems? Prioritize correctly?
- **Trade-offs:** Can you articulate pros/cons of different approaches?
- **Communication:** Can you explain decisions clearly to technical and non-technical audiences?
- **Pragmatism:** Do you balance ideal vs. practical given constraints?
- **Experience:** Do you consider production concerns (monitoring, rollback, performance)?

---

## 📚 Resources

- [React Documentation](https://react.dev/)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [PokéAPI Documentation](https://pokeapi.co/docs/v2)

---

Good luck! We're excited to see your approach. 🚀
