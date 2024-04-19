# Gmail Scraper for Word Analysis

### TLDR;
This small script will scrape your gmail and will creates a word analysis visualization from the contents of the queried emails. The purpose is to gather a general outlook on interactions in the correspondence to try and decipher a general emotion/reaction of the participants towards one another. 

---

### Setup
Update the System

```python
sudo apt-get update
```

Install virtual environment

```python
pip install virtualenv
```

Create your virtual enviornment

```python
 python<version> -m venv <virtual-environment-name>
```

Open the virtual environment

```python
source <environment name>/bin/activate
```

To get this repository, run the following command inside your git enabled terminal

```python
git clone https://github.com/TeaZea/gmail_scraper_word_analysis.git
```

Cd into the folder and install items on requirement.txt

```python
pip install -r /<path>/<to>/requirements.txt
```

Open in Jupyter Notebook

---

### Setting up your gmail API
Documentation on how to set up your gmail API can be found [here at the official documentation page](https://developers.google.com/gmail/api/guides).

---

### Overview of the code
This is the main iteration of the script. It uses the imaplib and email libraries to iterate through the query (which would have been assigned before this section) and places the contents into the _body_ variable. After converting the variable using the nltk library, we loop through the new variable (_token_) and remove any words from our _toDropAll_ list. 

This list is custom stopwords list I created for this example, but you can edit it with whatever other words you want. This can also be replaced by STOPWORDS library from wordcloud.
The result variable is appended into the _bar_ list variable before is converted to a string and passed into a CSV file to begin the visualization process.

![Main iteration of the script](https://github.com/TeaZea/Gmail-Scraper_Word-Analysis/blob/main/analysis_loop.jpg)

*_insert commentary of optional iteration_*
---

### Example output
#### This example had the lyrics of Queen's Bohemian Rhapsody sent through a number emails from 1 person.

![Output when using Jupyter Notebook](https://github.com/TeaZea/gmail_scraper_word_analysis/blob/main/outputExample.jpg)

---

### Challenges
*_insert commentary here_*




