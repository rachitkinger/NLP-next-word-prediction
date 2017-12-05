# Next Word Prediction App

## Introduction  
As part of the Capstone project for Data Science Specialisation by John Hopkins University (JHU) on Coursera,
a word prediction app was built. The only function of this app is to predict the next word that a user is about
to type based on the words that have already been entered.  

For this project, JHU partnered with [SwiftKey](http://swiftkey.com) who provided a corpus of text on which the
**natural language processing** algorithm was based. 

The data used in the model came from a **corpus** called HC Corpora (www.corpora.heliohost.org)

## Algorithm Development  
A classic **N-gram** model [1] was used to build the algorithm for the app. However, pre-processing or cleaning up
of the data was done in order to remove punctuations, expletives, etc.  

Based on this a sample of the entire data was used (since only limited computing power was available) and 
Maximum Likelihood Estimation or MLE was applied on the tokens.  

The tokens used were unigrams, bigrams and trigrams. In order to improve accuracy with limited computing resourced,
Jelinek-Mercer smoothing algorithm was used. 

But when interpolation failed (mainly because we used a sample of the data) part-of-speech tagging or POST was used 
to provide default predictions.  

Profanity filter was applied on all outputs based on the Google's bad word list

## The Shiny App  
The app accepts a phrase as input, and gives the next word that the user is most likely to write next. Simple!

The prediction is based on the linear interpolation of unigrams, bigrams and trigrams. The web-based application can be found 
<a href="https://jpdms.shinyapps.io/next-word-prediction/"> here</a>. 

## Using the Application

It is a simple app with a single purpose. Despite that (and probably because of that) it can
find its uses in many situations. For educational use, for speeding up typing on phones, or checking
writing style or even grammar (if we can augment it with grammatically correct corpus!).  
The user enters some text (in English and without punctuation) in the input box. 
As the user types, the text is echoed along with a suggested next word.
