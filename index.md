## Life Expectancy Causal Analysis Project

In this project, we aim to establish causality between various socioeconomic variables and life expectancy outcomes in  roughly 166 different countries, noting the strongest connections between economic and political factors with the length of life expectancy. 

Below you will find background information on our data, our reasoning, our methods, and how to gather information for real world questions you can have. 

To find out more about us, click [here.](About.md)


### How to Use

In order to use the algorithm yourself, and add in more variables, we have organized a demo showing how we got our [main results.](Main-Results.md)

To run the project just run the following two lines of code in a Unix shell, we utilized Unbuntu 20.04 LTS but it should work for others.
```
docker pull mglevitt/world_happiness_project:run_project
docker run mglevitt/world_happiness_project:run_project
```
The pull should not take too long, but to run the code may take upwards of half an hour as a result of the many computations being made with PC. The end output should be a dictionary of the relations we found that will be printed to your terminal and all the graphs of the relations we found will pop up on your device as the code is run. Feel free to consult us if you run into any difficulties with getting our code to run properly.

#### Reformat and combine your own data with World Health Report data
1. In a local terminal, navigate to where you would like to place the repository of our code
2. Clone this repository on to your local machine in the destination of your choice and navigate into the repository of our code with: 
```
git clone https://github.com/mglevitt/Medical-Disparity-Causal-Analysis.git
cd .\Medical-Disparity-Causal-Analysis\
```
3. Install pipenv on your local machine and use it to to install the dependencies needed to run our code with: 
```
pip install pipenv
pipenv install .
```
4. Save the data you would like to reformat to src/data as a csv or xlsx file. This data must be global time series data identified by country names or country name and year. 
5. Open the code of src/scripts/download_data.py with whatever method works from you local terminal or file exploror. Edit the 2 variables after the line "# Add your own data here" towards the bottom of the script to have the correct names for your file names in the list for variable name "new_file_names", including the extension .csv or .xlsx, and the name for your output file before .csv. Once these variable are edited, delete the "#" from before the last line of code then to save the changes to this file.
6. Run the code to have your new data file added to src/final_data with your inputted file name with: 
```
pipenv run .\src\scripts\download_data.py
```

To see how to use our data or organize your own data, see our [Data Cleaning](data-cleaning.md) section.

**LAST THING THAT NEEDS DONE!!!! EXPLANATION OF HOW TO READ GRAPHS**

### Our Methods

In this project, we utilize Independence-based causal discovery, leading us to use the popular **PC algorithm**, created and named after Spirtes and Glymour, that utilizes the idea that two statistically independent variables are not causally linked.

To read our explanation on the PC Algorithm, see our [Explanation of The PC Algorithm.](PC-Algorithm-Explanation.md)

### Our Data
We combined several different datasets in order to gather enough data to properly examine our question of choice. To begin, we utilized the World Happiness Report (WHR) (https://worldhappiness.report/faq/) which details, based on surveys, various factors that contribute to  a country’s overall happiness and wellbeing.

Our second dataset comes from the Comparative Political Data Set (CPDS) which includes a collection of political and institutional data from 1960 to 2019. Because the dataset is fairly large, we will not go into detail about each variable and instead encourage you to visit https://www.cpds-data.org/images/Update2021/Codebook_CPDS_1960-2019_Update_2021.pdf to read more about the specific variables used. In summary, the dataset includes detailed information on party composition, reshuffles, duration, types of government, and additional economic, socioeconomic, and demographic variables to add to the World Happiness Report and our examination of the connections between these variables and Life Expectancy. 

Lastly, our project is built as a pipeline, ready for any additional data to be added and utilized by  the algorithm. This means that as more reliable and detailed data is made publicly available, we can easily update our algorithm and output to accommodate this new knowledge, and change the conclusions of the report accordingly. 

To see the data cleaning and pipelining process, check out [Data Cleaning!](data-cleaning.md)

If you would like to read more about our data, see [this report,](https://docs.google.com/document/d/1cvPz98_5bFYzUca4mlcvndjPvenBJzs4ya1jSkPVNS0/edit?usp=sharing) or view the data directly on [our repo.](https://github.com/mglevitt/Medical-Disparity-Causal-Analysis)

### Support or Contact

Want to see more behind the scenes or need additional help? Check out our [documentation](https://github.com/mglevitt/Medical-Disparity-Causal-Analysis) or send us an email at eramond@ucsd.edu, mglevitt@ucsd.edu, and akreitzman@ucsd.edu. 
