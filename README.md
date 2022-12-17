# Euro_2021
This is a web scrapping project and it also touches some aspects of data manipulation, data wrangling, and data visualization. This project illustrates the web scrapping of UEFA Euro 2020 competitions. There are a total of **4 notebooks** in this repository.

1. Project_Euro_2020
2. Euro_2020_OOP
3. Individual_Achievements_ Euro_2020
4. Test_Project_Euro

## Project_Euro

This notebbok deals with simply getting data from the website and putting it in a form of a list. The following urls are used for web scrapping. These sites can be easily accessed and one can extract the data based on the dates on which the matches took place.

https://www.bbc.com/sport/football/european-championship/scores-fixtures/2021-06-11

https://www.bbc.com/sport/football/european-championship/scores-fixtures/2021-06-12

https://www.bbc.com/sport/football/european-championship/scores-fixtures/2021-06-13

..................................................................................................................................................................


https://www.bbc.com/sport/football/european-championship/scores-fixtures/2021-07-11

A clear pattern can be seen in these urls. The base url is same for all the matches however, the dates are changing at the end. So the dates have to be appended dynamically to the base url, which stays the same for all the urls. The tournament started on `2021-06-11` and it ended on `2021-07-11` 

There are three functions in this notebook. The first one takes the starting and the ending dates of the tounament and gives a list of the urls. The function `all_results` plays the main role in this notebook. It takes the list of the urls and requests for the html text from these pages one by one. Finally, it returns the list of results of all the matches of the tounament. The function `show_match_reuslt` specifies the structure of the results. The results are basically divided in two types. The program in the `all_results` checks whether a match was held after **26.06.21** and if it did, the program also checks if a match went to penalties or not.

## Euro_2020_OOP

This notebook depicts an alternate and a slightly more efficient way of handling the scraped data. It uses object oriented programming. The requesting and scrapping methods are the same however the handling of data is different. In this notebook, dataclass from the library `dataclasses` is used. Dataclass is used when a class contains a lot of numeric data. In such a class, the focus is more towards attributes and these classes are not used for behavioral purposes. 

There are a total of two classes in this notebook;

1. Results
2. TeamStats

In `Results` class, the name of teams along with the number of goals scored by each team is recorded. Also, if a match goes to penalties, the name of the winner is saved in the variable **pen_winner** and the score is handled by **pen_score**.

The class `TeamStats` transforms the data encapsulated in the Results class into a form that will be used for making the points table as seen in the real football analysis. This class stores the data like number of games played, won, lost, and drawn by each team in the form of attributes. Then a function `parse_team_stats` takes the results class, loops through it and increment the attributes of the `TeamStats` accordingly.

Using **pandas** library this data is then converted in a tabular form, furthermore some interesting insights can be drawn from this data with the help of graphs, drawn using **matplotlib** library.

## Individual_Achievements_ Euro_2020

Individual accolades are an important aspect of any sporting event. This project also covers this aspect. The top scorers and top assist providers can be found using the resources (**/top-scorers**) and (**/top-scorers/assists**) respectively after the base url (https://www.bbc.com/sport/football/european-championship). The scrapping in this case was a little different as scrapping a table is a little difficult as compared to scrapping simple text on a webpage. So, for this purpose this program has some nested loops that first goes in the table heads and grabs all the cell in the header. Same applies for the table body's cell however, in this case the nest is even more complicated. Finally, the data is converted intto a pandas dataframe and afterwards some meaningful visualizations were generated using matplotlib.

## Project_Euro

Testing is an important part of any progam. This project has also a few test cases. First of all, `ipytest` needs to be installed for enabling jupter notebook to run tests on it. Also, `import-ipynb` needs to be installed to import notebooks into the test notebook. The test cases are rather simple and self-explanatory. These test cases ensure that the data is being scraped from the webistes correctly, and stored in the lists and classes properly.


# How to Install

You can fork this repository and download it. This repository has a `requirements.txt` file that has the information of all the rquired libraries to run this program.

# How to Run

Follow this read me file and run all the notebooks in the same order. Don't forget to install `import-ipynb` and `ipytest` otherwise the test notebook will crash.


#   HAPPY PYTHON LEARNING!
