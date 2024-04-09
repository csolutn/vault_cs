### 3. Methodology
* utilized datasets : the Semantic Textual Similarity, Benchmarks(stsb-en-main)
#### 3.2. System architecture
* input : model answer, students' answer
* primary modules
	* keyword scoring : YAKE! extraction, POS tagging, WordNET Replacement
	* similarity scoring : NLTK tokenizer, SimCSE, Vectorization,  Cosine Similarity
	* NER(Named Entity Recognition) scoring : transformers (AutoTokenizer, AutoModelForTokenClassisfication)
#### 3.3., 3.4., 3.5. : details for each primary modules
#### 3.6. Final scoring module
* sum  of three numpy Rounded Scores
* 4-Layerd DNN
* Final Score