# YouTube Word Cloud Lab — Narrative and Results

This repository contains the deliverable for the YouTube word-cloud lab. Below you will find the narrative describing the search parameters, the reasoning behind the comparison, observations from the generated word clouds, possible explanations for the patterns, ideas for future improvements, and links to the result CSV files and exported images.

---

## 1) Topic and search parameters (what I searched and how)

Topic: Public conversation around "Israel" and a related topical comparison using the phrase "Gaza Peace".

Search parameters used (assumptions / choices made for this exercise):
- Search terms: `Israel` and `Gaza Peace` (two separate searches to compare word clouds).
- Region / language: I used the default (global / English-dominant results). If you run the notebook yourself you can restrict by language or region.
- Date range: Recent results (last few days/weeks) — the notebook/YouTube API parameters can be set to a narrower date range if needed.
- Items collected: video titles and descriptions (the notebook exports the collected metadata into CSV files in `assets/`).

These choices were picked to demonstrate how word clouds change when focusing on different search queries (a country name vs. a phrase focused on peace-related content).

---

## 2) Why make this comparison

The goal of this comparison is to see how different search terms shape the most common words found in YouTube metadata. Comparing a country keyword like `Israel` with a phrase like `Gaza Peace` helps highlight the difference between general news/coverage terms (which tend to include conflict, geopolitics, military words) and phrase-focused searches (which may emphasize activism, peace messaging, or community responses).

This exercise helps practice:
- Using the YouTube search API (via the provided `youtube.ipynb` notebook)
- Exporting the collected metadata to CSV
- Generating word clouds from text data
- Writing a short narrative tying the visual output to the data

---

## 3) Word clouds (images)

Below are the two word clouds generated and exported to `img/`.

### Word cloud 1 — Israel

![Israel word cloud](img/israel.png)

*Figure 1 — `img/israel.png`*

### Word cloud 2 — Gaza Peace

![Gaza Peace Board](img/Gaza%20Peace%20Board.png)

*Figure 2 — `img/Gaza Peace Board.png`*

---

## 4) Compare the word clouds — differences and similarities

Observations:
- The `Israel` word cloud (Figure 1) is dominated by the single token `Israel` (large center word), with other prominent terms such as `Iran`, `War`, `Military`, `Gaza`, and `Palestine` appearing nearby. This suggests a large proportion of results are news/analysis or conflict-related content.
- The `Gaza Peace` word cloud (Figure 2) tends to surface words related to activism, the phrase `Gaza` and `peace`, and possibly different place or organization names depending on the sample. The terms are likely to emphasize community-driven, advocacy, or humanitarian language (compared with the more general and conflict-oriented terms in the `Israel` cloud).
- Similarities: both clouds include geographic tokens (e.g., `Gaza`, `Israel`) and conflict-related tokens (`War`, `Military`) because the topics are highly related and many videos mention both places or the conflict context.

In short: `Israel` search results lean more toward general/global news/analysis vocabulary; `Gaza Peace` searches show stronger signals around advocacy/peace wording and local terms.

---

## 5) Possible reasons for the observed patterns

- Query specificity: `Israel` is a single-word, broadly used query that returns a wide range of content (news, politics, military analysis, opinion). That results in frequent appearance of geopolitical and security terms.
- Framing effects: `Gaza Peace` is a phrase that biases the search toward content explicitly about peace, which leads to more words about activism, solidarity, or humanitarian concerns.
- YouTube algorithm and labeling: Titles and descriptions written by creators will reflect their intended framing. News outlets often use certain recurring words (e.g., `war`, `attack`, `military`) that inflate their appearance in a cloud.
- Sampling: The notebook's number of videos collected, the date range, and which API page tokens were followed will influence which channels and topics appear most.

---

## 6) How this research could be improved in the future

- Increase sample size and repeat sampling over multiple days to reduce sampling noise.
- Restrict or vary by region and language to compare local vs. global coverage.
- Use more fine-grained query terms (e.g., `Israel news`, `Israel analysis`, `Gaza humanitarian`) to see how framing changes the vocabulary.
- Filter out stop words and improve tokenization (e.g., group `Israel` vs `israel` and handle punctuation consistently).
- Use stemming or lemmatization to group similar words and reduce fragmentation (e.g., `attack` vs `attacks`).
- Add quantitative metrics such as word frequency tables, tf-idf comparisons, or cosine similarity between the token frequency vectors of each search to back up visual claims with numbers.

---

## 7) Surprises and differences from expectations

- Seeing `Iran` prominently in the Israel word cloud (Figure 1) is an example of an unexpected co-occurring topic that indicates geopolitical entanglements in the data.
- The relative dominance of conflict-related terms in both clouds shows how strongly news coverage and conflict framing shape YouTube metadata even when using an ostensibly peace-oriented search phrase.

---

## 8) Files to download (CSV exports)

The CSV exports generated by the `youtube.ipynb` notebook are available via the Google Sheets links below (or add your own CSVs to the `assets/` folder if you prefer local files).

- [Google Sheet: search-result (sheet 1)](https://docs.google.com/spreadsheets/d/13PrIgVUu9EgNLRgZyHfEaIx3MR38Tfxg8lEXic0Pg90/edit?usp=sharing)
- [Google Sheet: search-result (sheet 2)](https://docs.google.com/spreadsheets/d/1dx9Tf68G9f7_RPjiL4D4M1OlfnsXllqDvLma6evYnj0/edit?gid=2093666527#gid=2093666527)

(If you ran the notebook yourself, add files named `search-result-*.csv` to `assets/` as needed.)

---

## 9) Short instructions to reproduce (run `youtube.ipynb`)

1. Open `youtube.ipynb` in Jupyter or Google Colab.
2. Set your API key or any required credentials in the first cell (if the notebook uses the YouTube API).
3. Set the search query parameter to `Israel` and run the collection cells. Export the results to `assets/search-result-1.csv`.
4. Repeat for `Gaza Peace` and export to `assets/search-result-2.csv`.
5. Run the word-cloud generation cells (they typically read the CSVs, combine text fields, and produce PNG exports in `img/`).

---

## 10) Notes and acknowledgements

- Acknowledgements: Thanks to Jou Ho, Yuke Cao, and Steven Bao for their assistance in preparing this lab.
- If you'd like, I can help you run the notebook locally or in Colab, generate additional word clouds, and commit the outputs directly into this repository.


---

If anything here doesn't match how you ran your notebook or you want the narrative to reflect a different set of queries/parameters, tell me what terms and what date ranges you used and I will update the narrative to match exactly.
