## Madhav Krishna Arumulla
**Software Engineer — AI & ML Systems**

I build LLM systems that survive contact with real users.

Most of what I do is the unglamorous half of machine learning — the part after the model works in a notebook and before a few thousand students start asking it things nobody anticipated. Retrieval that returns the right passage instead of a plausible one. A cache that knows two differently-worded questions are the same question. An audit log you can't quietly edit. A hard ceiling on what any one developer can spend.

I'm finishing an M.S. in Computer Science at Texas Tech. Through most of 2026 I built and ran the AI infrastructure for the university's Online division; I've since moved to a new role I'll be able to talk about shortly.

---

### What I'm working on

**[CIPHER](https://github.com/MadhavKrishna06/CIPHER)** — a local, privacy-preserving tutor and quiz agent for a network security course. All inference runs on the user's own machine through Ollama; course documents never leave the host. Hybrid retrieval over a local ChromaDB index, SHA-256 integrity checks on every ingested source, per-chunk citations down to the file and page. The only thing that ever touches the network is an optional citation lookup, and only the query text goes with it.

**[Healthcare-Chatbot](https://github.com/MadhavKrishna06/Healthcare-Chatbot)** — symptom-driven triage using decision trees and SVM.

### What I've built that isn't here

From April to September 2026 I owned the AI infrastructure at Texas Tech University Online. That code belongs to the university, so it isn't public. Roughly what it was:

- **An LLM API gateway** in front of every model provider the division used. Each developer got a virtual key with a token budget attached; the gateway authenticated it, metered it, and refused it when the budget was gone. Every request appended to a hash-chained audit log, so editing an old entry broke every entry after it. Later extended into a multi-tenant analytics layer for auditing AI voice-call quality — encrypted per-tenant keys, usage reporting, a triage queue for low-quality calls.
- **A student-facing chatbot**, shipped to production. Hybrid retrieval — dense vectors for meaning, keyword search for the exact course code someone typed — with a Redis semantic cache so the fiftieth phrasing of a question didn't cost a fiftieth call. Layered evaluation scored the answer and the retrieval that produced it. A crisis-keyword interceptor pulled certain conversations out of the model's hands entirely, and a prompt-injection filter sat in front, tested against adversarial inputs rather than assumed to work.
- **A reporting layer** on Snowflake, surfaced through Sigma, that replaced a pile of manual Salesforce and Smartsheet exports with dashboards that update themselves.

### Research

- **Modelling Physical Unclonable Functions with classical ML** — 100,000 challenge–response pairs, logistic regression and random forest, ~79% accuracy. Enough to show the design leaks structure. Advised by Dr. Yu Zhuang at Texas Tech.
- **BrailleMail: Voice-Controlled Email Assistant** — a voice-driven email client for blind and low-vision users. Published in *Computational Techniques and Smart Manufacturing*, CRC Press, 2026, pp. 753–759. [doi:10.1201/9781003679622-87](https://doi.org/10.1201/9781003679622-87)

---

### What I reach for

<p>
  <img alt="Python" title="Python" height="36" src="https://cdn.simpleicons.org/python/3776AB" />&nbsp;&nbsp;
  <img alt="FastAPI" title="FastAPI" height="36" src="https://cdn.simpleicons.org/fastapi/009688" />&nbsp;&nbsp;
  <img alt="Redis" title="Redis" height="36" src="https://cdn.simpleicons.org/redis/DC382D" />&nbsp;&nbsp;
  <img alt="Docker" title="Docker" height="36" src="https://cdn.simpleicons.org/docker/2496ED" />&nbsp;&nbsp;
  <img alt="PostgreSQL" title="PostgreSQL" height="36" src="https://cdn.simpleicons.org/postgresql/4169E1" />&nbsp;&nbsp;
  <img alt="Snowflake" title="Snowflake" height="36" src="https://cdn.simpleicons.org/snowflake/29B5E8" />&nbsp;&nbsp;
  <img alt="scikit-learn" title="scikit-learn" height="36" src="https://cdn.simpleicons.org/scikitlearn/F7931E" />&nbsp;&nbsp;
  <img alt="TensorFlow" title="TensorFlow" height="36" src="https://cdn.simpleicons.org/tensorflow/FF6F00" />&nbsp;&nbsp;
  <img alt="Ollama" title="Ollama" height="36" src="https://cdn.simpleicons.org/ollama/8B8B8B" />&nbsp;&nbsp;
  <img alt="Nginx" title="Nginx" height="36" src="https://cdn.simpleicons.org/nginx/009639" />
</p>

Python and FastAPI for most things, Flask when it's small. Redis does more work than people expect — rate limits, semantic caching, job state. Docker and Nginx to ship it; Postgres and Snowflake underneath; Sigma on top when the audience is analysts rather than engineers.

On the model side: RAG with hybrid vector and keyword search, prompt engineering that gets tested rather than tweaked, semantic caching, evaluation harnesses, prompt-injection defence. Scikit-learn, TensorFlow, Keras, Pandas and NumPy from coursework and research that still earn their place. Java, C, SQL and JavaScript when the problem asks for them.

Things I care about that aren't libraries: multi-tenant isolation, API security, FERPA compliance when student data is involved, and audit trails that would survive someone looking at them closely.

---

If you're building something where the LLM has to actually behave, I'd like to hear about it.

**[Email](mailto:madhav.arumulla@gmail.com)** · **[LinkedIn](https://linkedin.com/in/madhav-krishna-arumulla-033612290)** · Lubbock, Texas
