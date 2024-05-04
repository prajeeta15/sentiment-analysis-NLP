# sentiment-analysis-NLP
** using a pre-trained NLP model
notes:
1. install Transformers
2. Perform sentiment scoring using BERT
3. Scrape reviews from Yelp and score using beautiful soup
process :
   1. installing and importing dependencies
       - !pip install PyTorch transformers beautifulsoup4 pandas numpy
       - transformers library is used to install the NLP model-multilingual BERT model that also 
         gives you a 
         sentiment score.
       - requests library will send a request to the Yelp site that will be scrapped
       - beautifulsoup4 is for web scraping Yelp and extracting data that will be used
       - pandas library is used to structure data in a format that we can use
       - numpy library is used to provide additional data transformations
       - tokenizer: allow us to pass through a string and convert that into a sequence of numbers 
         that we can pass on through the NLP model
       -re allows us to create a regex function to be able to extract the specific comments that we 
        want
   3. instantiate model
      - creating a model and importing the pre-trained nlp model into the model that we created
      - logits=tensor shows the probability of a particular class being a sentiment
      - so in the notebook, we see that every time we used "I hate this"- a negative emotion 
        it returned 0 which is pre-trained or predefined to be the ranking for 
       negative emotions and once we write "I love this" a positive emotion it returns 5 which 
       is predefined as the positive emotion score.
   4. encode and calculate sentiment
   5. collect reviews
      - this is where beautiful soup comes in. Requests sends a request to the webpage to access the webpage and then Beautiful Soup scrapes the data from the webpage link and then passes it through regex which looks for the specifics that we are looking for and stores them in a different data frame.
   6. load reviews into the data frame and score
      - why a data frame? makes it easier to go through the scraped data and process further
      - we are putting everything into a column called review and then we are going through that with apply and lambda to be able to loop through every review on the webpage and give it a sentiment score from 0 to 5.
      - 512 is written to grab everything written before the 512th value which can easily be changed to a different value to get a better sentiment analysis for the restaurant review

Conclusion:
- we get a sentiment score from 0 to 5, 0 being the worst and 5 being the best for all the reviews about a restaurant in Chicago by web scraping through the Yelp comments.
  ![image](https://github.com/prajeeta15/sentiment-analysis-NLP/assets/96904203/0ff6de92-eb71-495b-bd2f-3ffaa12a0b5e)
