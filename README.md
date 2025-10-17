# **Replciation Material: Discursive Strategic Legitimation of Security International Organisations (DSLSIO)**
This replication package accompanies the term project for the course *Text-as-Data/Natural Language Processing for Political Science* (LMU Munich, SS 2025).  Its purpose is to provide a transparent, modular, and reproducible workflow for computational text analysis in political science. The workflow is structured into **phases**, each producing artifacts consumed by the next, ensuring that every step can be replicated and validated independently. This reproduction was tested to be functional by the three principla investigators: B.A Seohyun Yoon, B.A. Yegor Novikov, and M.A. Borna Ardehi

### **Why Phases?**
Breaking the pipeline into phases makes the workflow:
* **Reproducible** – each step is documented and produces concrete outputs.  
* **Auditable** – intermediate data (e.g., metadata, sentence files, gold sets) can be inspected.  
* **Modular** – errors or refinements can be addressed at the correct stage without rerunning everything.  
* **Extendable** – future researchers can plug in alternative dictionaries, models, or scaling methods.

### **5 phases**
* **Phase 1:** Converts collected PDFs into clean UTF-8 text and audits coverage.
* **Phase 2:** Builds metadata, removes boilerplate, and segments the corpus into analyzable sentences.
* **Phase 3:** Constructs and validates dictionaries, then trains and applies supervised classifiers.
* **Phase 4:** Implements scaling with seeds and supervised models to measure projection/protection.
* **Phase 5:** Produces descriptive statistics and visualizations of legitimation patterns over time and across organizations.

---

### **Execution Order**
`1.0 → 1.1 → 2.0 → 2.1 → 2.2 → 2.3 → 3.0 → 3.1 → 3.2 → 3.3 → 3.4 → 3.5 → 4.0 → 4.1 → 4.2 → 4.3 → 5.0 → 5.1 → 5.2`

---

### **Technical Requirements**
* Python 3.9+; Jupyter Notebook/Lab.  
* it is recommended to operate this file in a virtual environment in exact replication of the file.

#### **Core packages (pip installations)**
* **Data/ML:** pandas, numpy, scipy, scikit-learn, joblib
* **Text:** pdfminer.six (PDF → text), spacy, ftfy, chardet
* **Progress/CLI:** tqdm, argparse (stdlib)
* **Viz:** matplotlib, seaborn

##### *Installation*
* pip install numpy 
* pip install pandas 
* pip install matplotlib 
* pip install seaborn 
* pip install scikit-learn
* pip install nltk 
* pip install spacy 
* pip install gensim 
* pip install pyreadr 
* pip install pdfminer.six 
* pip install jupyter 
* pip install ipykernel 

##### *Additional Notes*
* nltk and spacy require downloading language models (nltk.download(...), python -m spacy download en_core_web_sm).
* gensim is used for embeddings / representation.
* pdfminer.six is only needed for the raw text extraction step (Phase 1)
* pyreadr is included since some of the data is converted from or to .RData/.sav formats

#### **Directory constants to set before running**
* input_dir, output_dir for Phase 1.0 conversion.
* CORPUS_DIR (and the UTF‑8 mirror path) in Phase 2.0.
* BASE paths in plotting cells (Phase 5.1/5.2).

#### **Required local files**
* **Dictionaries:** norm.txt, funct.txt, proj.txt, prot.txt (2 sets of each)
* **Seeds:** 4_projseed.txt, 4_protseed.txt

* **Outputs chained across phases:** 
0_metadata.csv, metadata_bp.csv, 1_sentences.csv, documents.csv, 2_golden_text.csv, 3_pred_documents.csv, 4_PPGS.csv, 4_norm_sentences_pp_SUP.csv, 4_org_year_pp_SUP.csv

#### **Hardware:** 
Standard laptop capacity is sufficient for dictionary and supervised classification tasks; however scaling large corpora may require GPU access. The writing and execution of this code was performed on M4 Macbook Air with 10 GPU.

___________________________________________________
