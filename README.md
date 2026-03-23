# CM3070-Final-Project
Final Project

This project uses the "Trending YouTube Video Statistics" dataset from Kaggle. Download it from: https://www.kaggle.com/datasets/datasnaek/youtube-new

Place the US, GB, and CA CSV and JSON files in a folder called dataset/ in the project root.

### Why only US, GB, and CA?

The Kaggle dataset includes files for additional countries (Germany, France, India, Japan, Korea, Mexico, Russia), but the pipeline uses only the three English-speaking countries for the following reasons:

1. **VADER requires English text.** The pipeline uses VADER sentiment analysis to compute compound sentiment scores from video titles. VADER's lexicon is English-only, so non-English titles would produce meaningless scores.

2. **Encoding issues.** The non-English CSV files contain characters (Japanese, Korean, Cyrillic) that cause parsing errors with standard UTF-8 reading. The US, GB, and CA files parse cleanly without special handling.

3. **Consistent cultural context.** English-speaking countries share similar YouTube trends, meme culture, and content styles. Mixing in videos from very different cultural contexts would add noise without adding useful signal for the classifier.

4. **Category alignment.** The three English-speaking countries use the same category ID structure. Some other country files have different or missing category mappings.

