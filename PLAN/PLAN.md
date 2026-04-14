# Branded Student Discovery Game for University Marketing

## Summary
Build a fast, branded “student discovery” experience for prospective undergrads that takes 2 to 5 minutes and outputs both a personalization profile and CRM-friendly lead insight.

Recommended v1 concept: **Topographical Swoop**
Swoop travels across a stylized Utah map/campus landscape. Each stop presents a quick choice, micro-challenge, or preference prompt. The route the student chooses becomes the quiz, so it feels like exploration rather than form-filling.

Keep **Block U Builder** as a secondary concept if the team later wants a simpler fallback or event activation version.

## Key Changes
### Core game concept
- Use a map/exploration loop with 5 to 7 short decision points.
- Each stop represents a meaningful college dimension: academics, campus life, support, career goals, challenge level, community, and environment.
- Interactions should be lightweight: pick-a-path, swipe/select cards, one-tap tradeoff choices, or short drag/drop moments.
- End with a named profile, a short “about you” summary, and personalized content modules.

### Recommended game ideas to consider
- **Topographical Swoop**
  Swoop navigates to locations like “Summit of Ambition,” “Trail of Belonging,” or “Career Canyon.” Each choice reveals student priorities while reinforcing Utah/campus branding.
- **Build Your Route**
  Students choose their own ideal route across campus-style landmarks. The order and selections shape the profile. This is the cleanest variant of the Swoop concept.
- **Block U Builder**
  Each answer adds a branded block to the U. The final structure visually reflects the student’s priorities. Best if the team wants a simpler mechanic with stronger logo integration.
- **Hybrid**
  Use the topographical map as the journey and the Block U as the end-state results animation. This gives the strongest brand payoff if design capacity allows.

### Recommended profile model
Use a **hybrid motivation + interest** system with one primary profile and one secondary academic leaning.

Primary motivational profiles:
- **The Explorer**
  Wants breadth, discovery, flexibility, and new experiences.
- **The Achiever**
  Motivated by ambition, challenge, prestige, and high performance.
- **The Builder**
  Focused on practical outcomes, careers, internships, and real-world readiness.
- **The Connector**
  Values belonging, collaboration, community, and student life.
- **The Changemaker**
  Driven by purpose, impact, service, and solving meaningful problems.

Secondary interest lens:
- Health and helping fields
- Business and leadership
- Engineering and technology
- Arts and creativity
- Science and research
- Humanities and society

Result format:
- Show 1 primary motivation profile
- Show 1 secondary academic-interest tag
- Optionally show a short “You thrive where…” statement for personalization logic

### Personalization outputs
After results, dynamically tailor:
- Featured programs and majors
- Student stories/testimonials
- Campus-life highlights
- Suggested next actions such as visit, apply, talk to admissions, explore scholarships

CRM/export fields:
- Primary profile
- Secondary interest tag
- Top 2 motivation signals
- Intended start term if collected
- Lead source and completion timestamp

### Public interfaces and content model
Define these content/data objects before implementation:
- `Question`: prompt, interaction type, answer options, scoring weights
- `Profile`: id, label, short description, personalized messaging
- `InterestTag`: id, label
- `ContentMapping`: profile or profile+interest to programs, stories, campus-life modules, CTA set
- `LeadPayload`: contact fields plus result metadata

Scoring defaults:
- Every answer contributes weighted points to 1 or more motivation profiles
- Some answers also increment interest tags
- Final result chooses highest motivation score plus top interest tag
- Tie-break with either latest high-confidence answer or predetermined priority order

## Test Plan
- Student can complete the full experience in under 5 minutes on mobile.
- Result feels accurate and non-corny across all 5 primary profiles.
- Every profile has distinct personalized programs, stories, campus-life content, and CTA modules.
- Scoring produces balanced distribution across profiles in sample test runs.
- CRM payload captures result fields correctly and consistently.
- If a student skips a question or abandons mid-flow, the experience still exits gracefully without broken personalization.
- Accessibility check: keyboard navigation, color contrast, motion reduction, readable touch targets.

## Assumptions
- v1 targets prospective undergraduate students only.
- The first launch should prioritize website personalization and recruiter follow-up equally.
- The team wants strong University of Utah branding, with Swoop and topographical/campus visual language leading the experience.
- The team is comfortable with 5 primary profiles; this is enough for personalization without making results feel too generic or too granular.
- Personalized content will be modular and mapped by profile rather than fully custom-written per individual student.
