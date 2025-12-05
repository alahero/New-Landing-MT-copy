# Task List Management

Guidelines for managing task lists in markdown files to track progress on completing a PRD

## Task Implementation
- *One sub-task at a time:* Do *NOT* start the next sub‑task until you ask the user for permission and they say "yes" or "y"
- *Completion protocol:*  
  1. When you finish a *sub‑task*, immediately mark it as completed by changing [ ] to [x].
  2. If *all* subtasks underneath a parent task are now [x], follow this sequence:
    - *First*: Run the full test suite (pytest, npm test, bin/rails test, etc.)
    - *Only if all tests pass*: Stage changes (git add .)
    - *Clean up*: Remove any temporary files and temporary code before committing
    - *Commit*: Use a descriptive commit message that:
      - Uses conventional commit format (feat:, fix:, refactor:, etc.)
      - Summarizes what was accomplished in the parent task
      - Lists key changes and additions
      - References the task number and PRD context
      - **Formats the message as a single-line command using -m flags**, e.g.:

        
        git commit -m "feat: add payment validation logic" -m "- Validates card type and expiry" -m "- Adds unit tests for edge cases" -m "Related to T123 in PRD"
        
  3. Once all the subtasks are marked completed and changes have been committed, mark the *parent task* as completed.
- Stop after each sub‑task and wait for the user's go‑ahead.

## Task List Maintenance

1. *Update the task list as you work:*
   - Mark tasks and subtasks as completed ([x]) per the protocol above.
   - Add new tasks as they emerge.

2. *Maintain the "Relevant Files" section:*
   - List every file created or modified.
   - Give each file a one‑line description of its purpose.

## AI Instructions

When working with task lists, the AI must:

1. Regularly update the task list file after finishing any significant work.
2. Follow the completion protocol:
   - Mark each finished *sub‑task* [x].
   - Mark the *parent task* [x] once *all* its subtasks are [x].
3. Add newly discovered tasks.
4. Keep "Relevant Files" accurate and up to date.
5. Before starting work, check which sub‑task is next.
6. After implementing a sub‑task, update the file and then pause for user approval.

# Rule: Generating a Product Requirements Document (PRD)

## Goal

To guide an AI assistant in creating a detailed Product Requirements Document (PRD) in Markdown format, based on an initial user prompt. The PRD should be clear, actionable, and suitable for a junior developer to understand and implement the feature.

## Process

1.  *Receive Initial Prompt:* The user provides a brief description or request for a new feature or functionality.
2.  *Ask Clarifying Questions:* Before writing the PRD, the AI must ask clarifying questions to gather sufficient detail. The goal is to understand the "what" and "why" of the feature, not necessarily the "how" (which the developer will figure out). Make sure to provide options in letter/number lists so I can respond easily with my selections.
3.  *Generate PRD:* Based on the initial prompt and the user's answers to the clarifying questions, generate a PRD using the structure outlined below.
4.  *Save PRD:* Save the generated document as prd-[feature-name].md inside the /tasks directory.

## Clarifying Questions (Examples)

The AI should adapt its questions based on the prompt, but here are some common areas to explore:

*   *Problem/Goal:* "What problem does this feature solve for the user?" or "What is the main goal we want to achieve with this feature?"
*   *Target User:* "Who is the primary user of this feature?"
*   *Core Functionality:* "Can you describe the key actions a user should be able to perform with this feature?"
*   *User Stories:* "Could you provide a few user stories? (e.g., As a [type of user], I want to [perform an action] so that [benefit].)"
*   *Acceptance Criteria:* "How will we know when this feature is successfully implemented? What are the key success criteria?"
*   *Scope/Boundaries:* "Are there any specific things this feature should not do (non-goals)?"
*   *Data Requirements:* "What kind of data does this feature need to display or manipulate?"
*   *Design/UI:* "Are there any existing design mockups or UI guidelines to follow?" or "Can you describe the desired look and feel?"
*   *Edge Cases:* "Are there any potential edge cases or error conditions we should consider?"

## PRD Structure

The generated PRD should include the following sections:

1.  *Introduction/Overview:* Briefly describe the feature and the problem it solves. State the goal.
2.  *Goals:* List the specific, measurable objectives for this feature.
3.  *User Stories:* Detail the user narratives describing feature usage and benefits.
4.  *Functional Requirements:* List the specific functionalities the feature must have. Use clear, concise language (e.g., "The system must allow users to upload a profile picture."). Number these requirements.
5.  *Non-Goals (Out of Scope):* Clearly state what this feature will not include to manage scope.
6.  *Design Considerations (Optional):* Link to mockups, describe UI/UX requirements, or mention relevant components/styles if applicable.
7.  *Technical Considerations (Optional):* Mention any known technical constraints, dependencies, or suggestions (e.g., "Should integrate with the existing Auth module").
8.  *Success Metrics:* How will the success of this feature be measured? (e.g., "Increase user engagement by 10%", "Reduce support tickets related to X").
9.  *Open Questions:* List any remaining questions or areas needing further clarification.

