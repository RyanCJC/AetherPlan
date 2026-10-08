You are an expert software engineer, AI/ML engineer, and technical interviewer.

I am preparing for a **Junior AI Automation Software Engineer** interview. I want you to analyze this ENTIRE project/codebase and generate a **very detailed, technically accurate interview preparation document** based ONLY on what is actually present in the repository.

## Critical rules

1. **Inspect the entire repository before answering.**

   * Read the source code, configuration files, README, documentation, notebooks, schemas, prompts, API integrations, frontend/backend code, model files/configuration, database-related code, tests, and other relevant files.
   * Trace important execution flows through the code rather than relying only on README descriptions.
   * Identify the actual entry points and how the components connect.

2. **Do not invent anything.**

   * Do not assume a technology, algorithm, API, database, architecture pattern, feature, or implementation exists unless you can find evidence in the code/documentation.
   * If something is described in documentation but does not appear to be implemented, explicitly label it:
     **"Documented but implementation not verified."**
   * If something appears in the code but is not documented, point that out as well.

3. Explain technical concepts in a way that I can use in an interview.
   I need to understand not only WHAT the project does, but also:

   * WHY it was designed this way
   * HOW each component works
   * HOW the components interact
   * WHAT alternatives were available
   * WHY the selected approach makes sense
   * WHAT its limitations are
   * WHAT could be improved

5. Use the official/recognized names of technologies, frameworks, algorithms, architectures, and concepts. Do not create your own terminology.

---

# PART 1 — EXECUTIVE SUMMARY

Give me a concise but technically accurate overview containing:

* Project name
* Project purpose
* Problem being solved
* Target users
* Main features
* Core technologies
* Overall architecture
* My likely contribution
* What makes the project technically interesting
* The 3–5 strongest points I should emphasize during an interview

Then give me a **30-second interview explanation** and a **2-minute interview explanation**.

---

# PART 2 — COMPLETE SYSTEM ARCHITECTURE

Reverse-engineer the project's architecture from the code.

Explain:

* Frontend
* Backend
* AI/ML components
* LLM components
* Databases
* External APIs
* Authentication if any
* Storage
* Data processing
* Workflow/orchestration
* Deployment/infrastructure if present

Create a clear text-based architecture such as:

User
↓
Frontend
↓
Backend/API
↓
...
↓
Database / External API / AI model

For every component explain:

1. What it is
2. Why it exists
3. What technology is used
4. What input it receives
5. What processing it performs
6. What output it produces
7. What component consumes that output

Also identify:

* synchronous vs asynchronous processing
* deterministic vs probabilistic components
* where state is stored
* where errors can occur
* important dependencies between components

---

# PART 3 — END-TO-END EXECUTION FLOW

Trace the most important user journey from beginning to end.

For example:

User action
→ frontend
→ API request
→ backend
→ validation
→ AI/LLM workflow
→ external API
→ processing
→ database
→ response
→ frontend

Explain the actual functions/classes/modules involved whenever possible.

For each major step provide:

* File
* Function/class
* Input
* Processing
* Output
* Next component

I want enough detail that I can explain the entire system verbally without opening the code.

---

# PART 4 — AI / ML COMPONENTS

Identify every AI/ML component.

For each one explain:

* Model/framework
* Task
* Input features/data
* Preprocessing
* Model inference/training if applicable
* Output
* Evaluation
* Why this approach was selected
* Alternatives
* Limitations

If the project uses an LLM, explain:

* LLM/provider/model
* Prompt structure
* System/user prompts
* Context passed to the LLM
* Structured output if any
* Tool/function calling if any
* Temperature/other relevant parameters
* How hallucination or incorrect output is handled
* How the LLM interacts with deterministic logic

Do NOT simply say "the LLM generates the response." Trace what information is actually given to it.

---

# PART 5 — AGENT / WORKFLOW / LANGGRAPH ANALYSIS

If LangGraph or another workflow/orchestration framework is used, analyze it in depth.

Explain:

* Graph/state architecture
* State schema
* Nodes
* Edges
* Conditional routing
* Tool calls
* Loops
* Retry logic
* Error handling
* Human-in-the-loop behavior if any
* How information moves through state
* Where the LLM is used
* Where deterministic logic is used

