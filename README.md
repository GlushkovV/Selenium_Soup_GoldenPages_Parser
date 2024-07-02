## Web scrapping: Golden Pages

# Working out errors related to the start of the code
If an error occurs when running the code after installing the necessary libraries, then most likely the Chrome web driver for your OS is not installed. How to install the web driver can be found at this link. [selenium-python.com](https://selenium-python.com/install-chromedriver-chrome?ysclid=ly2ufnhjip111135754)
If the code does not work after installing the web driver or an error occurs, then you need to check whether the Chrome browser is open in memory. If so, you need to unload it (close it). This is due to the fact that the Chrome browser launched by the code runs in the background in the PC memory and may conflict with the Chrome browser running at the same time.
If the error still occurs, then you need to check or reinstall the libraries you are using.

# Working with the parser
To start parsing the site [goldenpages.uz](https://www.goldenpages.uz/search/) it is required to create an array of site search queries, the variable task_array = ['кафе в самарканде', '', 'кафе в намангане', 'кафе в бухаре']. GoldenPages site restriction - queries must contain at least three words, otherwise the output of the site search result will be empty.
To start parsing and save the resulting frame of the parsed data, you need to call the command parsed_data = GoldenPagesParser(task_array).task_frame_parser() which will return the Pandas Data Frame with the result of parsing to the parsed_data variable. The code will contain the following columns of collected data: id type 'int' - the number of the collected cell of each request, company_name, company_second_name, company_third_name, address, landmarks, phone_array, site_url, parsing_url - a link to the page from which the data was collected, parsing_task - the query that collected the data.
To save the resulting frame to a CSV file, you need to uncomment the line of code parsed_data.to_csv(f"Selenium_Soup_GoldenPages_{datetime.now().strftime('%d%m%Y')}.csv"), which saves the data to a file named "Selenium_Soup_GoldenPages_01072024.csv" and the folder with the code being run. The date will be inserted automatically - the current date of saving the parsing result.

# Additionally
This script is provided for educational and informational purposes only.