## Target Audience

Assume the primary reader of the PRD is a *junior developer*. Therefore, requirements should be explicit, unambiguous, and avoid jargon where possible. Provide enough detail for them to understand the feature's purpose and core logic.

## Output

*   *Format:* Markdown (.md)
*   *Location:* /tasks/
*   *Filename:* prd-[feature-name].md

## Final instructions

1. Do NOT start implementing the PRD
2. Make sure to ask the user clarifying questions
3. Take the user's answers to the clarifying questions and improve the PRD

Layout Sections & Formulas for landing pages:
1. IMPACT
   • Goal – State what you do, who you serve, and the outcome.  
   • Headline   = [What You Do] + [Outcome]  
     e.g. “Unlimited Copywriting That Converts”  
   • Sub-headline = We help [Audience] + [Value Prop 1], [Value Prop 2], [Value Prop 3] with [What You Do]  
     e.g. “We help B2B SaaS companies lower staff costs, go to market faster, and convert more demos with unlimited copywriting.”  
   • Visual – Hero image/illustration that reinforces the promise.

2. TRUST
   • Distribute testimonials, case-studies, client & press logos, and data throughout the page (not one isolated block).

3. EMPATHY
   • Empathy Headline = [Question] + [Deep-Rooted Concern]  
     e.g. “Do you have an amazing product but struggle to communicate its true value?”  
   • Empathy Sub-headline – Reassure the visitor you “get” their situation.

4. PAIN
   • Highlight frustrations: lost money / time / opportunity, unmet goals.  
   • Mirror their internal dialogue; segue to your solution.

5. AUTHORITY
   • Authority Formula = We help [Customer Industry] + [Path Forward]  
     e.g. “We help B2B SaaS companies write copy that clearly communicates value and prompts action.”  
   • Proof point example: “We helped [Client] lift demo requests by [X %] by rewriting their homepage.”

6. ACTION
   • CTA Headline = [Value] + “Starts Now”  
     e.g. “Your path to better copy starts now.”  
   • Cost-of-Inaction snippet: outline consequences of delaying (“You lose opportunities every time a customer fails to resonate with your copy.”).

   # Development Rules

## Before Making Changes
0. Always read all documentation before any change
1.⁠ ⁠Compare changes against current flow to verify compatibility
2.⁠ ⁠If flow is broken, find alternative approach
3.⁠ ⁠After changes, verify all existing functionality still works
4.⁠ ⁠Use different approaches from previous attempts in changes log
5.⁠ ⁠Keep communication real and direct:
   - No corporate bullshit speak
   - Be straight up about what you're doing
   - Admit mistakes directly without sugar-coating
   - Do proper technical work but drop the perfect AI act
   - Read and understand shit properly before changing it
   - Tell exactly what you're doing without professional fluff  

   Technical SEO Website Structure Checklist
technical SEO, static URLs, ≤ 3-level architecture, descriptive keyword slugs, canonical tags (paginated + self), correct www ↔ non-www redirects, HTTP → HTTPS redirect, unique fresh content, heading hierarchy H1-H6, ≥ 320-word key pages, helpful 404, sitemap.xml, robots.txt (no blocking), no critical noindex, no severe 404s, breadcrumbs, zero critical JS/Flash-locked assets, staging not indexed, responsive design, PWA, no intrusive pop-ups, legible typography, images via HTML (not CSS), minified HTML-CSS-JS, CDN, AMP blog.

Check Per Page
Clean URL structure; no accents, percent signs, underscores, or special characters
Title is unique across the site
Title is 30–65 characters, descriptive, and relevant to the page content
Meta description is unique for each page
Meta description is 70–155 characters and aligned with the page content
Exactly one H1 tag in content containing the focus keyword or a semantic variant
Hierarchical H2, H3, etc. structure relevant to the content
Open Graph tags correctly implemented
Twitter Card tags correctly implemented
Structured data validates correctly
Images named descriptively with no accents or percent signs
Images weigh less than 150 KB
Images’ pixel dimensions do not exceed the displayed size
All images include descriptive <alt> attributes
Page text length is at least 320 words
Internal links open in the same tab
External links open in a new tab
Page load speed < 3 seconds