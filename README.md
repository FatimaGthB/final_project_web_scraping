# final_project_web_scraping

PROJECT: Web Scraper for News Headlines
Objective:
Construct a tool that extracts news headlines from a website, giving hands-on experience with web scraping, data storage, and basic searching/filtering techniques.

#### 1. Web Scraping:

In this section, I've worked on retrieving news headlines from the web using web scraping, by creating a function def get_news_headlines(url). The function returns the retrieved headlines in the form of a dictionary list.

To do this, I used the BeautifulSoup library to interact with HTML and inspected the web page to see under which tag the data we wanted to retrieve was nested: soup.findAll(["h3"]).

"h3" being the tag under which the titles are nested.

I also used the Requests library for the given URL to retrieve the HTML data returned by the server and store this data in a Python object and check the response to the request: if response.status_code == 200 then the request was successful.


#### 2. Data Storage and Retrieval:

   2. a. Store scraped headlines in a CSV file.
      
In this section, I've worked on storing retrieved headlines and retrieving them by keyword. To begin with, I created a function store_headlines_to_csv to store retrieved headlines in a CSV file for later retrieval.

I used the Python with open command to open my file securely:
with open(csv_file_name, 'w', newline='') as csvfile
 then the csv_writer.writerow([title.text.strip()]) method to write each title to our csv file

    2. b. Search headlines based on a keyword.
    
In this section, I've worked on searching for headlines based on a supplied keyword: def search_headlines(keyword, csv_file_name)

To do this, I defined a list that will contain the results of titles found with the given keyword: results = [ ]
I then opened our csv file in reading mode and, using a for loop that traverses each title and an if condition, I checked whether the given keyword was found in it, ignoring case: if keyword.lower() in title.lower():
                results.append(title)

each title found is then added to our results list.

#### 3. implementation of a graphical interface:

In this last part, I've improved user interaction by implementing a simple graphical interface.
To do this, I imported the tkinter library.
first, I created a def exit() function that exits the application with an exit button.

then the def search() function to search for titles found on the basis of a keyword before inserting them in a dedicated boxed list result_listbox.pack().

window = tk.Tk() enabled us to create our window, then we opened our csv file again in reading mode to insert all titles in another list box: title_listbox.pack()

then the exit and search buttons were created using the tk.Button command and the functions created above.

Finally, we execute our window with the command: window.mainloop()
