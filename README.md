# Data-Linked-Articles
Data-Linked Articles Study
Journal-Level Citation Impact of Articles with
Dataset Links in Abstracts Identified Using a
Generative AI Ensemble
This repository provides the data, prompts, and archived generative AI classification outputs used in the submitted manuscript:
Journal-Level Citation Impact of Articles with Dataset Links in Abstracts Identified Using a Generative AI Ensemble
All identifying author information has been intentionally removed to comply with double-blind review requirements.
1. Purpose of This Repository
This repository ensures:
Transparency of the generative AI–based classification workflow
Reproducibility of Data-Linked Article (DLA) identification
Auditability of model decisions
Verification of journal-level citation analysis
All classification outputs are archived exactly as generated at the time of analysis.
2. Study Overview
Data Source
Database: Web of Science (SCI-EXPANDED, SSCI, A&HCI)
Document type: Article
Citation window: Articles published in 2023, citations retrieved January 2026
Candidate Selection
Articles were screened for abstracts containing at least one URL beginning with:
http://
https://
After applying journal-level inclusion criteria (≥4 candidate articles per journal),
6,224 candidate articles across 329 journals were retained for generative AI classification.
3. Generative AI Classification
Models Used
Three independent generative AI systems were applied:
Microsoft 365 Copilot (GPT-5–based)
ChatGPT (GPT-5.2 Instant)
Gemini (3 Pro)
Each system evaluated whether URLs appearing in abstracts functioned as access points to publicly accessible research datasets.
Ensemble Strategy
Final classification was determined using majority voting:
≥2 Yes → Data-Linked Article (DLA)
Otherwise → Non-Data-Linked Article (NDLA)
Results:
5,554 articles classified as DLAs
670 articles classified as NDLAs
For journal-level impact analysis, only journals publishing ≥4 DLAs were retained:
Final analytical dataset: 5,403 DLAs across 261 journals
A strict-consensus subset (3/3 Yes agreement) was additionally analyzed to confirm robustness.
4. Repository Structure
4.1 Abstract Data
Example file:
UAI_AB_0001_0010.csv
Structure:
UAI,AB
UAI: Unique Article Identifier
AB: Full abstract text
Each abstract may contain one or more URLs embedded in the text.
4.2 Classification Outputs
Example file:
Classification_UAI_AB_0001_0010.csv
Structure:
UAI,Result,Reason
UAI: Unique Article Identifier
Result: Yes / No
Reason: Model-generated explanation
Example:
UAI:0001,No,URL links to general GitHub homepage without specific study outputs
UAI:0002,Yes,Study code or data available at repository URL
The UAI field links abstracts to classification decisions.
4.3 Prompts
The repository includes the exact structured prompts used for:
URL detection
Contextual interpretation
Dataset-access evaluation
Binary decision criteria
Prompts are provided verbatim to enable independent replication.
5. Operational Definition of Data-Linked Articles (DLAs)
An article is classified as a DLA if:
A URL appears in the abstract, and
The abstract context indicates that the URL provides access to publicly available research datasets or study outputs.
Excluded cases include:
DOI resolver links
Publisher webpages
Creative Commons license links
Generic informational websites
Non-specific repository homepages not clearly linked to the study
This operationalization isolates abstract-level dataset signaling.
6. Human Validation
A stratified random sample (n = 200) was manually annotated.
Performance of the majority-voting ensemble:
Precision: 0.95
Recall: 0.83
F1-score: 0.88
Accuracy: 0.88
Cohen’s κ: 0.75
Bootstrap confidence intervals were estimated (1,000 iterations).
7. Statistical Analysis
Citation comparisons were conducted at the journal level:
Metric: Median citation count
Test: Mann–Whitney U test
Multiple testing correction: Benjamini–Hochberg
Weighted average median difference across all journals: 4.05 citations (95% CI: 2.64–5.63)
Among statistically significant journals: 10.01 citations
The analysis is observational and does not imply causality.
8. Reproducibility and Transparency
All AI outputs are archived without manual modification
Ensemble aggregation is fully documented
Strict-consensus subset provided for robustness analysis
Prompts and decision criteria are included
Because generative AI systems evolve over time, archived outputs ensure reproducibility independent of future model updates.
9. Data Source and Licensing
Bibliographic metadata were obtained from Web of Science.
Due to licensing restrictions:
Full Web of Science records are not redistributed
Only abstracts, URLs, derived variables, and classification outputs are included
Users are responsible for complying with applicable database licensing agreements.
10. Disclaimer
Generative AI outputs may vary over time due to model updates.
The archived results represent the exact outputs used in the submitted analysis.
