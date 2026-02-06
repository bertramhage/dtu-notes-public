## Executive Summary

This briefing synthesizes insights from five sources on the challenges of bias, evaluation, and safety in medical artificial intelligence. The analysis highlights critical issues ranging from dataset integrity to model behavior and the limitations of current interpretability methods.

- **"Hidden Stratification Causes Clinically Meaningful Failures" (Oakden-Rayner et al., 2020):** This research identifies "hidden stratification" as a critical failure mode where machine learning models, despite high overall performance, significantly underperform on important but unlabeled clinical subgroups. Aggregate metrics can mask these failures, which are often driven by low subset prevalence, poor label quality, subtle features, or spurious correlations, posing a substantial risk to patient safety. The authors propose methods like schema completion and error auditing to detect and measure these effects.
- **"Slicing Through Bias" (Olesen et al., 2025):** This paper demonstrates the utility of Slice Discovery Methods (SDMs) for systematically identifying underperforming subsets ("slices") within medical datasets and hypothesizing the root causes of performance gaps. A case study on chest x-rays reveals that shortcut learning—such as models associating chest drains with pneumothorax or ECG cables with atelectasis—is a primary driver of observed performance disparities between male and female patients. This finding connects shortcut learning directly to fairness issues and suggests that targeted mitigation is more effective than simple data balancing.
- **"Half a million x-rays!" (Oakden-Rayner, 2019):** This critical review of large-scale public chest x-ray datasets, particularly CheXpert, finds that while they are an improvement over predecessors like CXR14, they retain fundamental flaws. Key issues include labeling inaccuracies inherent to Natural Language Processing (NLP), a reduced "effective size" due to high numbers of repeat scans per patient, insufficient documentation of cohort characteristics, and persistent, clinically dangerous hidden stratification (e.g., failing to distinguish treated vs. untreated pneumothoraces).
- **"Moving beyond 'algorithmic bias is a data problem'" (Hooker, 2021):** This opinion piece argues that algorithmic bias is not solely a data problem but is also actively amplified by model design choices. Techniques like model compression and differential privacy can disproportionately degrade performance for underrepresented minority groups. This perspective refutes the notion of an impartial algorithm, places responsibility on model designers to mitigate harm, and suggests that auditing the impact of design choices offers a more feasible path to fairness than exhaustive data collection.
- **"The false hope of current approaches to explainable artificial intelligence" (Ghassemi et al., 2021):** This viewpoint contends that current explainable AI (XAI) techniques are unreliable and potentially misleading for justifying individual patient-level decisions in health care. Post-hoc methods like saliency maps are approximations that can be manipulated and are prone to human confirmation bias. The authors argue that trust in AI should not be based on these flawed local explanations but on rigorous, global validation through methods like Randomized Controlled Trials and comprehensive algorithmic audits across diverse populations.

--------------------------------------------------------------------------------

## 1. Hidden Stratification in Medical Imaging AI

_Source: "Hidden Stratification Causes Clinically Meaningful Failures in Machine Learning for Medical Imaging" by Luke Oakden-Rayner, Jared Dunnmon, Gustavo Carneiro, and Christopher Ré (2020)._

This paper introduces and characterizes the problem of "hidden stratification," where machine learning models for medical imaging perform poorly on important, unrecognized subsets of a population, even when aggregate performance metrics like ROC-AUC are high. This phenomenon can lead to clinically meaningful failures, such as a cancer detection model that consistently misses a rare but aggressive subtype.

### Core Concepts

- **Hidden Stratification:** The existence of unrecognized, visually and clinically distinct subsets within a single labeled class (e.g., "lung cancer" containing both solid and subsolid tumors). Because these subsets are unlabeled, poor performance within them can be obscured by strong performance on more common subsets.
- **Clinical Risk:** The authors posit that "serious diseases are less common than mild diseases," suggesting that underperformance in minority subsets could lead to disproportionate harm to patients.
- **Causes of Stratification Effects:** The study hypothesizes and finds evidence that degraded model performance on subsets is driven by four key characteristics:
    1. **Low subset prevalence:** The model has few examples to learn from.
    2. **Reduced label accuracy:** The training signal for the subset is noisy.
    3. **Subtle discriminative features:** The visual markers for the subset are harder to learn.
    4. **Spurious correlations:** The model learns a non-causal feature that is correlated with the label in one subset but absent in another.

