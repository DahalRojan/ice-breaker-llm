**System Description**
The system is designed to automate the process of gathering information about a user from LinkedIn based on their name. It leverages the Llama3 LLM model to process input, search for LinkedIn profiles, and summarize user information.

**Workflow:**

Input: The system takes a name as input from the user.

Search: It performs a Google search to locate the LinkedIn profile URL associated with the input name. This is achieved by using web crawling or search API capabilities.

Data Extraction: Once the LinkedIn profile is identified, the system extracts relevant information such as the user's professional background, skills, current position, and other publicly available details.

Summarization: Utilizing the Llama3 LLM model, the extracted data is summarized to provide a concise and coherent profile overview. This summary includes key insights and highlights of the user's professional journey and expertise.

Output: The system returns a structured summary of the user's LinkedIn profile, offering insights into their professional life in a user-friendly format.

**Technologies Used:**

Web Crawling/Search API: For retrieving LinkedIn profile links from Google. 

LinkedIn API/Scraping Tools: To fetch user data from LinkedIn. 

Llama3 LLM Model: For processing and summarizing the extracted information.


<img width="706" alt="model finding the link with google" src="https://github.com/user-attachments/assets/810b5275-8865-40f1-bfe9-98d5dc553c52">

<img width="853" alt="ice breaker result" src="https://github.com/user-attachments/assets/5a0b2ad9-e6b0-4c7b-9e93-93ecef1b0c95">
