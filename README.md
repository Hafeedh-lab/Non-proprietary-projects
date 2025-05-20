# PROJECTS
Here's all the non-proprietary projects I have worked on thus far:


1.) **Automated Parsing of Ghana’s Budget Statements**

**Context & Challenge**

Manually extracting macroeconomic variables from lengthy government documents (such as Ghana’s budget statement and quarterly bulletins) is labor-intensive and prone to human error.

**Approach**

1. **Prompt Engineering with Large Language Models:**
    - Employed ChatGPT-4 and Google’s Notebook LM (Gemini 2.0) to parse through Ghana’s fiscal documents.
    - Crafted tailored prompts to retrieve specific indicators (e.g., tax revenue, debt service, domestic/external interest).
2. **Data Conversion & Validation:**
    - Used NumPy arrays in Python to quickly convert values from billions of Ghanaian cedis to millions of USD, based on the relevant quarterly exchange rates.
    - Manually reviewed outliers and anomalies to ensure final data quality.

**Outcome**

What typically took a full day of manual effort was reduced to about an hour, thanks to a combination of automated text retrieval and bulk numeric conversions. This streamlined process enabled more time for analysis and validation, rather than tedious data extraction.


2.) Risk Scoring Model for Payment Processing Using Unsupervised Learning

**Context & Challenge**

To enhance fraud detection in payment processing, I was tasked with developing a model that could identify unusual or high-risk transactions without explicit labels for fraudulent activities. The primary challenge was to detect anomalies in transaction patterns using only unlabeled transaction data.

**Approach**

1. **Data Preprocessing & Feature Engineering:**
    - Converted transaction timestamps and monetary amounts into appropriate numeric formats using pandas.
    - Computed client-specific metrics such as average transaction amounts and standard deviations to capture typical user behavior.
    - Implemented Z-scores to quantify how much individual transactions deviated from each client's historical spending patterns.
2. **Isolation Forest (Anomaly Detection):**
    - Utilized an Isolation Forest algorithm to detect outliers based on transaction Z-scores, flagging transactions that significantly differed from typical client activity.
    - Fine-tuned the contamination parameter to balance sensitivity, identifying approximately the top 5% most anomalous transactions.
3. **Visualization & Interpretation:**
    - Generated visualizations (histograms) to illustrate transaction Z-score distributions, clearly showing the concentration of typical transactions versus outliers.
    - Provided straightforward, interpretable insights on flagged transactions to inform further manual or automated reviews.

**Outcome**

This unsupervised approach successfully highlighted anomalous transaction behaviors without labeled fraud data, enabling proactive risk management. The method offers a scalable, interpretable framework adaptable to larger datasets, significantly improving anomaly detection capabilities in payment processing scenarios.


3.) Automating a Word Bibliography — Sorting, De-duplicating & Preserving Hyperlinks

**Context & Challenge**

As my supervisor was approaching the final stages of her PhD thesis, we had just a few days to compile nearly 200 references into a meticulously formatted bibliography adhering strictly to the Chicago referencing style. With only 24 hours left, the task became even more daunting: we needed to alphabetize all references accurately while preserving their precise formatting and hyperlinks. Attempting to use citation managers or AI-driven tools proved counterproductive, as these tools consistently disrupted formatting details and hyperlinks, requiring tedious manual corrections.

**Approach**

- **Python-docx + Direct XML Manipulation:**
Leveraged Python’s `python-docx` library alongside direct manipulation of XML tags (`OxmlElement` and `qn`) to precisely handle hyperlink formatting at a document’s XML level.
- **Custom Hyperlink Function (`add_hyperlink()`):**
Created a specialized function to construct `<w:hyperlink>` elements correctly, preserving clickable hyperlinks with their original color and underline attributes intact.
- **Efficient De-duplication and Sorting:**
Developed logic to eliminate duplicate entries by storing each paragraph’s content in a case-insensitive dictionary, ensuring uniqueness before alphabetically sorting all references.
- **Comprehensive Formatting Replication:**
Implemented the `copy_run_formatting()` helper function to meticulously copy formatting attributes (bold, italic, underline, font type, size, and color) from the source references to the new document, preserving stylistic integrity.
- **Robust Error Handling:**
Included error-catching mechanisms to identify and clearly report potential issues, ensuring the script’s reliability and ease of debugging under tight deadlines.

**Outcome**

This Python utility successfully transformed a task that initially threatened hours of manual labor into a streamlined, repeatable 30-second process. Not only did it meet the tight deadline flawlessly—sorting nearly 200 references without omitting or duplicating hyperlinks—but it also retained all intricate Chicago-style formatting. This efficient approach significantly reduced stress during a crucial period of my supervisor's thesis completion, demonstrating the immense practical value and precision of the developed tool for future academic projects.


4.) Automating Payment Reconciliation for Non-Tech Savvy Mom

**Context & Challenge**

My mother runs a waste management business servicing commercial clients, with transactions logged through a payment portal. However, the platform had significant usability challenges:

- Displayed only 25 transactions at a time, crashing beyond 500 entries.
- Excessive technical jargon and unnecessary data fields (invoice numbers, payment gateways) cluttered the interface, complicating her reconciliation process.
- Navigating the website was cumbersome, especially for non-tech savvy users.

This required manual reconciliation efforts, consuming significant time and increasing the potential for human error.

**Approach**

- **Automated Web Scraping:**
    - Utilized Selenium and BeautifulSoup to systematically scrape transactions directly from the payment portal.
    - Bypassed the website’s inherent limitations by programmatically selecting transaction counts manageable by JSON responses.
- **Simplified Data Structuring:**
    - Extracted and cleaned essential transaction details only (dates, amounts, payer details), removing irrelevant technical fields to streamline reconciliation.
- **Google Sheets Integration:**
    - Automatically populated a structured, clear, and simplified Google Sheet.
    - Implemented automated sorting and date-based organization to enhance clarity and ease of use.

**Outcome**

The solution drastically simplified the reconciliation process, eliminating the need for navigating cumbersome web pages. This automation significantly reduced both my mother's stress and my own manual workload, providing a robust and user-friendly method of managing transaction records.
