# Portfolio Project:

# Descriptive Analysis of Vancouver’s 311 Service Requests

## Project Description:
Descriptive Analysis Portfolio Project

## Project Title: 
Descriptive Analysis of Vancouver’s 311 Service Requests

## Objective:
The main objective of this project will be to provide a descriptive analysis of the service requests managed by the 311 contact center of Vancouver in the years 2023 and 2024. Through this analysis, it will be possible to understand specific patterns and potential trends in public service requests and responses, as well as possibilities for increasing the efficiency of service delivery. Such descriptions will also allow for an analysis of the activities of the city's departments and suggestions for improvements to the services rendered. 

## Dataset:

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
Figure 1:
The Outcome from The Cleaned Datasets

![Figure 1](https://github.com/user-attachments/assets/cff4bcb3-f940-4df0-9f18-a00b9ed7c85e)

The result of data cleaning for the 2023 and 2024 service request datasets indicates that the two datasets have been appropriately loaded, cleaned, and saved. Regarding 2023, there were missing values in many columns, including 217 in the Closure reason, 228 in the Service request close date, and 1,096 in the Address, Latitude, Longitude, and geom group. The same observation was made in the 2024 dataset, as there were more missing values in similar columns, including 296 in Closure reason, 302 in Service request close date, and 840 in location-related attributes. As illustrated in Figure 1, the overall structure of the cleaned 2023 data has 5,658 record entries and 3,549 record entries of the cleaned 2024 data. However, neither of them contains any duplicate records. The data of both datasets has passed the cleaning process, and the necessary columns such as department, request type, status, closure reason, timestamps, addresses, and geospatial representation have been retained and preserved for further analysis. The cleaned datasets were saved for future use in Excel format.

### Descriptive Statistics and Basic Data Exploration. 

In Step 2, cleaned datasets of 2023 and 2024, the databases for this analysis, are loaded, and after a quick examination, the following patterns and trends are identified in the service request data. The first aspect of this step is to determine the total number of services received in a specific year to form the basis of understanding the second part of this step, which is identifying the various types of service requests and determining which type of service requests are likely to be received most often. The status distribution also demonstrates the relative share of open, closed, and requests with other statuses. Subsequently, the mean time to address service requests is calculated as the time difference between the request open and closed timestamps to ascertain the time to tend to specific requests. Furthermore, the distribution of the service request submission choice, like telephone or electronic submission, is also analyzed to discover the frequency with which the public employs different modes of service request submission. Ultimately, the distribution of requests is presented based on the geographic location with the most requests. It considers the 2023 and 2024 years individually and jointly to provide deeper insight into Vancouver’s 311 system service requests.

Figure 2:
The Descriptive Statistics

![Figure 2](https://github.com/user-attachments/assets/e9a61d7d-5fef-411c-bc52-38a1d8926563)

Figure 2 illustrates the descriptive analysis of the 311 service requests situation in Vancouver for 2023 and 2024. Although in 2023, the total number of service requests was 5,658, that number was reduced by mid-2024 to 3,549. Again, as highlighted in the above figure, the most frequent type of request encountered in both datasets was the “City Services Feedback Case;” which constituted all service requests made in the two years under review. The status distribution indicates that both years' recorded requests were “Closed. ” When calculating the average request time for both years, it took approximately 11.22 days to resolve a request in 2023. In contrast, in 2024, the average resolution time increased to 13.58 days, suggesting a slight delay in handling requests.

The most utilized means of submitting the requests was the telephone in the two years, with 5,437 telephone requests submitted in 2023 and 3,463 in 2024. Chat, social media, and email were used much less frequently than call centers as a mode of communication. Concerning the distribution of service requests by region, the number of requests for both years was the highest in the Downtown region, followed by Kitsilano, Mount Pleasant, and Kensington-Cedar Cottage. The analysis of the first five closure reasons for service requests shows that most of the service requests, namely 4,532, were classified as “Service provided,” meaning that the service requested was delivered. 

The second most frequent reason (1,571) is “Closed automatically and sent to a service group,” which means such requests were automatically forwarded for further processing. Another 1,118 were closed with the reason ‘referred to another service group,’ indicating that many requests were passed on to other departments. ’Reviewed and no action planned’ (939) means that some of the requests did not need further action; ‘Further action has been planned’ (466) means that some of the requests will need further action in the future. These reasons give information on the different processes through which service requests are handled and closed.

### Data Visualizations
Figure 3:
Time Series On The Number of Service Requests

![Time Series](https://github.com/user-attachments/assets/bbb18b4d-3b80-48c1-9ae6-a3fdc18c37f1)


Figure 4: 
The Type of Service Request

![Service Request Type](https://github.com/user-attachments/assets/3c59c64c-5704-478b-a1b9-db544151b92c)


Figure 5:
The Distribution of Submission Channels Used.

![Submission Channels Distribution](https://github.com/user-attachments/assets/bdff4da9-6d46-40c0-ab1a-db6d9bb8a329)


Figure 6:
The Request Durations In Days.

![Service Request Duration](https://github.com/user-attachments/assets/91a54303-2993-4ab7-b52c-f59842ed8760)


Figure 7:
Local Area Distribution Comparison:

![Top 5 Local Areas](https://github.com/user-attachments/assets/f633dc1a-99cd-4ae8-b72f-9ac2dd9b9729)

The visualizations show how Vancouver 311 service requests differ in Year 2023 and Year 2024. The first chart (Figure 3) is the Time Series chart that indicates the total of service requests using different trend lines for each year and having different trends, where 2023 has more requests in the initial months of the year, and 2024 has upward tendency from the late months of the year 2023 and increasing till the early months of 2024. Figure 4 shows the most frequent service requests: the “City Services Feedback Case” is on the top of the 2023 and 2024 lists.  

Figure 5 features two pie charts illustrating the submission channels of service requests for 2023 and 2024. In both years, most service requests were made via phone, as indicated by the large sections with a lighter green shade in both figures. Methods like chat, email, social media, mail, and mail-out are not often employed relative to phone submissions. Figure 6 displays the range of service request duration, where most requests are handled in less than 50 days. 

In addition, there is a summary of request duration in terms of mean and standard deviation, with mean request time around twelve days with a maximum reaching 653 days. Figure 7 shows the counties with the most requested services, indicating that downtown is the leading city in both years. Ultimately, these visualizations focus on differences in service request patterns between the two years.

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


