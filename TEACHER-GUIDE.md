# Teacher Guide — Model Deployment Interactive Lesson

**Audience:** Beginner / vocational AI learners with no prior deployment knowledge  
**Anchor story:** A three-class fruit classifier (Apple, Banana, Orange)  
**Suggested duration:** 55–75 minutes  
**Source basis:** Chapter 4 — Model Deployment

## Learning outcomes
By the end of the lesson, students should be able to:
1. Explain model deployment in plain language and place it after Planning & Collection and Design & Training.
2. Explain why a trained model needs an interface or API before users or applications can use it.
3. Describe common deployment challenges: response time, model size/hardware and environment compatibility.
4. Distinguish the high-level roles of Streamlit, Flask, Django and Dash as deployment/web frameworks described in the chapter.
5. Trace the chapter's Flask fruit-classifier flow through `index.html`, `predict.html`, `app.py`, preprocessing and prediction.
6. Explain why deployment-time preprocessing must match the model's expected input preparation.
7. Explain the difference between a local Flask address (`127.0.0.1`) and a cloud/production deployment.
8. Describe the S3 → Lambda event-driven inference use case and the role of CloudWatch Logs.
9. Describe the chapter's high-level Google Cloud sequence: storage bucket → model resource → model version → deployment.

## Section 1 — Why deployment exists (Slides 1–4, 10–12 min)
**Objective:** Move students from “trained model” to “usable model.”  
**Teacher prompt:** “If your classifier only works inside your notebook, who can use it?”  
**Expected response:** “Only the developer / people with the notebook.”  
**Likely misconception:** Deployment means only “uploading the model file.”  
**Correction:** Emphasize that deployment includes the surrounding path that lets users/apps send input and receive output.  
**Interaction:** Use the first prediction choice, lifecycle cards and deployment-problem diagnosis.  
**Bridge:** “So how does a browser actually reach the model?”

## Section 2 — Web interface and API (Slides 5–7, 10–12 min)
**Objective:** Understand the input → backend → model → result path before naming frameworks.  
**Teacher prompt:** “Which part collects the image? Which part does the prediction?”  
**Expected response:** “The page collects; backend coordinates; model predicts.”  
**Likely misconception:** The HTML page itself performs the ML prediction.  
**Correction:** Replay the animated request packet and identify each component.  
**Interaction:** Request animation and API service-counter analogy.  
**Bridge:** “Now that we know the jobs, which tools can build the web/backend layer?”

## Section 3 — Tools and fruit-classifier project structure (Slides 7–10, 12–15 min)
**Objective:** Introduce Streamlit, Flask, Django and Dash at the level used in the chapter, then anchor on Flask.  
**Teacher prompt:** “Why might we choose a lightweight framework for a small custom classifier demo?”  
**Expected response:** “Less code / more control / suitable for lightweight apps.”  
**Likely misconception:** One framework is always best.  
**Correction:** Frame selection as a project-fit decision.  
**Interaction:** Click the folder/file buttons to reveal roles.  
**Bridge:** “We know the files. Which Python function moves the request through them?”

## Section 4 — `app.py` and preprocessing (Slides 11–13, 12–15 min)
**Objective:** Trace `index_view()`, `allowed_file()`, `read_image()` and `predict()`.  
**Teacher prompt:** “Why can't we send any random image shape straight into the model?”  
**Expected response:** “The model expects the same kind of input shape/preprocessing it was built for.”  
**Likely misconception:** Preprocessing is only a training concern.  
**Correction:** Use the banana pipeline and repeat: “same model → same expected input preparation.”  
**Interaction:** Function flow plus step-by-step code explanation.  
**Bridge:** “After the code works, where is it actually running?”

## Section 5 — Local vs cloud deployment (Slides 14–18, 12–15 min)
**Objective:** Distinguish local serving from cloud storage and event-driven cloud inference.  
**Teacher prompt:** “If the address is 127.0.0.1, can your friend across town access it?”  
**Expected response:** “No, it is local to the machine.”  
**Likely misconception:** Seeing a web page in a browser means it is publicly deployed.  
**Correction:** Separate browser interface from network reachability.  
**Interaction:** Localhost check, S3 bucket analogy, animated S3 → Lambda workflow, CloudWatch question.  
**Bridge:** “Different cloud platforms use different services, but what parts stay conceptually similar?”

## Section 6 — Synthesis and exit check (Slides 19–20, 8–10 min)
**Objective:** Build a reusable mental model of deployment.  
**Teacher prompt:** “Say the six deployment steps without looking.”  
**Expected response:** Save model → interface/API → preprocess input → predict → return/store result → run in an environment.  
**Likely misconception:** Cloud storage alone serves predictions.  
**Correction:** Storage holds the model/object; compute runs the prediction; logs/results show what happened.  
**Interaction:** Click-through synthesis checklist and four-question exit check.

## Practical handoff
Ask students to trace one fruit image verbally before they code:

`browser selects image → Flask receives request → allowed_file() checks extension → read_image() preprocesses → model.predict() runs inference → class selected → predict.html shows result`

Then students can reproduce the project structure and inspect each relevant file in the practical exercise.

## Delivery tips
- Keep the teacher notes toggle open only when useful; it can cover content on smaller projectors.
- Use prediction questions before clicking the answer.
- Replay the request and cloud animations rather than explaining the whole flow verbally.
- Avoid adding newer platform-specific steps unless you explicitly separate them from the chapter, because the deck is designed to preserve the source's terminology and sequence.
- For students with motion sensitivity, the deck respects `prefers-reduced-motion` and remains usable without animations.
