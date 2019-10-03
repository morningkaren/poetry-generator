# poetry-generator
Creating Poetry using a Recurrent Neural Network

My passion project was to use a recurrent neural network, specifically a LSTM (Long Short Term Memory) model to create 
a poetry generator. I first scraped and gathered about 21,500 poems off the internet. Then, I cleaned my poems and 
tokenized them on the character level because I will be generating my poetry character for character. Word by word
generation would be very difficult, since there are over 100,000 words in the English language, but only about 60 
characters including punctuation and white-space. I then chunked the sequences of character up into 100 character 
sequence chunks. 7.7 million of these chunks were created. All the data was managed under an Amazon Web Services instance. 

Next, I fed my preprocessed data into an LSTM Model. I chose an LSTM model because it is able to process sequences of
data and learn long term dependencies. An LSTM model is good for this project because it will take into account not only
the previous character in a sequence, but many previous characters in a sequence. This creates a more robust prediction 
of a future character. 

My poem generator would need a seed of 100 characters or more and can be user input. It also asks for a temperature 
parameter which basically changes the probability distribution that is used to predict the next character. The higher 
the temperature, the less chance a the most common character will show up next. My generator returns a 500 character 
continuation of the seed. 

-An example-

Seed:
“An ode to Metis, Data science is hard, You make it easy, Modeling, math, statistics, What is there not to love”

Continuation:
and in the sleep the language the lights the like the more
in the streets to see and an ancer'd in the poets,
the with the sense song to the wamble the words,
as i the still the ditch of prostance and start actures
and the blessing for the father stand,
as the last black and so all still the stils,
and works of readow, the wanging had and the too to the charmore contrie,
and the strength and the pretend to me against and the grave be greater,
the world to be nothing the father to and scare,

-End example-

At the end, although my computer generated poetry doesn’t make a lot of sense, it was able to create words and pick 
up on some sort of poetic structure, like alliteration and line breaks. Other alterations of temperature shows that 
the model was able to pick up on the most common formation of characters, and generated a lot of “the” and “and” words.  

Perhaps my model was not able to generate coherent poems because I had poems from too many different authors and from
too many different time periods. This may have caused some confusion in my model. 

An alternative approach is to use a lot of similar poems to generate poetry so the model might pick up on the structure 
and possibly an over-arching theme.