### Methods for Measuring Hidden Stratification

The authors define and evaluate three approaches to measure the clinical risk posed by hidden stratification on a test dataset.

| Method                      | Description                                                                                                  | Advantages                                                                 | Disadvantages                                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **Schema Completion**       | Exhaustive, prospective human labeling of data into a more complete set of subclasses.                       | Enables consensus on subclass definitions; guides model development.       | Limited by the schema author's knowledge; time-consuming; can become obsolete.       |
| **Error Auditing**          | Retrospective human analysis of model predictions to identify unexpected patterns or regularities in errors. | Not limited by predefined expectations; informed by actual model function. | Dependent on the auditor's skill; may miss low-prevalence, high-discordance subsets. |
| **Algorithmic Measurement** | Automated methods, such as unsupervised clustering, to search for underperforming subclasses.                | Reduces burden on human analysts; can leverage learned feature encodings.  | Variable performance; limited by separability of subsets in the feature space.       |

### Key Evidence and Findings

The study validates its hypotheses across a benchmark computer vision dataset and multiple real-world medical imaging datasets.

- **CIFAR-100 Benchmark:** A model trained on 20 "superclasses" showed substantial performance variation across the five constituent "subclasses," with the worst-performing subclass underperforming the aggregate by over 30 accuracy points. Experiments confirmed that artificially reducing a subclass's prevalence or label accuracy caused its performance to drop significantly (by 14-19 points) while only modestly affecting the superclass performance (by 4-5 points).
- **Adelaide Hip Fracture Dataset:** A high-performing model (overall AUC = 0.994) exhibited statistically significant lower sensitivity on clinically important subsets.
    - **Subtle fractures:** Sensitivity of **0.900** (vs. 0.981 overall).
    - **Cervical fractures (low prevalence):** Sensitivity of **0.911** (vs. 0.981 overall).
- **MURA Musculoskeletal Dataset:** A model trained on "normal" vs. "abnormal" labels showed varied performance on unlabeled subclasses within the "abnormal" class.
    - **Hardware (visually obvious):** AUC of **0.98** (higher than aggregate 0.91).
    - **Degenerative disease (subtle, low-quality labels):** AUC of **0.76** (lower than aggregate 0.91).
- **CXR-14 Pneumothorax Dataset (Error Auditing):** Analysis revealed a spurious correlate: the presence of a chest drain (a treatment device).
    - The model performed far better on **treated** pneumothoraces with chest drains (ROC-AUC = **0.94**).
    - Performance was substantially worse on **untreated**, life-threatening pneumothoraces without drains (ROC-AUC = **0.77**).
    - This disparity was masked by the overall AUC of 0.87 and the fact that 80% of pneumothorax cases in the test set had a chest drain.
- **Algorithmic Measurement:** A simple k-means clustering algorithm was able to separate high- and low-error clusters in some cases (e.g., enriching for cases with drains in the CXR-14 dataset) but failed in others (MURA), demonstrating potential but inconsistent utility.

### Conclusion

Hidden stratification is a fundamental and underappreciated problem in medical AI. The authors argue that evaluation of these effects should be a "critical component of any machine learning deployment in medical imaging" and that regulators should not certify models for deployment unless careful testing for hidden stratification has been performed.

--------------------------------------------------------------------------------

## 2. Using Slice Discovery Methods to Explain Performance Gaps

_Source: "Slicing Through Bias: Explaining Performance Gaps in Medical Image Analysis Using Slice Discovery Methods" by Vincent Olesen, Nina Weng, Aasa Feragen, and Eike Petersen (2025)._

This paper explores the use of Slice Discovery Methods (SDMs) to identify interpretable, underperforming subsets of data ("slices") and to formulate hypotheses about the root causes of performance disparities between patient groups. The work explicitly connects the technical problem of shortcut learning to the ethical problem of algorithmic fairness.

### Core Concepts

