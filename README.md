# Portfolio Project:

# Descriptive Analysis of Vancouver’s 311 Service Requests

## Project Description:
Descriptive Analysis Portfolio Project

## Project Title: 
Descriptive Analysis of Vancouver’s 311 Service Requests

## Objective:
The main objective of this project will be to provide a descriptive analysis of the service requests managed by the 311 contact center of Vancouver in the years 2023 and 2024. Through this analysis, it will be possible to understand specific patterns and potential trends in public service requests and responses, as well as possibilities for increasing the efficiency of service delivery. Such descriptions will also allow for an analysis of the activities of the city's departments and suggestions for improvements to the services rendered. 

## Dataset:

![Data Discovery1](https://github.com/user-attachments/assets/9d81f60b-13ba-4f83-b1aa-d46ea2013881)


The dataset includes service requests submitted to Vancouver’s 311 contact center, with the following key columns: 
  Department: It refers to the city department that needs to attend or handle the service request. 

  Service request type: The type/or category of the request made, for instance, garbage collection repair of a street. 

  Status: What is the current status of the request? For example, it can still be open, considered closed, or forwarded to another department. 

  Closure reason: The nature of closure of the respective request (for instance, closed due to completion, closure due to rejection, or closure due to existing duality). 

  Service request open timestamp: The date and time when creating a particular service request. 

  Service request close date: The date on which the request was closed. 

  Last modified timestamp: The broken-down update of the last time the request was made. 

  Address: The geographical place from which the service request has been initiated. 

  Local area: The geographical area of Vancouver from which the request was made. 

  Channel: This includes how the request was made, whether online or verbally, such as through a phone call. 

  Latitude/Longitude: Geographical coordinates of the service request. 

  Geom: Geometry column corresponding to the given dataset's spatial attributes. 

## Methodology
### Data Collection and Preparation:
At the first step of the defined methodology, the 2023 and 2024 service request data is first imported into the Python environment using the Pandas library. After observing the first few rows to ascertain valid loading, the data cleaning involves handling missing values and duplicates. Missing values are identified using ‘.isnull().sum(),’ and rows with missing data are dropped. Duplicate records are checked using ‘.duplicated()’ and removed with ‘.drop_duplicates().’ Once the datasets are cleaned, a summary of the cleaned data is created to ensure it is ready for analysis. The cleaned datasets are then imported and saved as new Excel files to be used in the subsequent steps of the project. This step helps to clean the data and create a format that enhances efficient and effective descriptive analysis in the following steps.

### Data Storage Design
Data storage design is crucial when migrating data from an operational environment to an analytical one. AWS S3 is the service used for this implementation, providing an organized structure for data storage through the use of folders, facilitating easier access. The S3 bucket in use is named 311cntctcntr_srvrqst_rilwan, divided into subfolders for 2023 and 2024, each containing landing folders where datasets are initially stored. The data is set to "standard" access frequency, indicating that it will be frequently accessed and updated at various intervals.

![Data Storage 1](https://github.com/user-attachments/assets/2f6ca432-8ad1-48d5-881e-28dd42c54e60)

![Data Storage 2](https://github.com/user-attachments/assets/35e0647d-f325-46d7-9159-7f7b73793807)

![Data Storage 3](https://github.com/user-attachments/assets/a4a8899f-897b-455c-882d-159ad5312d5c)

![Data Storage 4](https://github.com/user-attachments/assets/217f54da-fc0c-45dc-a188-a7d42b314a88)

### Data Preparation
In this step, after organizing folders in the S3 bucket, data is ingested in Excel format, ensuring consistency and validity, while maintaining proper alignment with analysis goals. The Excel files represent 311 server requests for 2023 and 2024, stored in the designated landing folders in the S3 bucket.

![Data Preparation](https://github.com/user-attachments/assets/a255392a-294e-4a4c-806e-8976e428c2f3)

### Data Ingestion
This stage involved transferring our Excel data from our source into our S3 storage analytical environment, where it will be accessed with a frequency of S3 Standard. After we validated our data set from the source and considered all regulations and data privacy instructions, we ingested data into the S3 Folder, where we have lading. We stored each data in its specific year files.

![Data Ingestion 1](https://github.com/user-attachments/assets/6645550b-7117-4c16-9286-811da1399dab)

[Data Ingestion 2](https://github.com/user-attachments/assets/2d1e49aa-72ec-4e2c-968e-0e3b8435b0ed)

### Data Pipeline Implementation
An important aspect of implementing an AWS data analytic platform for the city of Vancouver is the data pipeline design. This step entails creating a data lineage diagram that exemplifies how our data metamorphoses at different stages before our final analysis. this step shows how each data set goes through different filtering and is reorganized systematically, aligning with the project set goals and objectives. the diagram represents a flow of data. The data pipeline begins with the data in Excel format in our landing zone, followed next by different processing, which involves grouping, extraction, and removing columns or rows to eliminate inconsistencies and irrelevant information .at the final stage of the pipeline, lineage diagrams data is set with relevant categories represented by percentage values.

![Data Pipeline](https://github.com/user-attachments/assets/b1b0a848-9446-44ad-90c0-0c4bf6c01e3d)

![Data Pipeline 2](https://github.com/user-attachments/assets/aec3d455-1325-4614-90a8-f5dced6733cf)

![DAat Pipeline 3](https://github.com/user-attachments/assets/13c9deed-d3cc-48fb-b2aa-b13956b4a635)

![Data Pipeline 4](https://github.com/user-attachments/assets/3ba6b16e-48b9-45d8-85c5-7479f8658356)

### Data Cleaning
This procedure is performed using a service called AWS Data Brew, which entails creating projects and transforming data. The service enhances data cleaning and filtering required for analysis. Each data we have stored in the landing folder in our S3 in the 2023 and 2024 buckets is created as a project and cleaned to remove null, invalid, inconsistent, and missing values. In my case, I filtered out invalid years, extracted years, a status created new column needed for my analysis cleaned data is then saved in CSV format and saved the RAW folder in our S3 bucket. The data-cleaning process is shown below. 

![Cleaning 1](https://github.com/user-attachments/assets/d5627e61-8603-445c-9750-a7252db07b4d)

![Cleaning 2](https://github.com/user-attachments/assets/d85141c8-63ca-41cb-9b7a-de1b88518207)

![Cleaning 3](https://github.com/user-attachments/assets/e0b00f6f-4b3c-4223-a8b7-a6308e1799e2)

Figure 1:
The Outcome from The Cleaned Datasets

![Figure 1](https://github.com/user-attachments/assets/cff4bcb3-f940-4df0-9f18-a00b9ed7c85e)

The result of data cleaning for the 2023 and 2024 service request datasets indicates that the two datasets have been appropriately loaded, cleaned, and saved. Regarding 2023, there were missing values in many columns, including 217 in the Closure reason, 228 in the Service request close date, and 1,096 in the Address, Latitude, Longitude, and geom group. The same observation was made in the 2024 dataset, as there were more missing values in similar columns, including 296 in Closure reason, 302 in Service request close date, and 840 in location-related attributes. As illustrated in Figure 1, the overall structure of the cleaned 2023 data has 5,658 record entries and 3,549 record entries of the cleaned 2024 data. However, neither of them contains any duplicate records. The data of both datasets has passed the cleaning process, and the necessary columns such as department, request type, status, closure reason, timestamps, addresses, and geospatial representation have been retained and preserved for further analysis. The cleaned datasets were saved for future use in Excel format.

### Data Structuring

This step involved creating a project in the AWS data brew for individual data sets. This process follows the data cleaning process we have previously Implemented. we organized the data in a logical manner and then exported it as CSV files into our curated folder in 2024. At this stage, the data set has maintained high quality and is ready to implement structured query languages.

![Structuring 1](https://github.com/user-attachments/assets/a2e2e6b6-838a-4368-8c53-e73e87af20a3)

![Structuring 2](https://github.com/user-attachments/assets/0835852b-0a68-4b73-8aab-7852543eeb0f)

### Data Implementation ETL

The focus of the data pipeline implementation is to set up the ETL (Extract, transform, load) process. It does this by using AWS Glue’s Visual Code ETL tools. To achieve this process, it creates a data pipeline that then procedures to extract raw data from the S3 landing folders. It then creates suitable data by following a clean and well-structured step. The processed suitable data stores include examples like an Amazon Redshift data warehouse or another S3 bucket.

![Data Implementation ETL](https://github.com/user-attachments/assets/950caf87-5bc0-47ac-99c5-5be5bbb9cc6c)

### Data Analysis
In this data analysis phase, the AWS Athena was used to interpret the clean and well-structured data. The serverless and interactive query service is used to analyze data stored in S3. Using Structured Query Language (SQL), helped with investigating the license data set, uncovering patterns, trends, and gaps, and gaining a deeper understanding of the data. Through this process, meaningful information was extracted, and it helped with identifying correlations and developing a more comprehensive knowledge of the data set.

![Analysis 1](https://github.com/user-attachments/assets/334a9374-c3f6-428d-9a35-a797d21eef6e)

![Analysis 2](https://github.com/user-attachments/assets/5a69367e-1893-4de1-a1c0-15ba8ba17ece)

### Data Publishing
The final step includes releasing the analyzed data and visualization into a web server hosted on an AWS EC2. This will ensure that the release of analyzed data is safe and secured. It also provides a strong foundation for the assess and usage of the data.

![Publishing 1'](https://github.com/user-attachments/assets/296a5df1-f55e-4fab-a33d-48725162be2f)

### Cost Estimation

![Cost 1](https://github.com/user-attachments/assets/e8e0ddef-9f2f-41ee-b0b9-1bd2c6b4ef83)

![Cost 2](https://github.com/user-attachments/assets/25ded3da-62a3-4fe9-97b6-e08e677cdfc8)

### Data Protection

![Replication For Protection](https://github.com/user-attachments/assets/d2aaa551-26a0-4510-946f-9048f914edbd)
 
![Data Encryption For Protection](https://github.com/user-attachments/assets/5ac67fd8-547c-4ffd-973e-48d8b4c92a22)

### Data Governance
Data governance ensures that data in AWS analytical environment adheres to guidelines such as integrity, compliance ,data privacy and policies regulating data usage in the city of Vancouver and Canada at large. The first step in the data governing ETL is to load data set (CSV) from RAW zone in the departments S3 bucket (311cnctccntr-servrqst-rilwan) in Glue. In the initial stage, it is crucial to implement data sensitivity rule to eliminate any possibilities of data breaching and data privacy problems. The next step in this ETL is to evaluate data quality. T

his step ensures data meets predefined criteria such as checks for null, missing values and incorrect values which might hinder accuracy of data results. To achieve a well-defined data quality evaluation, we identified our metric (percentage of complete values) and threshold (>0.95) i.e., we accept data quality that is 95% and above and reject any percentage lower that 0.95. After running the job, AWS then help us group our outcomes into two categories (Fail, Pass) based on the rules we implemented. At this point we have implemented privacy rule, completeness rule, data quality rule and store the passed group into out trusted zone in S3 bucket for both 2023 and 2024.

![ETL Job Governnace](https://github.com/user-attachments/assets/c5a7d4d5-fbda-4be9-96a6-b50dad5a61cd)

![ETL Governance](https://github.com/user-attachments/assets/6a2ba63f-246d-42f4-b86c-13feaf266283)

![Governance 2](https://github.com/user-attachments/assets/74a6be34-a545-4268-b550-da28bf9d734e)

![Trusted Zone](https://github.com/user-attachments/assets/17d04c1f-f785-4223-90eb-eb2c38fdbcd9)

![Trusted Zone 1](https://github.com/user-attachments/assets/62fe5c85-e2b2-4593-bbdc-e61ee54cb824)

![Monitoring Governnace](https://github.com/user-attachments/assets/d1c75792-7898-4f1c-a0db-50971ac0fbd7)

### Data Monitoring 
This AWS features provides information about performance and success rate of our jobs. These observation enables us to get insights how job performed at different point in time and increase or reduce computing power. this is helpful in saving cost, latency and increasing other resources based on data requirements. The monitoring feature is then integrated with AWS cloud watch. 311 contacts have a robust staff strength and prone to risk due to the amount of sensitive data handles and stored on daily basis. AWS cloud watch will help the department stores day-to-day logs of activities that takes place in the data based. This feature is particularly important to identify user identity and track activities step by step in glue , s3buckets and Ec2 instances .According to 311 contact center requirements we identify  three metrics which  billing because we want to manage cost (total  estimated charge)  of our S3 and (number of objects) in our S3 bucket because the department handles continuous data which is stored simultaneously and finally (Bucket size or capacity) to know if we need more storage size .To identify resource usages for this metrics  in AWS glue we then create a dashboard customed to monthly window enhancing visualization of t cost we have incurred in a particular period  of time. To analyze and control activities we then create alarm which is an important business requirement. We then set alarm to notify the department when total estimated charge is over 35usd. this is vital to set a threshold for usage and resources and cost management. 


![Workflow 1](https://github.com/user-attachments/assets/148890bf-e90e-49f7-9b06-805fc93ff564)

![Workflow 2](https://github.com/user-attachments/assets/74bd5f57-651e-437f-9c97-ae0070347155)

![Dashboard](https://github.com/user-attachments/assets/83863b9e-2afb-4fd0-a7c4-c6ff71244821)

![Alarms](https://github.com/user-attachments/assets/417c0c78-90a9-44e3-a446-c0f86dfcbbc8)


![Cloud trail](https://github.com/user-attachments/assets/abe4364f-4f6f-4b20-b7c1-6bf5839bf650)



### Descriptive Statistics and Basic Data Exploration. 

In Step 2, cleaned datasets of 2023 and 2024, the databases for this analysis, are loaded, and after a quick examination, the following patterns and trends are identified in the service request data. The first aspect of this step is to determine the total number of services received in a specific year to form the basis of understanding the second part of this step, which is identifying the various types of service requests and determining which type of service requests are likely to be received most often. The status distribution also demonstrates the relative share of open, closed, and requests with other statuses. Subsequently, the mean time to address service requests is calculated as the time difference between the request open and closed timestamps to ascertain the time to tend to specific requests. Furthermore, the distribution of the service request submission choice, like telephone or electronic submission, is also analyzed to discover the frequency with which the public employs different modes of service request submission. Ultimately, the distribution of requests is presented based on the geographic location with the most requests. It considers the 2023 and 2024 years individually and jointly to provide deeper insight into Vancouver’s 311 system service requests.

Figure 2:
The Descriptive Statistics

![Figure 2](https://github.com/user-attachments/assets/e9a61d7d-5fef-411c-bc52-38a1d8926563)

Figure 2 illustrates the descriptive analysis of the 311 service requests situation in Vancouver for 2023 and 2024. Although in 2023, the total number of service requests was 5,658, that number was reduced by mid-2024 to 3,549. Again, as highlighted in the above figure, the most frequent type of request encountered in both datasets was the “City Services Feedback Case;” which constituted all service requests made in the two years under review. The status distribution indicates that both years' recorded requests were “Closed. ” When calculating the average request time for both years, it took approximately 11.22 days to resolve a request in 2023. In contrast, in 2024, the average resolution time increased to 13.58 days, suggesting a slight delay in handling requests.

The most utilized means of submitting the requests was the telephone in the two years, with 5,437 telephone requests submitted in 2023 and 3,463 in 2024. Chat, social media, and email were used much less frequently than call centers as a mode of communication. Concerning the distribution of service requests by region, the number of requests for both years was the highest in the Downtown region, followed by Kitsilano, Mount Pleasant, and Kensington-Cedar Cottage. The analysis of the first five closure reasons for service requests shows that most of the service requests, namely 4,532, were classified as “Service provided,” meaning that the service requested was delivered. 

The second most frequent reason (1,571) is “Closed automatically and sent to a service group,” which means such requests were automatically forwarded for further processing. Another 1,118 were closed with the reason ‘referred to another service group,’ indicating that many requests were passed on to other departments. ’Reviewed and no action planned’ (939) means that some of the requests did not need further action; ‘Further action has been planned’ (466) means that some of the requests will need further action in the future. These reasons give information on the different processes through which service requests are handled and closed.

### Data Visualizations
Time Series On The Number of Service Requests

![Time Series](https://github.com/user-attachments/assets/bbb18b4d-3b80-48c1-9ae6-a3fdc18c37f1)


The Type of Service Request

![Service Request Type](https://github.com/user-attachments/assets/3c59c64c-5704-478b-a1b9-db544151b92c)


The Distribution of Submission Channels Used.

![Submission Channels Distribution](https://github.com/user-attachments/assets/bdff4da9-6d46-40c0-ab1a-db6d9bb8a329)

The Request Durations In Days.

![Service Request Duration](https://github.com/user-attachments/assets/91a54303-2993-4ab7-b52c-f59842ed8760)

Local Area Distribution Comparison:

![Top 5 Local Areas](https://github.com/user-attachments/assets/f633dc1a-99cd-4ae8-b72f-9ac2dd9b9729)

The visualizations show how Vancouver 311 service requests differ in Year 2023 and Year 2024. The first chart is the Time Series chart that indicates the total of service requests using different trend lines for each year and having different trends, where 2023 has more requests in the initial months of the year, and 2024 has upward tendency from the late months of the year 2023 and increasing till the early months of 2024. The fourth chart shows the most frequent service requests: the “City Services Feedback Case” is on the top of the 2023 and 2024 lists.  

The two pie charts illustrate the submission channels of service requests for 2023 and 2024. In both years, most service requests were made via phone, as indicated by the large sections with a lighter green shade in both of them. Methods like chat, email, social media, mail, and mail-out are not often employed relative to phone submissions. the sixth chart displays the range of service request duration, where most requests are handled in less than 50 days. 

In addition, there is a summary of request duration in terms of mean and standard deviation, with mean request time around twelve days with a maximum reaching 653 days.The seventh figure shows the counties with the most requested services, indicating that downtown is the leading city in both years. Ultimately, these visualizations focus on differences in service request patterns between the two years.

## Insights and Findings.
The trend analysis of the frequency of service requests for 2023 and 2024 shows a pattern of seasonal fluctuations in the number of requests. The highest number of service requests was recorded in the first quarter of 2023, with January and February having the highest rate associated with the winter period and, therefore, involving issues like snow clearance and infrastructure upkeep. There was a peak in the number of requests midway through the year, and then the frequency was much steadier for the rest of the time, though it did increase slightly in the summertime. However, the service requests in 2024 had a different pattern from the previous years' service requests, which started rising from November 2023 and reached their highest in the first months of 2024. Such a pattern implies that the later quarters of 2023 or 2024 witnessed increased service demands, possibly caused by the city’s increasing preoccupation with end-of-year infrastructure issues or winter-related challenges. That is why city services should anticipate a higher demand during the cold period, usually within the year's first quarter.

Subsequently, an examination of the frequency of the different types of service requests revealed that most of them were ‘City Services Feedback Case’ in 2023 and 2024, with all or nearly all the entries of the type. The fact that all of the requests are of the same kind means that residents use the application actively to report different concerns rather than explicitly requesting any particular service, such as pothole repair or garbage collection. The lack of variation in the types of services requested in the dataset may point to the need to create awareness and increase the usage of other services the city can offer so that its citizens can acquire more specialized services when needed. Furthermore, the relative stability in request types over the years indicates that the nature of issues that residents bring to the city's attention, primarily through feedback, has not changed.

The pie charts depicting the difference in the kind of submission in 2023 and 2024 to the service show a higher degree of phone submission. Phone requests dominated the number of requests in both years, and other forms of requests, including chat, email, social media requests, mail, and mail-outs, only featured as a fraction of the overall request. This overly exclusive reliance on phone submissions does point to issues such as accessibility, frequency, and preference. It also poses another question as to whether digital or online media are not fully exploited because people are not aware of them or cannot access them. The city could explore programs to advertise online submission channels like web forms or mobile applications, mainly to youngsters or the tech-savvy population. Furthermore, comparing the channel preferences by local area could provide insights into geographic or demographic differences in citizens’ engagement with city services.

The closure reason ‘Service Provided’ was the most used, followed by ‘Closed Automatically and Sent to Service Group’ and ‘Referred to Another Service Group.’ These high numbers show that many requests are being channeled to the wrong department or must be redirected to multiple departments before being solved. This could be inefficient in handling requests, and this might lead to residents experiencing a long time waiting for their issues to be resolved. One possible solution to this issue could be to enhance the primary way requests are sorted within the system to route them to the proper departments. Further, requests that are marked “Reviewed and No Action Planned” indicate that there are some requests that are non-actionable. The city could use better information and communicate with the residents about what requests meet those criteria.

The bar charts showing the distribution of local areas regarding service requests reveal disparities in demand for service within the city. The Downtown Vancouver area remained famous for service requests throughout 2023 and 2024, with other areas including Kitsilano, Mount Pleasant, and Kensington-Cedar Cottage. They are the areas of high people demand that can require increased resources for city services to fulfill the needs of residents. On the other hand, low request areas indicate low population density or improved access to services where incident interventions are less frequent. The pattern of the requests gathered geospatially will further guide the city's planning and respond adequately to the frequently visited areas, especially regarding response time. Also, examining whether some regions react more slowly than others could reveal shortcomings in the organization’s service provision, including inadequate staffing or difficulties in reaching areas in the capacity needed to meet their demands.

In sum, the analysis of 311 service requests for the canonical Pacific Northwest city, Vancouver, with data for 2023 and 2024, holds critical insights that may prove binding for decision-making and resource distribution of the town. It is to be noted that high-traffic periods of service delivery occur in winter months, which signals the importance of anticipating and addressing issues related to snow and maintenance of the physical structures. The dominance of phone channels regarding submissions may indicate the need to enhance the publicity of online and digital channels. However, optimizing request closure, such as referral and redirection, could improve service delivery and operational efficiency while reducing residents’ frustration. Logistically, areas such as Downtown and Kitsilano are high-demand zones, hence the need to allocate resources to help them respond to service requests and maintain the infrastructure quickly. The strategies presented herein can be used to inform future enhancements to the public service delivery system in Vancouver for improved performance for residents and city departments.

## Recommendations
Due to seasonal variations, where the number of service requests is always high, particularly during winter, the City of Vancouver should adopt a proactive service delivery model. Such things could include setting up a specific time when there is expected to be a high utilization of the roads and utilizing extra personnel or equipment to cope with the problems of extreme weather, as in the cold seasons when there is the issue of snow or roads closure due to some calamity. Sophisticated forecasting techniques based on service demand data from previous years could also be used to identify periods of high demand to ensure that appropriate resources are provided. It also can be helpful to enhance public awareness of when specific services are seasonal and to provide more precise guidelines on where and how to submit service requests through online platforms, which could reduce demand on the phone lines and help ensure more efficient service provision during busy periods. Distributing the resource allocation more equally for a year will allow the city to minimize the backlog of requests and maintain a shorter response time during the peak of the winter season. 

As the main service type is “City Services Feedback Case,” the municipal departments of Vancouver should increase the awareness of other services. This could entail conducting awareness campaigns to inform the residents on specific service delivery areas, such as fixing potholes, waste collection, and safety measures, and urging them to report any related issues to the right authority. If more information is given to citizens to explain what kind of requests are acceptable under different categories, more restrictions on feedback submissions and more effective use of the service platform by the city will result. In addition, a more enhanced user experience of the submission platform, particularly in the context of multichannel encounters, can promote better service classification and reduce the instances of recourse to manual passing on cases from one department to another. A more user-friendly interface and well-defined services would provide explicit instruction on the residents' precise and focused service demands, allowing departments to tackle problems more efficiently. 

Since most of the submissions have been through the phone, the city should ensure that online and digital platforms are promoted. Although reliance on phone submission points to the possibility of achieving convenience for some population groups, there is a low uptake of online technologies, which could be convenient for residents using advanced technologies. The city could develop a campaign to provide residents with an understanding of how to apply for something online or via an application, at least for the tasks that do not need a phone call. In conjunction with these, the usability, availability, and stability of these digital platforms should be enhanced to ensure that they are effective, efficient, and scalable to accommodate numerous requests. A transition to online will not only alleviate pressure from phone lines. Still, it will also enhance faster and more accurate sorting of service requests to the correct department, minimizing time wasted due to misplaced or untimely requests.


