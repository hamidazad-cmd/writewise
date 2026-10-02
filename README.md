WriteWise - English Writing Analyzer

WriteWise is a command-line tool that analyzes English writing and provides feedback on vocabulary, sentence structure, repetition, filler words, and readability.

It is designed to help students improve their academic writing by giving quick insights into their writing style and areas for improvement.

Features

- Count total words and sentences
- Calculate average sentence length
- Calculate a Flesch Reading Ease readability score
- Detect repeated words
- Detect filler words (e.g. "very", "really", "basically")
- Analyze academic vocabulary usage
- Generate writing feedback
- Calculate an overall writing score out of 100
- Save reports automatically and compare with your previous score
- View your report history
- Analyze pasted text, a text file, or piped input

How It Works

Vocabulary Analysis

- Compares your writing against an academic vocabulary list
- Calculates the percentage of academic words used
- Shows which academic words appeared in your writing

Sentence Analysis

- Splits text into sentences, handling abbreviations (e.g. "Dr.", "e.g.") and decimal numbers
- Calculates average sentence length
- Gives feedback on sentences that are too short or too long

Readability

- Calculates the Flesch Reading Ease score (higher is easier to read; 60-70 is plain English)
- Uses an estimated syllable count, so results are approximate

Repetition and Filler Detection

- Finds frequently repeated words, ignoring common function words
- Flags filler words that can usually be cut
- Suggests varying your vocabulary

Writing Score

The score is out of 100:

Category| Points| Based on
Vocabulary| 35| Number of academic words used
Sentence structure| 35| Average sentence length (12-25 words is ideal)
Word variety| 30| Whether any words are repeated

Filler words and readability appear in the report and feedback but do not change the score.

Installation

Clone this repository:

git clone https://github.com/hamidazad-cmd/writewise.git
cd writewise

Make sure you have Python 3 installed:

python --version

No external packages are required.

Usage

Paste your writing (finish with Ctrl+D on macOS/Linux, or Ctrl+Z then Enter on Windows):

python writewise.py

Analyze a file:

python writewise.py essay.txt

Analyze piped text:

cat essay.txt | python writewise.py

View writing history:

python writewise.py --history

This displays previously saved reports from "reports.json", including the date, writing score, and word count.

Example:

WRITING HISTORY
----------------------------------------
2026-10-02T15:30:49 | Score: 90/100 | Words: 166
2026-10-02T15:31:43 | Score: 90/100 | Words: 72
2026-10-02T15:32:43 | Score: 90/100 | Words: 70
2026-10-02T15:33:44 | Score: 90/100 | Words: 166

Options

Option| Description
"--academic PATH"| Use a different academic word list
"--reports PATH"| Use a different report history file
"--no-save"| Analyze without saving the report
"--history"| Show previous reports and exit

Example Report

WriteWise - English Writing Analyzer
----------------------------------------

REPORT
----------------------------------------
Words: 120
Sentences: 8
Average sentence length: 15.0 words
Readability (Flesch): 48.3

Repeated words:
- technology: 4 times

Academic Vocabulary:
Academic words used: 12
Academic vocabulary percentage: 10.0%
Words found:
- analyze
- significant
- ...

Writing Score: 85/100
Previous score: 80/100 (+5)

Feedback:
- ✓ Good use of academic vocabulary.
- ✓ Your sentences show good complexity.
- ⚠ You repeat 'technology' often (4 times). Consider varying your vocabulary.
- ⚠ Consider cutting filler words: very, really.

Files

writewise/
│
├── writewise.py              # Main program
├── academic_words.txt        # Academic word list (one word per line)
├── reports.json              # Saved analysis reports (created automatically)
└── README.md

If "academic_words.txt" is missing, WriteWise prints a warning and treats the academic word list as empty, which lowers the vocabulary results and score.

Future Improvements

- Add grammar error detection
- Detect sentence variety and passive voice
- Use lemmatization so "use" and "uses" count as the same word
- Add more advanced vocabulary analysis
- Create a graphical user interface (GUI)
- Export reports as PDF
- Show progress charts from report history

Limitations

WriteWise is a simple writing analyzer designed for learning and basic feedback. It uses rule-based methods rather than advanced language models, so it is not 100% accurate:

- Academic vocabulary detection depends on the provided word list.
- Repeated word detection matches exact words only, so it may miss variations (e.g. "use" vs. "uses") or flag words that are acceptable in context.
- Sentence splitting is rule-based and can be wrong in unusual cases.
- Readability uses an estimated syllable count, so scores are approximate.
- Comparing against your previous score is only meaningful if both texts are similar in length and type.
- The writing score is an estimation, not an official measurement of writing quality.
- The feedback is guidance, not a replacement for a teacher or professional evaluation.

Technologies Used

- Python 3
- Regular Expressions ("re")
- "argparse" for the command-line interface
- JSON
- Collections ("Counter")
- File handling with "pathlib"

Purpose

WriteWise was created as a personal project to practice Python programming while building a useful tool for improving English academic writing skills.

License

This project is open-source and available for learning and improvement.
