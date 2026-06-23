# Spaceflight CDSS Evaluation Layer

This repository supports the development of an evaluation framework for clinical decision support systems (CDSS) designed for long-duration spaceflight, including lunar and deep-space exploration missions.

## Background

Long-duration spaceflight will require increasing medical autonomy. Communication delays, limited resupply, restricted diagnostic capacity and delayed or impossible evacuation mean that a CDSS for exploration missions must do more than provide possible diagnoses. It must support safe, evidence-grounded and mission-appropriate decision-making over time.

Recent work on conversational AI for disease management, including AMIE and the RxQA medication-reasoning benchmark, provides a useful methodological blueprint. The key lesson is that evaluation should move beyond one-off diagnostic accuracy and assess whether a system can reason longitudinally, adapt to changing clinical information, ground recommendations in authoritative sources, avoid unsafe decisions and communicate clearly to users.

## Repository Aim

The aim of this repository is to define an evaluation layer for spaceflight CDSS models.

This includes:

* structured astronaut clinical scenario templates;
* OSCE-style evaluation methods;
* medication and countermeasure reasoning benchmarks;
* safety and “never-event” test cases;
* human factors and crew usability criteria;
* DAG-based causal reasoning evaluation;
* documentation of required data sources, expertise and validation pathways.

## Proposed Evaluation Components

### 1. Astronaut Clinical Case Scenarios

The repository will define templates for realistic, clinically grounded scenarios relevant to long-duration spaceflight. These may include infection risk, spaceflight-associated neuro-ocular syndrome, renal stone risk, radiation exposure, musculoskeletal injury, behavioural health concerns, sleep disruption, dental emergencies and medication adverse events.

The long-term goal may be to develop approximately 150–200 structured scenarios, ideally with review from clinicians, NASA collaborators or space medicine experts. The initial goal is to create a small pilot set of 5–10 scenarios to test the evaluation format.

### 2. OSCE-Style Evaluation

Objective Structured Clinical Examination style methods can be adapted to assess whether a CDSS can:

* identify the key clinical problem;
* ask for or use relevant information;
* prioritise risks appropriately;
* recommend safe and feasible next steps;
* respond to evolving symptoms, test results or treatment response;
* recognise escalation thresholds;
* avoid unsafe or unsupported recommendations;
* communicate clearly to a crew user or crew medical officer.

### 3. SpaceRxQA Medication and Countermeasure Reasoning

Inspired by RxQA, this repository will explore a spaceflight-specific benchmark for medication and countermeasure reasoning. This could include questions relating to:

* limited onboard formularies;
* medication contraindications;
* dose, route and duration;
* drug-drug interactions;
* monitoring limitations;
* mission constraints;
* escalation thresholds;
* countermeasure selection;
* unavailable resources;
* uncertainty and risk communication.

### 4. Safety and Never-Event Testing

Safety testing will define situations where a CDSS output should be considered unacceptable. Examples may include:

* recommending medication or equipment not available on board;
* failing to escalate red-flag symptoms;
* hallucinating a drug, dose, diagnostic test or protocol;
* giving false reassurance in a high-risk scenario;
* ignoring communication delay;
* ignoring crew medical officer availability;
* recommending an intervention requiring unavailable monitoring;
* failing to state uncertainty where evidence is limited.

### 5. DAG-Based Causal Reasoning Evaluation

Directed Acyclic Graphs may be used to represent causal pathways in complex spaceflight health risks. This could allow evaluators to assess not only the final answer given by a CDSS, but whether its reasoning follows an appropriate causal and clinical logic.

This component may include:

* mapping clinical scenarios to causal pathways;
* checking whether CDSS reasoning aligns with expected DAG relationships;
* identifying missing causal links;
* identifying unsupported or inappropriate causal assumptions;
* comparing final recommendations against causal risk pathways.

### 6. Human Factors and Crew Usability

For a CDSS to be useful in spaceflight, it must provide recommendations that are understandable, actionable and appropriate under mission conditions. Evaluation should therefore consider:

* clarity of advice;
* cognitive load;
* confidence calibration;
* prioritisation of actions;
* usability for non-specialist crew;
* usability for a crew medical officer;
* ability to support rather than replace human judgement;
* usefulness under time pressure.

## Repository Structure

```text
docs/
  evaluation_framework_overview.md
  required_expertise.md
  data_sources.md

case_scenarios/
  case_template.md
  example_case_infection.md
  scenario_taxonomy.md

space_rxqa/
  README.md
  question_template.md
  example_questions.md

safety_guardrails/
  never_events.md
  safety_test_template.md

dag_evaluation/
  README.md
  dag_reasoning_rubric.md
  example_dag_mapping.md

rubrics/
  osce_scoring_rubric.md
  human_factors_rubric.md
  clinical_reasoning_rubric.md
```

## Initial Pilot Goals

The initial aim is to develop a small proof-of-concept evaluation set before scaling.

Proposed pilot outputs:

* 5–10 structured astronaut clinical scenarios;
* 20–30 medication or countermeasure reasoning questions;
* a draft OSCE-style scoring rubric;
* a draft safety and never-event checklist;
* a draft DAG-based reasoning evaluation template;
* a draft human factors and crew usability rubric.

## Required Expertise

This repository will require input from multiple areas of expertise, including:

* clinical medicine;
* space medicine;
* pharmacy or medication safety;
* human factors;
* aerospace medicine;
* causal modelling and DAGs;
* AI evaluation;
* clinical decision support;
* OSDR and spaceflight biomedical data.

Where possible, scenario content and scoring criteria should be reviewed by clinicians or relevant subject-matter experts before being used for formal evaluation.

## Important Disclaimer

This repository is for research, evaluation and framework development only. It does not provide medical advice and is not intended for use in real-world clinical decision-making, astronaut healthcare or mission operations. Any future operational system would require formal clinical, regulatory, ethical, safety and mission-level review.

## References and Related Resources

* Liévin et al.  *Towards Conversational AI for Disease Management* . Nature, 2026.
* Google Health RxQA repository: [https://github.com/Google-Health/rxqa](https://github.com/Google-Health/rxqa)
* NASA Open Science Data Repository: [https://osdr.nasa.gov/](https://osdr.nasa.gov/)
