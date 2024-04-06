# -BizCardX-Extracting-Business-Card-Data-with-OCR
BizCardX project, aims to develop a user-friendly application to manage business card information. It leverages Optical Character Recognition (OCR) technology to extract data from business card images and allows users to store and organize the extracted information in a database.
The project utilizes Streamlit, a Python library, to create a web-based graphical user interface (GUI). This interface guides users through the process of uploading business card images, extracting relevant data (name, company, contact details etc.), and saving the information along with the image to a database.

Overall, BizCardX offers a solution to streamline business card data management by:
Extracting data from business card images using OCR
Providing a user-friendly interface for data entry and management
Enabling storage and organization of extracted data in a database
This project caters to individuals and businesses seeking an efficient way to handle business card information. 
a Streamlit app that uses OCR to extract data from business cards and saves it to a database, making information management easier.
benifits:BizCardX offers increased efficiency in managing business card information by automating data entry through OCR and providing a central storage solution in a database.

#*#the workflow of the BizCardX code:

Set Up Environment:
Install required libraries (pandas, streamlit, streamlit_option_menu, easyocr, mysql.connector, PIL, OpenCV, matplotlib).

Design User Interface (UI):

Create a Streamlit layout with:
File uploader for business cards.
Buttons for data extraction, saving, and (optional) viewing/updating.
Text boxes for displaying extracted data.
Initialize EasyOCR Reader:
Create an easyocr.Reader object for text recognition, specifying the language (e.g., 'en' for English).
Connect to MySQL Database:
Establish a connection to a MySQL database using mysql.connector.
Create Database Table (if not exists):
Define and execute an SQL statement to create the card_data table with relevant data fields (company name, card holder, etc.) and an image field to store binary image data.
Home Menu (Optional):
Display an informative message about the app's functionalities and showcase the logo.
Upload & Extract Menu:
Provide a file uploader for users to select a business card image.
Save Uploaded Image:
Define a function (save_card) to save the uploaded image in a designated directory ("uploaded_cards").
Process Image with OCR (Optional):
Define a function (image_preview) to display the uploaded image with bounding boxes around extracted text using OpenCV and Matplotlib (for visualization purposes).
Read Text from Image:
Use reader.readtext on the saved image to extract text data.
Convert Image to Binary:
Define a function (img_to_binary) to convert the uploaded image data into a binary format for database storage.
Create Empty Data Dictionary:
Initialize an empty dictionary (data) to store extracted information.
Extract Data from Text (Optional):
Define a function (get_data) to parse extracted text lines using regular expressions and populate the data dictionary with relevant fields (company name, contact details, etc.).
Create DataFrame:
Define a function (create_df) to convert the data dictionary into a pandas DataFrame for easier data manipulation.
Display Extracted Data:
Show a success message indicating data extraction.
Display the extracted data in a clear and organized manner using the DataFrame.
Upload Data to Database (Optional):
Provide a button for users to upload extracted data to the database.
Insert Data into Database:
When the upload button is clicked, iterate through the DataFrame rows.
For each row, execute an INSERT SQL query using mycursor.execute to insert data into the card_data table.
Database Commit (Optional):
If using MySQL, commit the changes to the database using mydb.commit() to ensure data persistence.
Modify Menu (Optional):
Provide options for users to select a business card from the database and update or delete its information.
Fetch data from the database based on user selection and populate text boxes for editing.
Implement functionality to update the chosen entry in the database based on user modifications.
Offer a "Delete" button with confirmation to remove a selected business card entry from the database.
View Updated Data (Optional):
Provide a button for users to view the updated data in the database.
Execute a SELECT SQL query to retrieve all data from the card_data table.
Display the retrieved data in a DataFrame using st.write.