- **Underperforming Slices (or Blind Spots):** Subsets of data with similar characteristics on which a model systematically underperforms, even while overall accuracy remains high.
- **Slice Discovery Methods (SDMs):** Unsupervised techniques used to discover these underperforming slices when the distinguishing features are not known or labeled a priori. The typical process involves:
    1. Embedding data into a latent representation.
    2. Performing dimensionality reduction.
    3. Using clustering to extract data slices.
    4. Prioritizing slices based on a performance metric.
- **Shortcut Learning:** A phenomenon where a model learns to rely on spurious, non-causal correlations in the data (e.g., medical devices) to make predictions, rather than learning the actual pathology.

### Proposed Slice Discovery Method

The authors introduce a novel SDM with specific design choices:

- **Image Representation:** Uses the penultimate layer of the classification model under analysis.
- **Dimensionality Reduction:** Inserts and trains a single, supervised fully connected layer.
- **Clustering:** Employs a Gaussian Mixture Model (GMM).
- **Cluster Selection:** Prioritizes clusters using the **Brier score**, which is threshold-independent and captures both discriminative ability and calibration.

### Case Study: Pneumothorax and Atelectasis Classification

The study applied its SDM to analyze performance gaps in chest x-ray classification models trained on the NIH-CXR14 and CheXpert datasets.

- **Pneumothorax Classification:**
    - **Finding:** SDMs identified that the best- and worst-performing slices were strongly distinguished by the presence or absence of chest drains.
    - **Hypothesis:** Previously observed performance gaps between male and female patients were not due to biological sex differences, but rather to the model learning a "chest drain shortcut" combined with a different prevalence of chest drains between sexes in the dataset (e.g., 49.5% in pneumothorax-positive males vs. 42.8% in females in NIH-CXR14).
    - **Validation:** When the test set was re-balanced to have an equal prevalence of chest drains across sexes, the statistically significant performance gap in AUROC between male and female subjects disappeared. This confirmed that shortcut learning was the primary cause of the fairness disparity.
- **Atelectasis Classification:**
    - **Finding:** Following a similar SDM analysis, visual inspection of the worst- and best-performing slices revealed a new potential shortcut.
    - **Hypothesis:** The presence of **ECG cables** was being used by the model as a shortcut feature for atelectasis classification.
    - **Validation:** A post-hoc labeling effort confirmed a substantial difference in ECG cable prevalence between the slices. For atelectasis-negative samples, 95% of images in the worst slice had ECG cables, versus only 10% in the best slice.

### Conclusion

SDMs are an effective tool for generating and testing hypotheses about the causes of model underperformance and fairness gaps. The study provides strong evidence that shortcut learning on non-sensitive features (like medical devices) can be a direct cause of performance disparities between sensitive demographic groups (like gender). This understanding allows for targeted mitigation strategies that "level up" performance, rather than "leveling down" through blind group balancing.

--------------------------------------------------------------------------------

## 3. A Critical Review of Large-Scale Chest X-Ray Datasets

_Source: "Half a million x-rays! First impressions of the Stanford and MIT chest x-ray datasets" by Lauren Oakden-Rayner (February 25, 2019)._

This blog post provides a detailed "first impressions" critique of the CheXpert dataset, contextualized by the known flaws of its predecessor, the NIH CXR14 dataset. The author argues that while CheXpert represents a significant step forward, it is still hampered by fundamental limitations that affect its utility for training reliable clinical AI systems.

### Summary of Flaws in the CXR14 Dataset

The author recaps the widely-recognized problems with the NIH CXR14 dataset:

- **Variability:** Low effective size due to many repeat studies on the same patients (45% of the dataset from 7% of patients).
- **Labeling Method & Quality:** Labels generated by error-prone NLP on radiology reports, which do not thoroughly describe images, leading to estimated error rates of 30-90%.
- **Hidden Stratification:** Clinically crucial subgroups are unlabeled (e.g., deadly untreated pneumothoraces vs. safe, treated ones).
- **Documentation:** Inadequate description of the cohort, label definitions, and usage guidelines.
- **Image Quality:** Downsampled resolution and heavily reduced grey-levels (8-bit), obscuring subtle pathology.

