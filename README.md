# Abdul Rehman

**AI Engineer and Architect for AECO.** I work where law, architecture, planning and technology meet, on one recurring problem: data fragmentation. Regulations, plans, cadastral records and BIM models describe the same building but sit in different offices, formats and systems.

Architect by training, then business developer for an architecture firm, then an M.Sc. in Sustainable Mobilities at HfWU Nürtingen-Geislingen (2026). My thesis on AI-assisted regulatory intelligence for Stuttgart's building governance was graded 1.0 and 1.3 (German grading system). 

Currently based in Ulm, Germany.

## Five disciplines, one practice

| | What I bring |
|---|---|
| **Law and compliance** | German planning and building law (BauGB, BauNVO, LBO BW, Bebauungspläne) and digital regulation and governance frameworks (EU AI Act, GDPR, ISO 37301, COBIT, NIST) |
| **Architecture and planning** | Design practice, permitting and approval processes, zoning plans, BIM and IFC |
| **Strategy and business** | Process modelling in BPMN 2.0, stakeholder and expert interviews, evaluation design, client acquisition, CRM and marketing for architecture services |
| **Technology** | Agentic AI, RAG, computer vision, MCP servers, workflow automation, geodata and data pipelines |
| **Applied AI research** | Design Science Research, benchmark design with verified answers, failure-mode analysis, model comparison, mixed-methods evaluation, academic writing |

## Applied AI research

Research I have carried out, each piece on a real system:

- **Benchmark design:** a 25-query cross-layer benchmark with answers verified by hand against the legal text or the plan itself, and an 82-query diagnostic set for failure patterns
- **Failure-mode analysis:** traced wrong answers to their cause (a missing federal law in the corpus, a worked example left in a prompt, retrieval ranking distracted by place names, a misrouting query classifier), fixed the first three and documented what remains open
- **Model comparison:** general-purpose vision-language models (GPT-4o vision and Qwen) against a small domain-trained detector for reading zoning plans
- **Controlled experiments:** query decomposition by governance level against single-pass retrieval on the same corpus
- **Calibration:** scoring not only whether an answer is right, but whether the system was confident when it was wrong
- **Graph analysis:** a knowledge graph of what the system cites, showing that answers anchored to a specific plan rarely go off-topic
- **User studies:** a usability study with 55 participants, conducted with a student research team and analysed with ANOVA and regression, alongside expert consultation

## How I approach a project

I start with the process, not the model. For my thesis I mapped how a building regulation question actually travels through Stuttgart's administration as a five-lane BPMN model, built from correspondence with the city offices and validated by a planning-law professor. Only then did I design the system, following Design Science Research. I evaluated it three ways: a usability study with 55 participants, expert consultation with the authorities, and a technical benchmark against verified answers.

My view is that trustworthy AI for regulated domains will come from agents that cross-check each other against official sources, and that are tested until we know exactly where they fail.

## Featured work

### [Stuttgart Building Regulations AI](https://github.com/meet-rehman/digital-building-permit-stuttgart)
A regulation assistant that answers one question three ways and compares the results, across three levels of government: federal, state and municipal.

- **Text:** retrieval over 12,701 chunks of regulation text (BauGB, BauNVO, LBO BW, Stuttgart Bebauungspläne and local statutes)
- **Vision:** a YOLOv8 + EasyOCR pipeline that reads the drawing templates on zoning plans
- **Space:** ALKIS cadastral data to resolve an address or plot number to its parcel, area and built coverage

Built and deployed as a working web application. The problem and the process model were checked with Stuttgart's building law office and city planning office. I benchmarked all three layers against verified answers and documented the failures: which ones I fixed, and which are still open, such as an off-topic answer on 32% of a wider question sample.

`CrewAI` `FastAPI` `OpenAI` `YOLOv8` `EasyOCR` `GeoPandas` `QGIS`

