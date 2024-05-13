# Gmail Scraper for Word Analysis

### TLDR;
This small script will scrape your gmail and will creates a word analysis visualization from the contents of the queried emails.

The purpose is to gather a general outlook on interactions in the correspondence to try and decipher a general emotion/reaction of the participants towards one another. 

---

### Setup
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
git clone https://github.com/TeaZea/Gmail-Scraper_Word-Analysis.git
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
I decided to use getpass library for some basic security. You can hardcode your gmail api password but I reccomend not doing so.

![getpass code](https://github.com/TeaZea/Gmail-Scraper_Word-Analysis/blob/main/getpass.jpg)

This is the main iteration of the script. It uses the imaplib and email libraries to iterate through the query (which would have been assigned before this section) and places the contents into the _body_ variable. After converting the variable using the nltk library, I  loop through the new variable (_token_) and remove any words from the _toDropAll_ list. 

This list is custom stopwords list I created for this example, but you can edit it with whatever other words you want. This can also be replaced by STOPWORDS library from wordcloud or another prefered library. The result is appended into the _bar_ list variable before is converted to a string and passed into a CSV file to begin the visualization process.

![Main iteration of the script](https://github.com/TeaZea/Gmail-Scraper_Word-Analysis/blob/main/analysis_loop.jpg)

This loop is similar to the previous one but instead it throws the tokenized words to a list that is sorted and then printed. This is useful if you'd like to create a .py file to run from the terminal window. Since this was created using jupyter notebooks, I decided to leverage the fact that I can use visualizations to show to output.

![Loop for the tokenized wordcount](https://github.com/TeaZea/Gmail-Scraper_Word-Analysis/blob/main/tokenized_wordcount.jpg)

---

### Example output
#### This example had the lyrics of Queen's Bohemian Rhapsody sent through a number emails from 1 person.

![Output when using Jupyter Notebook](https://github.com/TeaZea/gmail_scraper_word_analysis/blob/main/outputExample.jpg)

---

### Challenges
One of the more challenging parts was the iterating through emails to tokenize the words within the contents of the email. The library made it easy, but grasping the loop within the loop was difficult at first.

This project was also the first time I was content with my utelization of list comprehension. I've always had trouble with it, but with this project, my grasp of list comprehension really grew.




