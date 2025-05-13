## ROUGE: Recall-Oriented Understudy for Gisting Evaluation

ROUGE is a collection of evaluation metrics commonly used to assess automatic text generation systems, such as summarization or translation tools. It works by comparing the generated output with one or more high-quality human-written references.

---

### 📏 Overview of ROUGE Metrics

The ROUGE framework includes several key metrics, each designed to evaluate different aspects of text overlap:

---

### 🔹 ROUGE-N

This metric calculates the overlap of n-grams (contiguous sequences of words) between the model-generated text and the reference.

**Example:**

* **Reference (R):** The cat is on the mat.
* **Candidate (C):** The cat and the dog.

**ROUGE-1 (Unigrams)**
Matches: “the”, “cat”, “the”

* **Precision:** 3/5 = 0.6
* **Recall:** 3/6 = 0.5
* **F1 Score:** 2 × (0.6 × 0.5) / (0.6 + 0.5) ≈ 0.54

**ROUGE-2 (Bigrams)**
Matches: “the cat”

* **Precision:** 1/4 = 0.25
* **Recall:** 1/5 = 0.20
* **F1 Score:** 2 × (0.25 × 0.20) / (0.25 + 0.20) ≈ 0.22

---

### 🔹 ROUGE-L (Longest Common Subsequence)

ROUGE-L identifies the longest sequence of words shared between the reference and candidate in the same order (though not necessarily consecutively).

* **LCS:** “the cat the”
* **Precision:** 3/5 = 0.6
* **Recall:** 3/6 = 0.5
* **F1 Score:** 2 × (0.6 × 0.5) / (0.6 + 0.5) ≈ 0.55

---

### 🔹 ROUGE-S (Skip-Bigram)

ROUGE-S evaluates skip-bigrams — pairs of words that appear in order but may have other words in between. This gives flexibility in capturing relevant content despite word reordering.

**Example:**

* **Reference (R):** The cat is on the mat.
* **Candidate (C):** The gray cat and the dog.
  The skip-bigram "the cat" still counts, even though there's an extra word ("gray") in the middle.

*Note:* ROUGE-S is less commonly used today and may not be supported in some modern evaluation tools.

---

### ✅ Strengths and ❌ Limitations of ROUGE

**✅ Strengths:**

* Aligns well with human evaluations
* Computationally efficient
* Works across languages

**❌ Limitations:**

* Doesn’t account for meaning (e.g., ignores synonyms and paraphrasing)
* Prioritizes exact word or phrase matches

---

### 🔄 Comparison: ROUGE vs. BLEU

| Metric | Focus     | What It Measures                                      |
| ------ | --------- | ----------------------------------------------------- |
| BLEU   | Precision | How much of the candidate is present in the reference |
| ROUGE  | Recall    | How much of the reference is present in the candidate |

These metrics are often used together to balance precision and recall perspectives.

---

**Reference:**
[Learn the ROUGE Metric by Examples – Medium](https://medium.com/nlplanet/two-minutes-nlp-learn-the-rouge-metric-by-examples-f179cc285499)