For each important node:

Node name:

* Purpose
* Input state
* Processing
* Tools/API calls
* Output state
* Next node

Then answer:

**Why is a graph/workflow architecture useful for this project instead of one large LLM prompt?**

Also identify whether the system is actually "agentic" based on the implementation, rather than simply accepting that label from the README.

---

# PART 6 — DATA FLOW

Trace every important piece of data.

Explain:

* Where data originates
* How it is validated
* How it is transformed
* Where it is stored
* How it is retrieved
* How it enters AI/ML processing
* How the final result is generated

Create separate flows for important data types if necessary.

For example:

User input
→ validation
→ database
→ retrieval
→ model
→ explanation
→ LLM
→ final response

---

# PART 7 — API INTEGRATIONS

Identify every external API.

For each API explain:

* API name
* Purpose
* Endpoint/functionality used
* Request structure
* Parameters
* Authentication method
* Response structure
* How the response is processed
* Error handling
* Rate-limit considerations if visible
* Why the API is needed

Pay special attention to whether APIs are called directly by the frontend, backend, or AI workflow.

---

# PART 8 — DATABASE / STORAGE

Identify all databases, vector databases, object storage, caches, or other persistence mechanisms.

Explain:

* Database technology
* Tables/collections
* Important fields
* Relationships
* CRUD operations
* Queries
* Indexes/vector indexes if applicable
* Why this database was selected
* How data moves between the application and database
* Security considerations visible in the implementation

If Supabase, PostgreSQL, pgvector, DynamoDB, S3, etc. are present, explain exactly how they are used.

---

# PART 9 — FRONTEND

Explain:

* Framework
* Architecture
* Important pages/components
* State management
* API communication
* User interaction flow
* Form handling
* Error handling
* Important libraries
* How frontend communicates with backend

I need to be able to answer:

**"How does your frontend communicate with your backend?"**

and

**"What happens when the user performs X?"**

---

# PART 10 — BACKEND

Explain:

* Framework
* Application entry point
* Routes/endpoints
* Request/response models
* Business logic
* Service layer if any
* AI integration
* Database integration
* Error handling
* Validation
* Configuration/environment variables

Explain the most important endpoints in detail.

---

# PART 11 — ENGINEERING DECISIONS

Identify the important technical decisions made in the project.

For each:

**Decision → Reason → Alternative → Trade-off**

Examples:

* Why this framework?
* Why this model?
* Why this database?
* Why this API?
* Why LangGraph?
* Why RAG?
* Why separate deterministic logic from LLM reasoning?
* Why this frontend framework?
* Why this architecture?
* Why this data structure?

Do not invent reasons. If the codebase does not reveal the original reason, clearly say:

**"The repository does not establish the original reason; a technically reasonable justification would be..."**

Clearly distinguish actual project rationale from your suggested interview explanation.

---

# PART 12 — FAILURE MODES AND EDGE CASES

Identify potential failure scenarios.

Examples:

* API failure
* Invalid user input
* Missing data
* LLM hallucination
* malformed LLM output
* database failure
* timeout
* rate limit
* incorrect model prediction
* conflicting constraints
* unavailable external service
* unexpected API response

Explain how the current code handles each one.

If it does not handle them, say so.

Then suggest how I could improve it.

---

# PART 13 — SECURITY

Analyze visible security considerations:

* API keys
* environment variables
* authentication
* authorization
* input validation
* SQL injection
* prompt injection
* sensitive data
* CORS
* exposed endpoints
* secrets in source code
* dependency risks

Do NOT claim the system is secure simply because no obvious issue was found.

Instead distinguish:

* Implemented
* Partially implemented
* Not implemented / not evident

---

# PART 14 — PERFORMANCE AND SCALABILITY

Analyze:

* computational bottlenecks
* API latency
* database queries
* LLM latency
* concurrent requests
* caching
* model inference
* vector search
* scalability limitations

Then answer:

**"If 100 users used this system simultaneously, what could become a bottleneck?"**

and

**"How would you improve the architecture for production?"**

Only make recommendations based on the actual architecture.

