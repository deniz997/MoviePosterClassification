# MoviePosterClassification

## Introduction
Genre classification for movies, a type of multilabel-classification, is well used in industry. Such
companies like Netflix, Amazon etc. use this functionality to deliver their contents, to whom it may
attract. Beyond static genres, they even produce dynamic(combined) genres. Netflix also generates
dynamic posters for their contents, accordingly to consumers interests. Based on this feature, we can
say that posters are very important for attracting consumers and also they inform the consumer about
the content of the product.[1] Some posters might lead its consumer wrong, and this might cause
time waste and disappointment. Dynamic posters of Netflix are mostly based on the objects, and do
not represent the style of the genre, movie belongs. This project might lead a future work to see the
effect of style transfer on poster based movie genre classifier and by comparing this effect with a
survey, with some audience and maybe lead a future work of making this dynamic posters better.
The input to our algorithm is a database of movie poster images and their genres. We then use a
neural network to predict movie genres.

## Database and Features

The database "Movie Genre from its Poster" from Kaggle is used in this project.[2] It contains
information about movies from 1995 to 2018, such as IMDB id, IMDB link, title, IMDB score and
the link of the poster of the movie. Data is pre-processed similarly as Rahul et al.(2020)[3]’s work.
After pre-processing the database and the retrieval of the movie posters, a movie poster image dataset,
consists of 36898 268X182 resolution RGB posters, is obtained. Distribution of examples is 80/10/10
as 31704 train set, 3522 val set, 3914 test set respectively. First movies with missing genres or image
link to the posters are removed. Then posters are transferred in to the resolution of 150X150. Dataset
contains 28 different genres, resulting a high imbalance on the dataset. To overcome this problem,
we have determined genres with a threshold of 4500 examples per genre. 28 different genres are then
reduced to top 6 most popular genres. For the movies, belong to a genre that is not in our list, we
have created an extra column called ’Others’ and set it to 1.

At the end we have the pre-processed data that the algorithm requires. Yet, the data is not equally
distributed, and this limits the expected accuracy.

## More Info

For more information you can read the article about the work that can be found in project folder. The link below contains the weights files and the posters used as the data source for this project.

In the folder *movie_genre.csv* file contains the movie id with corresponding genre labels. In *posters.zip* file, you can find the posters with their ids.
Weights were saved in a *.h5* files and the naming convention defined as follows:

model_{algorithm used}-e{number of epochs}-{type of network}-unfreez{number of trainable layers from the last layer(e.g. last 40 layers)}-{starting weights}.h5

Google Drive Link to posters.zip and weights files: https://drive.google.com/drive/folders/1HgF5dfQkcMREjMKoSYm-gLzn7OVfA2DV?usp=sharing
