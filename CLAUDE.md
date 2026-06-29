# AZ-204 Exam Prep Hub

## Goal
Build a single standalone HTML file (no server, opens directly in browser, works offline).

## What to build
- Home screen with two sections: Topic Drills and Practice Tests
- 10 topic drill sets, 40 questions each, topic switcher on home screen
- 10 timed practice tests, 40 questions each, 85-minute countdown timer
- All questions hard-coded in JS (no API calls, fully offline)

## Topics for drills (one set each)
1. App Service & Azure Functions
2. Azure Storage (Blob, Table, Queue, Files)
3. Azure Cosmos DB
4. API Management
5. Event Grid / Service Bus / Event Hubs
6. Security — Key Vault, Managed Identity, RBAC
7. Containers — ACI, AKS, Azure Container Apps
8. Azure AD / Authentication / Authorization
9. Monitoring, Logging, Application Insights
10. Caching (Redis) & CDN

## Question requirements — CRITICAL
- All questions must be scenario-based and trap-heavy (NOT Microsoft Learn easy level)
- Mix of: best-option scenarios, code/config snippet questions, "what is wrong" diagnostics
- Each question has exactly 4 options, one correct answer, and a detailed explanation
- Practice tests should feel like real exam questions — ambiguous distractors, edge cases
- Past-exam style for practice tests: cover all 10 topic areas proportionally

## UI reference
- Match the style in `reference.html` exactly:
  - Cards with subtle borders, progress bar, nav dots, timer display
  - Green/red feedback on answer selection, explanation shown after answering
  - Score screen with % score, correct/wrong count, time taken
  - "Review wrong answers" and "Restart" buttons on score screen
- Home screen needs: topic cards grid + practice test cards grid
- Back button to return to home from any drill or test

## File output
- Single file: `az204_prep.html`
- No external dependencies (no CDN, no fonts, no images)
- Must work when opened directly from filesystem (file:// protocol)

## How to build without hitting size limits
Write the file in chunks using bash append (>>), never in one shot:
1. Write HTML head + CSS first
2. Write JS question banks topic by topic (one topic at a time)
3. Write practice test question banks (one test at a time)  
4. Write the app logic (navigation, timer, scoring) last
5. Verify file size and test open in browser

## Coding conventions
- Vanilla JS only, no frameworks
- All questions in a single TOPICS object and TESTS array
- Each question: { q, options, answer, explanation, code (optional) }

## Visual upgrades over reference.html
- Dark sidebar or top nav with Azure blue (#0078D4) accent
- Hero-style home screen with exam stats (total questions, topics, tests)
- Topic cards with icons (use emoji — 🗄️ Storage, ⚡ Functions, 🔐 Security etc.)
- Practice test cards showing test number, question count, time limit
- Smooth transitions between home/drill/test views
- Better score screen — pass/fail banner, per-topic breakdown on practice tests
- Sticky timer with color warning at 20 min and danger at 10 min remaining
- Question difficulty badge (Medium / Hard) on each question card