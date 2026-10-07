# Abdul Rehman

**AI Engineer and Architect for AECO.** I work where law, architecture, planning and technology meet, on one recurring problem: data fragmentation. Regulations, plans, cadastral records and BIM models describe the same building but sit in different offices, formats and systems.

Architect by training, then business developer for an architecture firm, then an M.Sc. in Sustainable Mobilities at HfWU Nürtingen-Geislingen (2026). My thesis on AI-assisted regulatory intelligence for Stuttgart's building governance was graded 1.0 and 1.3. Based in Ulm, Germany.

## Four disciplines, one practice

| | What I bring |
|---|---|
| **Law and compliance** | German planning and building law (BauGB, BauNVO, LBO BW, Bebauungspläne) and digital regulation and governance frameworks (EU AI Act, GDPR, ISO 37301, COBIT, NIST) |
| **Architecture and planning** | Design practice, permitting and approval processes, zoning plans, BIM and IFC |
| **Strategy and business** | Process modelling in BPMN 2.0, stakeholder and expert interviews, evaluation design, client acquisition, CRM and marketing for architecture services |
| **Technology** | Agentic AI, RAG, computer vision, MCP servers, workflow automation, geodata and data pipelines |

## How I approach a project

I start with the process, not the model. For my thesis I mapped how a building regulation question actually travels through Stuttgart's administration as a five-lane BPMN model, built from correspondence with the city offices and validated by a planning-law professor. Only then did I design the system, following Design Science Research. I evaluated it three ways: a usability study with 55 participants, expert consultation with the authorities, and a technical benchmark against verified answers.

My view is that trustworthy AI for regulated domains will come from agents that cross-check each other against official sources, and that are tested until we know exactly where they fail.

## Featured work

### Stuttgart Building Regulations AI
A regulation assistant that answers one question three ways and compares the results, across three levels of government: federal, state and municipal.

- **Text:** retrieval over 12,253 chunks from 363 source documents (BauGB, BauNVO, LBO BW, Stuttgart Bebauungspläne and local statutes)
- **Vision:** a YOLOv8 + EasyOCR pipeline that reads the Nutzungsschablone on zoning plans (mAP50 0.705)
- **Space:** ALKIS cadastral data to resolve an address or plot number to its parcel, area and built coverage

Built and deployed as a working web application, and reviewed by the Baurechtsamt Stuttgart. I benchmarked all three layers against verified answers and documented the failures, including a 32% off-topic rate on topics with thin corpus coverage and what fixed it.

`CrewAI` `FastAPI` `OpenAI` `YOLOv8` `EasyOCR` `GeoPandas` `QGIS`

Source code is private. A walkthrough or demo is available on request.

### vCOO: Virtual Chief Compliance Officer
A research-assistant project at HfWU. The vCOO helps people who build digital products with no-code and generative AI tools to see which rules apply to them.

- **Knowledge layer:** five MCP servers, one per framework: EU AI Act, GDPR, ISO 37301, COBIT and NIST, each with its own vector store and source citations
- **Prototype:** a test scenario (an AI mobility adviser for city planners that uses GPS data) run through all five frameworks, producing risk levels, cited passages and recommended actions
- **Research bot:** pulls current regulatory updates from EUR-Lex
- **Orchestration:** LangGraph agents for risk mapping, recommendations and documentation, with human oversight

`MCP` `LangGraph` `FAISS` `HuggingFace embeddings` `Python`

### Workflow automation with AI agents
Business automation built in n8n, where an agent does the routine work and a person keeps the final say.

- **Team content pipeline for a travel startup:** a webhook starts an AI agent that researches and drafts a message, an email asks a human to approve or decline, and the approved text is posted to the team's WhatsApp group
- **Personal productivity agent:** plain-language commands ("schedule gym tomorrow at 7pm") become Google Calendar events and a prioritised task list in Google Sheets, with memory across sessions, in three to six seconds

`n8n` `OpenAI` `Perplexity` `WhatsApp API` `Google Calendar` `Google Sheets`

### More projects

| Project | Highlight | Built with |
|---|---|---|
| IFC compliance server | An MCP tool that checks IFC geometry against a regulation service. It caught a fabricated value in my own system. | FastMCP, IfcOpenShell |
| Regulatory knowledge graph | Graph analysis of 91 benchmark answers: answers that cite a specific plan almost never go off-topic, answers that cite nothing often do. | TopologicPy, Python |
| Weissenhof geodata study | 73 official LoD2 buildings compared with ALKIS and aerial imagery in 3D. The datasets disagree on the roof of a Le Corbusier house. | Blender, MCP, QGIS |
| Embodied carbon calculator | Plain-language questions about grey energy of building materials, answered from the Swiss KBOB dataset (SIA 2032 context). | Python, RAG |
| Claude and Revit through MCP | Natural-language queries on a live Revit model: element counts and a DIN 276 cost estimate worked, heavy scripts crashed the bridge. | Revit 2026, MCP |
| PakCarbon AI | Competition prototype for carbon credit verification on Karachi's Green Line BRT, using real air-quality data and the ACM0016 method. | CrewAI, FastAPI, PostgreSQL |

