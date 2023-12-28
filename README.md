# Web_Scraping_Internshala

1. **Importing Libraries:**
   - `pandas`: Data manipulation library.
   - `numpy`: Numerical computing library.
   - `BeautifulSoup`: Used for web scraping.
   - `requests`: Used to send HTTP requests.
   - `matplotlib` and `seaborn`: Plotting libraries for data visualization.

2. **Function Definitions:**
   - `get_title`, `get_role`, `get_company`, `get_location`, `get_ctc`, `get_exp`, `get_skills`: These functions are defined to extract specific information from the HTML content of a job posting page. They use BeautifulSoup to parse the HTML and find elements based on their attributes.

3. **User-Agent and Headers:**
   - `HEADERS`: Simulates a request from a web browser to prevent being blocked during web scraping.

4. **Data Dictionary `d`:**
   - A dictionary with keys corresponding to different attributes of a job posting (`Title`, `Role`, `Company`, `Location`, `Ctc`, `Experience`, `Skills`).
   - Initially, these keys have empty lists as values.

5. **Loop for Web Scraping:**
   - A loop from page 1 to page 3 is used to scrape job postings from Internshala.
   - Inside the loop, the script fetches the HTML content of each job posting page and extracts links to individual job postings.

6. **Nested Loop for Individual Job Postings:**
   - For each job posting link, the script fetches the full content and creates a new BeautifulSoup object (`new_soup`).
   - The functions defined earlier (`get_title`, `get_role`, etc.) are then used to extract information from the job posting page and append it to the respective lists in the dictionary `d`.

7. **Creating a DataFrame:**
   - After scraping all the pages, a Pandas DataFrame (`jobs`) is created from the dictionary `d`.
   - Rows with missing values in the "Title" column are removed.

8. **Data Visualization:**
   - Three bar plots are created using Matplotlib and Seaborn:
      - **Plot 1:** Shows the top 5 most common roles.
      - **Plot 2:** Shows the top 5 companies with the highest number of job postings.
      - **Plot 3:** Shows the top 5 locations with the majority of job opportunities.

   - Each plot includes a title, x-axis label, y-axis label, and rotated x-axis ticks for better readability.

In summary, the code scrapes job postings from Internshala, extracts relevant information, stores it in a DataFrame, and then visualizes the data through bar plots.
