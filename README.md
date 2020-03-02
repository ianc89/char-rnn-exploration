# char-rnn-exploration
Collecting sources for different kinds of char-rnn configurations.

# Code
The basic code builds simply with the char-rnn in https://github.com/karpathy/char-rnn which is an amazing tool to play with. To setup the tool, just follow the requirements instructions in order to use torch and lua.

# Data
The power of this kind of RNN training is strongly dependent on the training data. The blog post (http://karpathy.github.io/2015/05/21/rnn-effectiveness/) is very interesting and suggests that it learns structure and pattern when predicting subsequent characters, so if you want a structured output, it is reasonable to have a structured input.

## Horoscopes
Horoscope data was taken from : https://raw.githubusercontent.com/dsnam/markovscope/master/data/horoscopes.csv where the user has collected 3 years of horoscopes from the NY Post and attempts to use MCMC and RNN to generate new horoscopes. This data was not processed further yet, but could be done to remove the dates and starting number which the char-rnn picks up on and learns. However one benefit is that it always ends with a star sign.


## Haiku
Poem data was taken from : https://github.com/docmarionum1/haikurnn/blob/master/input/poems/haikus.csv where the user had scraped many sources of poems and haikus, and preprocessed into a csv file which had the syllable counts. Their approach was to train while giving the syllables, but I have chosed to strip this down to only contain a chunk of data with 5,7,5 (where each block is comma-separated) in the hope to find that the char-rnn will learn this pattern. 

# Network Training
I have added some of the training that I have performed so far. This may change in the future.

## Horoscopes
`Training/horoscope.t7` : -rnn_size 128 -num_layers 2 -dropout 0.2

## Haiku
`Training/haiku.t7` : -rnn_size 50 -num_layers 3 -dropout 0.2