Repositories for these are being published one by one.

## Training and coursework projects

The foundations under the work above. These are course projects, labelled as such.

<details>
<summary><b>Agentic AI engineering: eight projects</b> (AI Engineer Agentic Track: The Complete Agent and MCP Course, Udemy)</summary>

<br>

| Project | What it does | Framework |
|---|---|---|
| Career digital twin | An agent that answers questions about my background on my behalf | OpenAI Agents SDK |
| SDR agent | Automated sales outreach with drafting and sending tools | OpenAI Agents SDK |
| Deep research agent | A team of agents that plans, searches and writes a research report | OpenAI Agents SDK |
| Stock picker | A crew that researches companies and recommends one | CrewAI |
| Engineering team | Four agents that design, write and test software together | CrewAI |
| Operator agent | Browser automation with tools and memory | LangGraph |
| Agent creator | An agent that writes and launches new agents | AutoGen |
| Trading floor | Four agents working through six MCP servers and 44 tools | MCP |

</details>

<details>
<summary><b>Data Analysis and Visualization</b> (M.Sc. course, HfWU)</summary>

<br>

Seminar project on mobility planning in Baden-Württemberg:

- Processed more than 200,000 spatial data points (linestrings and coordinates) from open government data with Pandas, NumPy, GeoPandas and Shapely
- Buffer analysis and hub-distance calculations for proximity mapping
- K-Means clustering of parking capacity
- Heatmaps and spatial visualisations in QGIS and Matplotlib

Related work: heatwave mapping in QGIS.

`Python` `Pandas` `GeoPandas` `Shapely` `Matplotlib` `QGIS`

</details>

<details>
<summary><b>Business Analytics and Artificial Intelligence</b> (M.Sc. course, HfWU)</summary>

<br>

- **Fraud detection for banking data:** binary classification on an imbalanced dataset in KNIME, comparing neural networks, regression and decision trees, with feature engineering and precision and recall as the target metrics
- **Customer churn prediction for a telecom dataset:** exploratory analysis and preprocessing, then logistic regression, decision trees and random forest compared by AUC-ROC

`KNIME` `scikit-learn` `Excel`

</details>

## Experience

- **Research assistant (HiWi), HfWU, 2025 to 2026:** the vCOO compliance system, then Python and AI teaching notebooks and research support
- **Business Development and Marketing Manager, Disruptive Designs LLC (US architecture firm), 2023 to 2024:** built international client acquisition with a CRM (Snov.io), lead generation, conversion funnels, KPI tracking, and LinkedIn and website content
- **Architect, SHA Architects, 2021 to 2023:** design, client and contractor coordination, permitting and documentation

## Research and talks

- **DBP26, Munich, November 2026:** poster, "Restoring Information Mobility in Multi-Level Building Governance: A Deployed Multi-Agent RAG System for German Building Regulations"
- **OGC iDays 2026, Munich, November 2026:** accepted presentation
- **Journal paper** on the mixed-methods evaluation of the Stuttgart system, in preparation

## Work with me

I take on freelance and project work in two areas.

**AI for regulations, BIM and geodata** (architecture firms, engineering offices, public bodies)

- **Strategy and scoping:** mapping the current process, interviewing stakeholders, and defining where AI helps and where it does not
- **Regulation and document assistants:** question answering over building codes, standards or internal documents, with sources
- **Compliance knowledge tools:** a first-pass map of an AI product against the EU AI Act, GDPR and governance frameworks (a research aid, not legal advice)
- **Plan reading and geodata integration:** structured data from zoning plans, connected to cadastral and building data
- **AI for BIM:** connecting language models to Revit and IFC models through MCP
- **Evaluation:** testing an existing AI system against verified answers before it is trusted

**AI automation for business development and marketing** (AEC firms and small teams)

I have done client acquisition for an architecture firm myself, so I know the workflow before I automate it.

- **Lead and CRM workflows:** collecting, enriching and tracking leads, with outreach sequences and KPI reporting
- **Content pipelines with human approval:** agents that research and draft, a person who approves, automatic publishing to email, LinkedIn or WhatsApp
- **Internal assistants:** scheduling, task tracking and reporting connected to the tools a team already uses

## Currently

- Deepening BIM and IFC workflows, with digital twins as the next direction
- Open to AI engineering roles, research positions and freelance projects

## Contact

[LinkedIn](https://www.linkedin.com/in/meetrehmann)
