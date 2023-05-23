# M12-NoSQL-Challenge

The objective of this project is to conduct an analysis of the food hygiene ratings data provided by the UK Food Standards Agency. The primary aim is to support the editors of the food magazine "Eat Safe, Love" in the selection of establishments for upcoming articles.

**Requirements**
Python v3.10.9
PyMongo
Install Pandas
Pretty Print (pprint)
Import json file "establishments.json" within the "Resources" folder

**Part 1: Database and Jupyter Notebook Setup**

1. Data Import: The establishments.json file was seamlessly imported into the MongoDB database via the Terminal. The database was elegantly named "uk_food," while the collection bore the refined title of "establishments." Allow me to share the import command that was gracefully employed:

*mongoimport --db uk_food --collection establishments --file establishments.json

2. Should the "establishments.json" file be situated in a different location, kindly ensure to gracefully replace the file path with the appropriate one.
3. To ensure the impeccable setup, the following meticulous checks were dutifully performed:

- The databases were graciously listed, thereby verifying the presence of the esteemed "uk_food" database.
- The collections within the distinguished "uk_food" database were elegantly listed, confirming the dignified presence of the "establishments" collection.
- A single document from the distinguished "establishments" collection was gracefully fetched and eloquently displayed using the find_one method, coupled with the pprint function.
- With utmost prudence, the "establishments" collection was dutifully assigned to a variable, ensuring its availability for subsequent endeavors.

**Part 2: Update the database**

1. Inclusion of "Penang Flavours" into the Establishments Database: An exquisite addition was made to the prestigious Establishments database by introducing the esteemed restaurant named "Penang Flavours."
2. Discovery of BusinessTypeID for "Restaurant/Cafe/Canteen" and Selective Return: With a keen eye for detail, the BusinessTypeID corresponding to the distinguished category "Restaurant/Cafe/Canteen" was diligently explored. Only the BusinessTypeID and BusinessType fields were elegantly extracted, delivering the desired information.
3. Impeccable Update of the New Restaurant: The newly added restaurant was subjected to a meticulous update process. Leveraging the BusinessTypeID discovered earlier, the appropriate BusinessTypeID was gracefully assigned to the "Penang Flavours" restaurant, ensuring accuracy and alignment.
4. Dover Establishments Exclusion: An attentive audit was conducted to assess the presence of Establishments within the Dover locality. Any establishments falling under the jurisdiction of Dover Local Authority were dutifully removed from the database. To confirm the successful execution of this deletion, a thorough verification was conducted, ensuring a pristine and updated database.
5. Conversion of Numeric Values: As part of a comprehensive data refinement process, certain numeric values that were inadvertently stored as strings were identified. With utmost precision, the latitude and longitude values were gracefully converted to decimal numbers using the update_many function. Additionally, the RatingValue was impeccably converted to integer numbers, ensuring the proper representation of these crucial numerical attributes.

Part 3: Exploratory Analysis

1. Establishments with Hygiene Score 20:

- The count_documents function was employed to calculate the total count of establishments that boasted a hygiene score of 20.
- To gain a visual understanding of the results, the first document from the obtained results was showcased using the pprint function.
- In order to facilitate further data analysis and manipulation, the results were seamlessly converted into a Pandas DataFrame, a versatile tabular structure. The number of rows present in the DataFrame was conveniently printed, and a glimpse into the initial 10 rows was provided, offering valuable insights into the structured representation of the data.

2. Establishments in London with RatingValue >= 4:

- count_documents was utilized to determine the count of establishments located in London that possess a RatingValue equal to or higher than 4.
- The initial document from the obtained results was presented using pprint for immediate visualization.
- To enable efficient data manipulation, the results were transformed into a Pandas DataFrame, a versatile tabular structure. The number of rows in the DataFrame was printed, and a preview of the first 10 rows was exhibited, allowing for insightful observations and analysis of the data in a structured manner.

3. Top 5 Establishments with RatingValue '5':

- The establishments possessing a RatingValue of '5' were meticulously sorted based on their lowest hygiene score and proximity to the recently added restaurant, "Penang Flavours."
- An exemplary presentation was made by showcasing the first document from the obtained results using the pprint function.
- To facilitate seamless data manipulation, the results were transformed into a Pandas DataFrame, an esteemed tabular structure. The number of rows within the DataFrame was conveniently printed, and a glimpse into the initial 10 rows was provided, offering valuable insights into the structured representation of the data.

4. Number of Establishments with Hygiene Score 0 by Local Authority:
- The number of establishments with a hygiene score of 0 was meticulously tallied for each Local Authority area.
- The results were diligently sorted in descending order, from the highest count to the lowest.
To provide a concise summary, the top ten Local Authority areas with the highest number of establishments possessing a hygiene score of 0 were printed, offering a clear insight into the areas that require immediate attention.

**References**
UK Food Standards AgencyLinks to an external site. (2022). UK food hygiene rating data API. https://ratings.food.gov.uk/open-data/en-GBLinks to an external site.. Contains public sector information licensed under the Open Government Licence v3.0Links to an external site. Accessed Sept 9, 2022 and Sept 12, 2022 with the establishment settings as follows: longitude=51.5072, latitude=-0.1276, maxdistancelimit=4567, pagesize=10000, sortoptionkey=distance, pagenumber=(1,2,3,4,5,6,7,8).
