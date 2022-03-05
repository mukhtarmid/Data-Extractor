# Procedure To Scrape Data from Website
There might be enumerous ways to scrape data from websites, but upto my knowledge, I know these following procedures to scrape data from various websites. Hope this might helpful to my fellow Githubers.

To scrape data from a certain desired website, first you have to findout the type of the site, whether it is dynamic or static. To scrape table from the desired website, there are slightly different method.

Let's begin with Dynamic Scraping,

## Dynamic Websites:
First let me explain you what are the dynamic websites, to summarize in one sentence, *A dynamic website or dynamic web page contains information that changes, depending on the viewer, the time of the day, the time zone, the viewer's native language, and other factors.*

Now, to scrape data from these websites you have to be updated with the websites, from time to time. To fulfill this condition we have a package in python called `Selenium`. Let's follow the procedure to scrape data:

**Step 1:** We import the libraries such as, `BeautifulSoup from bs4`, `webdriver from selenium`, `time`, & as usual `pandas` for playing with datas.

**Step 2:** Now we need a remote web browser, so we can have command over him, and we can control with codes. For this we have `webdriver.Chrome()`, this code will open a remote blank Chrome Browser.

**Step 3:** Inside an varibale store the dynamic website url in the form of string.

**Step 4:**`browser.get(variable)` will open the website in a Remote Chrome Browser.

**Step 5:** Under the `html` variable, or variable name of your wish place `browser.page_source`. This will get the html code of the website, but it won't be in a workable form. For this we need to get it in soup form. 

**Step 6:** Define an object called `soup = BeautifulSoup(html or varbale name, 'html.parser'/'file.parser')`. This will convert the html code into soup class type, and from this we can get our desired info.

**Step 7:** Now get back to the Remote Chrome Browser or website and right-click anywhere and goto inspect, under that prefer hover-mouse icon on the upper-left side of the html code window, and hover your mouse to the desired data you want to extract. Get the tag name, as well as class name and perform action with the help of `soup.find_all('tag_name', class_ ='class_name')` OR go with `soup.select('tagname.class1name.class2name. . . ')`.

***NOTE:*** We need `time.sleep(number of seconds)` to freeze the code for that much number of seconds, as while requests and response from internet might not be so fast, we might loose some of the data. For *n* number of pages to extract from websites, we just define a function to perform certain desired tasks. The only key point to remember is, where page number is variable, replace it with `{}`, and then you can access that page by `page.format(page_number)`. 

Now, let's move to Static Website,

## Static Websites:
Lets first understand, what are the static websites. *A static website or static web page contains information that doesn't change automatically. It remains the same, or static, for every viewer of the site.*

As compared to dynamic websites, you need not to be updated so much with the websites from time to time as the defination has made it clear. Now, to scrape data from the static websites we need some packages to first reach to websites from python, and then perfom the action. For that we need `requests` and `BeautifulSoup from bs4`.

**Step 1:** We import the libraries such as, `BeautifulSoup from bs4`, `requests`, `time`, & as usual `pandas` for playing with datas.

**Step 2:** Inside an varibale store the website url in the form of string.

**Step 3:** `requests.get(url).text` will give you the html code, but in the text form. Store it in `html` variable.

**Step 4:** Define an object called `soup = BeautifulSoup(html or varbale name, 'html.parser'/'file.parser')`. This will convert the html code into soup class type, and from this we can get our desired info.

**Step 5:** Now get back to the website and right-click anywhere and goto inspect, under that prefer hover-mouse icon on the upper-left side of the html code window, and hover your mouse to the desired data you want to extract. Get the tag name, as well as class name and perform action with the help of `soup.find_all('tag_name', class_ ='class_name')`

***NOTE:*** We need `time.sleep(number of seconds)` to freeze the code for that much number of seconds, as while requests and response from internet might not be so fast, we might loose some of the data. For *n* number of pages to extract from websites, we just define a function to perform certain desired tasks. The only key point to remember is, where page number is variable, replace it with `{}`, and then you can access that page by `page.format(page_number)`.

Now, Let's suppose you wanna scrape a table from some website.

## Table Scraping:
The preocedure remains same as of the above, the only differences arrive while scraping the data. Rather than giving you outer shape of the code, I'll take you to the tour of inside the code.

**Follow the steps of static or dynamic scraping till Step 4. And further follow these.**

**Step 5:** `soup.find_all('table')` and select the table by [index of table], such as if you wanna select 1st table then, `soup.find_all('table')[0]`.

**Step 6:** Under the `th` tag you'll get the header column names of the columns.

**Step 7:** `soup.find_all('tbody')[0]` will give you the body of the first table, for another just play with [index of table].

**Step 8:** Now, we have to access the rows and then data of the row, for that we have tags `tr` & `td`.

***NOTE: I have shared my jupyter notebook, for your convenience, for each section you'll find a jupyter notebook, and further more will be uploaded.***
