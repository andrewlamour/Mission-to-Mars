# Mission to Mars

<p align="center">
 <img src="images/mars.png">
</p>

# Background

Build a Web Application that Scrapes Various Websites for Data Related to the Mission to Mars and Displays the Information in a Single HTML Page

# Tools Used

* [Nasa Mars News Website](https://mars.nasa.gov/news/?page=0&per_page=40&order=publish_date+desc%2Ccreated_at+desc&search=&category=19%2C165%2C184%2C204&blank_scope=Latest)
* Pandas
* HTML
* Javascript
* MongoDB
* Flask

# Process

# Step 1 - Scrapping

Scrape the NASA Mars News Site and collect the latest News Title and Paragraph Text
Visited the URL for the JPL Featured Space Image
Used Splinter to navigate the site and find the image URL for the current Featured Mars Image and assign the URL string to a variable
Visited the Mars Weather Twitter account and scraped the latest Mars Weather Tweet from the page
Visited the Mars Facts webpage and used Pandas to scrape the table containing facts about the planet including Diameter, Mass, etc.
Used Pandas to convert the data to a HTML table string.
Visited the USGS Astrogeology [site](https://astrogeology.usgs.gov/search/results?q=hemisphere+enhanced&k1=target&v1=Mars) to obtain high resolution images for each of Mar's hemispheres.
Saved both the image URL string for the full resolution hemisphere image, and the Hemisphere title containing the hemisphere name.
Used a Python dictionary to store the data using the keys img_url and title.
Appended the dictionary with the image URL string and the hemisphere title to a list.

# Step 2 - MongoDB and Flask Application

Used MongoDB with Flask templating to create a new HTML page that displays all of the information that was scraped from the URLs above.
Converted Jupyter Notebook into a Python Script called scrape_mars.py with a function called scrape that will execute all of the scraping code from above and return one Python Dictionary containing all of the scraped data.
Created a route called /scrape that will import the scrape_mars.py script and call the scrape function.
Stored the return value in Mongo as a Python Dictionary.
Created a root route / that will query the Mongo database and pass the Mars Data into an HTML template to display the data.
Created a template HTML file called index.html that will take the Mars Data Dictionary and display all of the data in the appropriate HTML elements.