### In-Depth Analysis of the CheXpert Dataset

|   |   |
|---|---|
|Feature|CheXpert Evaluation|
|**Variability**|An improvement over CXR14, but still has a high degree of repeat imaging (70% of images from 31% of subjects), reducing the effective dataset size.|
|**Labeling Method**|Also uses NLP on reports, but with a superior, validated "expert systems" labeller. However, the author notes the inherent disconnect between reports (communication tools) and ground-truth image content remains a primary source of error.|
|**Labeling Quality**|Estimated error rates are much lower, around **5-15%**. This is considered "close to as accurate as NLP can get." The "no finding" class is noted as one of the hardest to label accurately.|
|**Label Structure**|Praised as a major strength. It uses a clinically-oriented, hierarchical ontology based on the Fleischner society glossary and includes "uncertain" labels, which is more clinically realistic.|
|**Hidden Stratification**|**Remains a significant weakness.** The author highlights two key examples:<br> • **Pneumothorax:** No distinction between treated cases (with a chest drain) and untreated cases. The author found ~50% of pneumothorax cases in a CheXpert subset had drains.<br> • **Fracture:** The label combines clinically urgent new fractures with common, unimportant healed fractures.|
|**Documentation**|**Strongly criticized as lacking.** The paper combines dataset presentation with model results, dedicating only two pages to the dataset itself. It lacks crucial details on cohort demographics, repeat study distribution, and clinical setting (inpatient vs. outpatient). This knowledge asymmetry benefits the dataset creators while hindering external users.|
|**Image Quality**|Offers native resolution images, which is an improvement. However, the images are still downsampled from 12/16-bit to **8-bit** (256 grey levels), which can obscure pathology like retrocardiac opacities.|

### Conclusion

CheXpert is lauded as "the best quality chest x-ray dataset we currently have" and a "great step forward." Its improved labeling schema and quality push the limits of what is achievable with NLP-based methods. However, its clinical utility is limited by persistent weaknesses, most importantly the insufficient documentation and the presence of clinically meaningful hidden stratification. The author advocates for dedicated dataset papers and a "star-rating" system to guide users on the reliability and clinical relevance of different labels.

--------------------------------------------------------------------------------

## 4. Model Design as a Source of Algorithmic Bias

_Source: "Moving beyond 'algorithmic bias is a data problem'" by Sara Hooker (2021)._

This article challenges the prevalent belief that a machine learning model merely reflects biases present in its training data. It argues that model design choices are an active and significant contributor to algorithmic harm, particularly by amplifying disparities against underrepresented groups.

### The Fallacy of the Impartial Model

The core argument is that viewing algorithmic bias as solely a "data problem" is a flawed and dangerous oversimplification.

- **Diffusion of Responsibility:** This belief absolves model designers of accountability, framing bias as "somebody else's problem."
- **Infeasibility of Data Fixes:** De-biasing a data pipeline by re-sampling or re-weighting is often impractical. It requires a priori knowledge of all sensitive attributes and their proxies, which is impossible in high-dimensional, large-scale datasets.
- **Model Choices Express Preference:** Just as model design choices (architecture, loss function, hyperparameters) affect test-set accuracy, they also affect fairness, robustness, and other desiderata. Training involves trade-offs; optimizing for one objective inevitably impacts others.

### How Model Design Amplifies Bias

Bias amplification often occurs in how models handle the "long-tail" of a data distribution, where protected or minority attributes are underrepresented.

- **The "Rich Get Richer":** Design choices made to optimize for a primary goal can systematically harm minority subgroups in order to preserve performance on the majority, well-represented features.
- **Specific Examples:**
    - **Model Compression (Pruning, Quantization):** These techniques are shown to systematically and disproportionately degrade accuracy on low-frequency protected attributes (e.g., gender, age).
    - **Differential Privacy (Gradient Clipping, Noise Injection):** These methods can disproportionately reduce accuracy for minority groups, such as users of African-American English or individuals with darker skin tones in facial analysis datasets.
    - **Training Dynamics (Early Stopping, Learning Rate):** Underrepresented examples are often learned later in the training process, meaning choices like early stopping can systematically prevent the model from learning to classify them correctly.