---

# PART 15 — TESTING AND QUALITY

Identify:

* unit tests
* integration tests
* end-to-end tests
* validation
* error handling
* logging
* monitoring
* test coverage if available

Explain what is tested and what isn't.

Then provide the **5 most important tests I should add** if the project were being prepared for production.

---

# PART 16 — DEPLOYMENT

If deployment/infrastructure exists, explain:

* hosting
* cloud provider
* services
* environment configuration
* CI/CD
* containers
* networking
* database deployment
* frontend deployment
* backend deployment

If deployment is not implemented, clearly say so.

Then explain how you would deploy the project properly in production.

---

# PART 17 — INTERVIEW QUESTIONS

Generate a comprehensive list of likely interview questions based specifically on THIS project.

Categorize them:

### Beginner

Questions about what the project does.

### Intermediate

Questions about architecture and implementation.

### Advanced

Questions about trade-offs, scalability, reliability, AI architecture, security, etc.

### Challenge questions

Questions designed to expose whether I genuinely understand the project.

For every question provide a strong but natural answer that I could actually say during an interview.

Do not make the answers unnecessarily academic.

---

# PART 18 — "WHY DID YOU CHOOSE X?"

Generate specific questions and answers for:

* Why this programming language?
* Why this framework?
* Why this database?
* Why this AI model?
* Why this LLM?
* Why LangGraph?
* Why LangChain?
* Why RAG?
* Why this API?
* Why this architecture?
* Why not an alternative?

Only include technologies actually present in the repository.

---

# PART 19 — "WHAT WOULD YOU IMPROVE?"

Give me realistic answers to:

* What would you improve?
* What was the biggest limitation?
* What would you change if you rebuilt it?
* How would you productionize it?
* How would you scale it?
* How would you improve reliability?
* How would you reduce cost?
* How would you improve accuracy?
* How would you improve security?

The answers should demonstrate engineering maturity without pretending that I implemented improvements that I did not actually implement.

---

# PART 20 — MY CONTRIBUTION

Create a section specifically titled:

**"What I Can Honestly Claim I Built"**

Separate:

### Definitely implemented / evidenced

### Probably contributed

### Cannot be verified from repository

This is extremely important because I must not accidentally claim ownership of another teammate's work during an interview.

---

# PART 21 — 30-SECOND / 1-MINUTE / 3-MINUTE ANSWERS

Create three versions of the project explanation:

### 30 seconds

For "Tell me briefly about this project."

### 1 minute

For a normal interview explanation.

### 3 minutes

For when the interviewer asks me to explain the project in detail.

Make these sound like natural spoken English, not a written report.

---

# PART 22 — MOCK TECHNICAL INTERVIEW

Finally, act as a strict technical interviewer for a **Junior AI Automation Software Engineer** position.

Generate a mock interview based ONLY on this project.

Ask questions progressively:

1. Project overview
2. Architecture
3. My contribution
4. AI/ML
5. LLM
6. Workflow/orchestration
7. API integration
8. Database
9. Error handling
10. Security
11. Scalability
12. Trade-offs
13. Failure scenarios
14. Improvement

For each question provide:

* What the interviewer is testing
* What a strong answer should contain
* A model answer
* Common bad answer
* Follow-up question the interviewer may ask

---

# FINAL SECTION — INTERVIEW CHEAT SHEET

End with a compact cheat sheet containing:

### Project in one sentence

### Architecture in one sentence

### My contribution

### 5 technologies I should emphasize

### 5 technical decisions

### 5 important numbers/metrics (if applicable)

### 5 limitations

### 5 likely technical questions

### 5 likely follow-up questions

### 5 things I absolutely must NOT claim

### 5 strongest points for a Junior AI Automation Software Engineer interview

## Output quality

Be extremely detailed and technically rigorous.

However, prioritize **understanding and interview usefulness over simply producing a huge amount of text**.

Use headings, tables, diagrams, bullet points, and code references where useful.

When referring to implementation details, include the relevant **file path and function/class name** so I can verify your explanation against the source code.

Do not merely summarize the README.

**Analyze the actual implementation and reconstruct how the system works.**
