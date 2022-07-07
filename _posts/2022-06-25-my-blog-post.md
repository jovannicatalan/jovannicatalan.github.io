# ST558 Project 1 Vignette

## This post is for the ST558 Project 1 Vignette.

As part of this project I decided to research some Pokemon related APIs and ended up using APIs
from [PokeAPI](https://pokeapi.co/docs/v2#pokemon)

As part of this Vignette I created some functions to make use of APIs to obtain some data on Pokemon based on some values.
The values used to retrieve information on pokemon were: __Pokemon Name, Pokemon Shape, Pokemon Type, Region, Move name and Move Type__.

It was rather simple to get the data using the appropriate API endpoint(url), after that it became quite a bit messy. The structure of the
data was all over the places and it was a difficult task to parse it and get it into a format that I could regonize and be able to match with the
data we used in class to be able to apply the same techniques. In the end this took up the bulk of my time, trying to get the data into a format
I could work with. It was just a list within list and each list was only relevant to the value you passed and not really relevant to the other 
lists retrieved along side it. They were also of different lengths, making it hard to fit into a dataframe. I first had to create dataframes
with duplicates and then remove them later on.

I think I would of probably chosen an API with more structured data for my first project so I would have more time and more of a chance
to apply the many techniques we learned in class and in a simpler way. Trying to parse the data made my code convoluted and hard to read
at times.

__Repo Links__:
[Regular Repo](https://github.com/jovannicatalan/jovannicatalan.github.io)
[github pages Repo](https://jovannicatalan.github.io/)