### A Path Forward: Mitigating Bias Through Model Design

Acknowledging the role of model design opens new, often more feasible, avenues for mitigating harm.

- **Auditing Model Behavior:** Understanding how specific design choices exacerbate harm provides a roadmap for auditing models.
- **Human-in-the-Loop Tooling:** This knowledge can be leveraged to surface the most challenging examples for human review. An example is **Compression Identified Exemplars (CIEs)**, which identifies data points most affected by compression, directing limited human auditing time where it is needed most.

### Conclusion

Overall harm is a product of the interaction between both the data and model design choices. The stance that algorithms are impartial is incorrect; some design choices are better than others. The research community must move beyond the "data problem" narrative to acknowledge, measure, and mitigate the harm introduced by the models themselves.

--------------------------------------------------------------------------------

## 5. The Limitations of Explainable AI in Clinical Practice

_Source: "The false hope of current approaches to explainable artificial intelligence in health care" by Marzyeh Ghassemi, Luke Oakden-Rayner, and Andrew L Beam (2021)._

This Viewpoint argues that the current generation of explainable AI (XAI) methods fails to deliver on the promise of providing trustworthy, transparent, and unbiased support for individual, patient-level clinical decisions. The authors advocate for a shift in focus from local explanations to rigorous global validation.

### The "False Hope" of Explainability

The desire for XAI is driven by the goals of engendering clinician trust, providing transparency, and mitigating bias. However, the authors argue it is a "false hope" that current techniques can achieve this for individual decisions. Local explanations are often unreliable, superficial, and can even be misleading.

### Critiques of Current XAI Methods

- **Interpretability Gap:** Post-hoc explanations like heat maps (saliency maps) suffer from a crucial gap. They show _where_ a model is looking but not _what_ it is seeing or _why_ that feature is important. This invites humans to project their own reasoning onto the map, a form of confirmation bias.
- **Unreliability and Lack of Guarantees:**
    - Explanations can appear reassuring even for completely untrained models or when the model's prediction is wrong (e.g., after an adversarial attack).
    - They are merely **approximations** of the model's true decision process and are not guaranteed to be faithful.
    - The performance of the explanations themselves is rarely validated, adding a second potential source of error to the decision-making process.
- **Risk of Over-Trust:** Evidence shows that humans tend to over-trust computer systems. Providing a "plausible-looking" explanation can unreasonably increase a user's confidence, hamper their ability to detect model errors, and lead to decreased vigilance.
- **Failure to Detect Bias:** Reliance on local explanations is an ineffective way to catch systemic bias. A model may highlight a clinically relevant area, but the explanation does not reveal if the model's internal reasoning is based on a biased association (e.g., linking the word "doctor" to maleness).

### The Proper Role of XAI vs. The Path to Trust

The authors distinguish between the appropriate and inappropriate uses of XAI.

- **Appropriate Use (Global Analysis):** XAI methods are valuable tools for developers, auditors, and regulators to understand **aggregate model behavior**.
    - **Model Debugging:** Identifying when a model is using shortcuts (e.g., a skin cancer AI focusing on surgical markings).
    - **Knowledge Discovery:** Revealing novel clinical features that are predictive of disease.
- **Inappropriate Use (Local Justification):** Using an explanation to justify a decision at the patient's bedside is unreliable and risky.
- **The Recommended Path to Trust:** Instead of flawed explanations, trust in medical AI should be built upon **thorough, careful, and meticulous validation**.
    - This is analogous to how the medical system validates other "black boxes" like drugs, whose exact mechanisms are not always fully understood.
    - Methods should include **Randomized Controlled Trials (RCTs)** and extensive testing across diverse and distinct populations to prove that the AI system improves outcomes without disproportionately harming marginalized groups.
    - **Algorithmic audits** that analyze aggregate data are more effective at identifying bias than local explanations.

### Conclusion

Explainability for patient-level decision-making remains an open and unsolved challenge. The authors strongly caution health-care workers and regulators against making explainability a requirement for clinical deployment. Instead, the focus must be on rigorous, experimental validation to ensure AI systems are safe, effective, and equitable.