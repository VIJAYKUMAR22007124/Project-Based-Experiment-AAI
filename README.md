<H3>B VIJAY KUMAR</H3>
<H3>212222230173</H3>
<H3>DATE:14-05-2024</H3>
<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:<H3>
 Perform sentiment analysis using your Facebook data and count the number of Occurrences of my name in the extracted text.
<H3>Program:</H3>

```
import json
from nltk.sentiment import SentimentIntensityAnalyzer

# Load Facebook data
with open('facebook_data.json') as f:
    data = json.load(f)

# Initialize sentiment analyzer
sia = SentimentIntensityAnalyzer()

# Count occurrences of term
term_count = 0

# Perform sentiment analysis
positive_count = 0
negative_count = 0
neutral_count = 0

for post in data['posts']:
    # Count occurrences of term
    term_count += post['message'].count('Syed Abdul Wasih')
    
    # Perform sentiment analysis
    sentiment_score = sia.polarity_scores(post['message'])
    if sentiment_score['compound'] > 0.05:
        positive_count += 1
    elif sentiment_score['compound'] < -0.05:
        negative_count += 1
    else:
        neutral_count += 1

print("Occurrences of 'VIJAY ':", term_count)
print("Positive posts:", positive_count)
print("Negative posts:", negative_count)
print("Neutral posts:", neutral_count)
```

<H3>Output:</H3>

![image](https://github.com/Lavanyajoyce/Project-Based-Experiment-AAI/assets/119657657/bf23aaca-a7bb-4297-b9d0-5a2abe4c35d8)

<H3>Inference:</H3>
Write about your learning experience out of this project. (What you have learned)
