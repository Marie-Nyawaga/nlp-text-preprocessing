📘 Text Preprocessing & Exploratory Analysis for Hate Speech Detection

This project focuses on cleaning, preprocessing, and analyzing text data extracted from a hate speech dataset. The goal is to build a robust text preprocessing pipeline that prepares raw tweets/posts for downstream NLP tasks such as classification, clustering, or topic modeling.

🧹 1. Preprocessing Pipeline Overview

The preprocessing workflow includes:

Importing and initializing required NLP libraries

Removing HTML tags & special characters

Handling whitespace normalization

Stopword removal

Expanding contractions

Tokenization

Stemming & Lemmatization

Cleaning entire dataset using multiprocessing for speed

Exploratory Data Analysis (EDA) on cleaned text

Bigram analysis

Word cloud generation

🛠️ 2. Importing Necessary Libraries

Python libraries used:

pandas

re

BeautifulSoup (bs4)

nltk (stopwords, stemmers, lemmatizers)

multiprocessing

matplotlib

wordcloud

This ensures a comprehensive NLP setup.

📥 3. Loading and Extracting the Tweet Texts

The raw dataset (HateSpeechRaw.csv) contains semi-structured text.
We:

Load the dataset

Split semi-colon-separated text

Extract the relevant tweet column

Remove duplicate entries

This creates a clean working dataframe containing only the raw text.

🧼 4. Cleaning HTML Tags & Whitespace

We use BeautifulSoup to remove HTML content and regex to normalize whitespace.

Tasks handled:

Remove HTML tags

Normalize spacing

Strip leading/trailing whitespace

This ensures text is plain and uniform.

🛑 5. Stopword Removal

Using NLTK’s English stopword list to eliminate common but uninformative words like:

the, and, is, of, to, a, in, on …

🔤 6. Text Normalization (Tokenization, Lowercasing, Stemming & Lemmatization)

The pipeline includes:

✓ Contraction Expansion

Handles cases like:

can't → cannot

won't → will not

you're → you are

✓ Lowercasing

Standardizes text for consistent processing.

✓ Removing Special Characters

Keeps only alphabet characters and meaningful spaces.

✓ Tokenization

Splits text into words.

✓ Stemming (PorterStemmer)

Converts words to root form:
“running” → “run”

✓ Lemmatization (WordNet)

Ensures linguistically correct base forms:
“better” → “good”

A custom preprocess_text_fast() function applies this full pipeline.

⚡ 7. Full Dataset Preprocessing using Multiprocessing

Because the dataset is large, preprocessing is parallelized using:

Pool(cpu_count())


This dramatically speeds up execution by utilizing all CPU cores.

Preprocessed output is stored in a new column:

df['clean_text']

📊 8. Exploratory Data Analysis (EDA)
Top 10 Most Common Words

Using frequency counts to understand dominant themes.

Common words include:

kikuyu

luo

kalenjin

hatespeech

electionsboycott

http

These reveal strong ethnic, political, and hate-related patterns in discourse.

Graph Interpretation:

Ethnic groups appear frequently → suggests targeted hate speech

“http” indicates many tweets include shared links

Political language reveals election-related tensions

🧩 9. Bigram Analysis

Bigrams (two-word combinations) provide deeper context.

Top bigrams include:

"hawa wazungu" — racial references

"kikuyu kalenjin" — ethnic group tensions

"hate speech" — dataset’s core theme

"hate kikuyu" / "hate luo" — evidence of targeted hate

"electionsboycott kenyapol" — political activism

These bigrams reveal narratives around ethnic identity, political conflict, and hate speech patterns.

A horizontal bar chart visualizes bigram frequency.

☁️ 10. Word Cloud Visualization

The word cloud highlights the most frequent words in the dataset after cleaning.

Key insights:

Heavy presence of ethnic terms (kikuyu, luo, kalenjin, kamba, luhya)

Political terms (raila, uhuru, vote, elect, governing)

Hate speech indicators (“hawa wazungu”, “fight”, “tribe”, “hatespeech”)

Code-mixed language (Swahili + English + Sheng)

This shows the multilingual nature of Kenyan social media.

🧠 11. Interpretation & Insights

The dataset reflects:

Strong ethnic and political polarization

Repeated hate speech targeting specific groups

Election-related activism and conflict

Online tension amplified on social platforms

Use of mixed languages (English, Swahili, Sheng)

This preprocessing pipeline prepares the data for:

Hate speech detection

Topic modeling

Sentiment analysis

Machine translation

Social media analysis

📘 12. Conclusion

This project successfully implements a full text-preprocessing workflow and performs in-depth exploratory analysis of a real-world, sensitive dataset. The output is ready for downstream NLP modeling such as classification or machine translation.

The pipeline is efficient, scalable, and suitable for both academic and industry NLP tasks.