Source code is private. [Results, figures and failure analysis](https://github.com/meet-rehman/digital-building-permit-stuttgart). A walkthrough or demo is available on request.

### vCOO: Virtual Chief Compliance Officer
A research-assistant project at HfWU. The vCOO helps people who build digital products with no-code and generative AI tools to see which rules apply to them.

- **Knowledge layer:** five MCP servers, one per framework: EU AI Act, GDPR, ISO 37301, COBIT and NIST, each with its own vector store and source citations
- **Prototype:** a test scenario (an AI mobility adviser for city planners that uses GPS data) run through all five frameworks, producing risk levels, cited passages and recommended actions
- **Research bot:** pulls current regulatory updates from EUR-Lex
- **Orchestration:** LangGraph agents for risk mapping, recommendations and documentation, with human oversight

`MCP` `LangGraph` `FAISS` `HuggingFace embeddings` `Python`

### [Weissenhof geodata study](https://github.com/meet-rehman/geodata-ai-integration)
The Weissenhofsiedlung in Stuttgart rebuilt in 3D from official open data by an AI agent, to test how far the public datasets agree with each other.

- **3D model:** 73 real LoD2 building objects from the state survey's CityGML data, imported and assembled in Blender by an AI coding agent
- **Cross-check:** footprints compared against the ALKIS cadastre (69 of 69 buildings match, largest gap 3.4 cm), then against DOP20 aerial imagery and the state's new live API
- **Findings:** 4 small canopies are buildings in one official dataset and structures in the other. LoD2 gives part of Le Corbusier's double house gable roofs, while the aerial photo shows a flat roof.
- **Render:** a 3D view of the estate highlighting the 11 buildings that survive from 1927
- **Next:** one agent per data source (cadastre, massing, imagery, terrain, land use) and a coordinator that flags where they disagree

`Blender` `Python` `CityGML LoD2` `ALKIS` `OGC API Features` `QGIS`

### More projects

| Project | Highlight | Built with |
|---|---|---|
| IFC compliance server | An MCP tool that checks IFC geometry against a regulation service. It caught a fabricated value in my own system. | FastMCP, IfcOpenShell |
| Regulatory knowledge graph | Graph analysis of what the system cites in its benchmark answers: answers that cite a specific plan almost never go off-topic, answers that cite nothing often do. | TopologicPy, Python |
| [Embodied carbon prototype](https://github.com/meet-rehman/kbob-embodied-carbon) | Plain-language material descriptions matched to the Swiss KBOB life cycle data. A prototype, published with its errors documented. | Python, sentence embeddings |
| [Claude and Revit through MCP](https://github.com/meet-rehman/revit-mcp-case-study) | Natural-language queries on a live Revit model: element counts and areas worked, two cost estimates for the same floor differed by a factor of two, heavy scripts broke the connection. | Revit 2026, MCP |
| [Python and AI teaching notebooks](https://github.com/meet-rehman/python-ai-for-real-estate) | A four-module course for business and real estate students: Python fundamentals, sentiment analysis, sales forecasting, and room-type recognition in property photos with transfer learning. | pandas, scikit-learn, TensorFlow/Keras, Plotly |
| PakCarbon AI | Competition prototype for carbon credit verification on Karachi's Green Line BRT, using real air-quality data and the ACM0016 method. | CrewAI, FastAPI, PostgreSQL |
| WhatsApp content pipeline | Team automation for a travel startup: an AI agent researches and drafts a message, a person approves it by email, and it is posted to the team's WhatsApp group. | n8n, OpenAI, Perplexity, WhatsApp API |

The remaining repositories are being published one by one.

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

<details>
<summary><b>Certificates and short courses</b></summary>

<br>

| Course | Provider | Completed |
|---|---|---|
| Supervised Machine Learning: Regression and Classification (grade 99.66%) | DeepLearning.AI and Stanford Online, via Coursera | March 2025 |
| Advertising on LinkedIn | LinkedIn Learning | August 2024 |
| BIM Manager: Managing Revit | LinkedIn Learning | May 2020 |
| Geometry in Design: In the Footsteps of Masters (workshop) | Department of Architecture and Planning, NED University, Karachi | March 2019 |
| Certificate in Information Technology (four months) | Skill Development Council Karachi | 2014 |

</details>

## Experience

- **Research assistant (HiWi), HfWU, 2025 to 2026:** built the vCOO compliance system, then developed a four-module set of Jupyter teaching notebooks for a Python and AI course in the real estate department (Python fundamentals, sentiment analysis, sales forecasting, computer vision for real estate) and assisted the students in class
- **Business Development and Marketing Manager, Disruptive Designs LLC (US architecture firm), 2023 to 2024:** built international client acquisition with a CRM (Snov.io), lead generation, conversion funnels, KPI tracking, and LinkedIn and website content
- **Architect, SHA Architects, 2021 to 2023:** design, client and contractor coordination, permitting and documentation

## Research and talks

- **DBP26, Munich, November 2026:** poster, "Restoring Information Mobility in Multi-Level Building Governance: A Deployed Multi-Agent RAG System for German Building Regulations"
- **OGC iDays 2026, Munich, November 2026:** accepted presentation
- **Journal paper** on the mixed-methods evaluation of the Stuttgart system, in preparation

## Work with me

I take on freelance and project work in four areas.

**AI agents for architecture practices** (architecture and planning offices)

I have worked as an architect, so I start from how an office actually runs a project.

- **Practice audit:** going through your project phases to find where agents save real hours and where they would only add risk
- **Agents inside your design tools:** asking a Revit or IFC model questions in plain language, such as element counts, parameter checks and first cost estimates
- **Site and context models from open data:** official building, cadastral and aerial data assembled into a 3D context model by an agent
- **Regulation checks during design:** zoning and building-code questions answered with sources while the design is still moving
- **Office workflows:** document tracking, client communication and reporting automated with a person approving each step
- **Teaching and workshops:** Python and AI for people without a technical background, based on the course material I built for real estate students at HfWU, where I also assisted in class

**Applied AI research and evaluation** (companies, research groups, public bodies)

- **Evaluation of an existing AI system:** a test set with verified answers, scored results, and a report on where and why it fails
- **Feasibility studies:** can AI do this task reliably, tested on your own documents or data before you commit to building
- **Model and method comparison:** candidate models or approaches tested side by side on your use case
- **Research support:** literature review, study design, analysis and writing for papers, funding applications and whitepapers

**AI for regulations and geodata** (engineering offices, public bodies, PropTech)

- **Strategy and scoping:** mapping the current process, interviewing stakeholders, and defining where AI helps and where it does not
- **Regulation and document assistants:** question answering over building codes, standards or internal documents, with sources
- **Compliance knowledge tools:** a first-pass map of an AI product against the EU AI Act, GDPR and governance frameworks (a research aid, not legal advice)
- **Plan reading and geodata integration:** structured data from zoning plans, connected to cadastral and building data

**AI automation for business development and marketing** (AEC firms and small teams)

I have done client acquisition for an architecture firm myself, so I know the workflow before I automate it.

- **Lead and CRM workflows:** collecting, enriching and tracking leads, with outreach sequences and KPI reporting
- **Content pipelines with human approval:** agents that research and draft, a person who approves, automatic publishing to email, LinkedIn or WhatsApp
- **Internal assistants:** scheduling, task tracking and reporting connected to the tools a team already uses

## Currently

- Deepening BIM and IFC workflows, with digital twins as the next direction
- Open to Doctoral research positions, AI Architect and engineering roles and freelance projects

## Contact

[LinkedIn](https://www.linkedin.com/in/meetrehmann)
