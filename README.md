Alcoholic liver disease treatment effects
=============

<img src="https://img.shields.io/badge/Study%20Status-Started-blue.svg" alt="Study Status: Started">

- Analytics use case(s): **Characterization, Population-Level Estimation**
- Study type: **Clinical Application**
- Tags: **Liver, Alcoholic liver disease, Drug, Gender**
- Study lead: **Prof. Dr. Dr. Andreas Teufel, Medical Faculty Mannheim, Heidelberg University, Germany**
- Study lead forums tag: **[[Lead tag]](https://forums.ohdsi.org/u/[Lead tag])**
- Study start date: **-**
- Study end date: **-**
- Protocol: **[Here](https://github.com/titzel/AlcoholicLiverDisease/blob/master/documents/Protocol.docx)**
- Publications: **-**
- Results explorer: **-**

Within this study we are interested in investigating new treatment options for patients with alcoholic liver disease respectively inside different sub groups as well as gender specific in respect of the overall survival of the patients.


How to run
===========

1. To easily run this package, R need to be installed and also the dependencies 'SqlRender', 'DatabaseConnector' and 'survival'.

2. Please install the package for this study. Example from the command line on a linux system.

   ```bash
       R CMD build AlcoholicLiverDisease
       R CMD INSTALL AlcoholicLiverDisease_0.0.1.tar.gz
   ````
 
3. Open an interactive R session and execute the adapted commands below.



  ```r
      library(AlcoholicLiverDisease)
      
      connectionDetails <- DatabaseConnector::createConnectionDetails(
          dbms = "sql server", 
          server = "localhost", 
          user = "SA", 
          password = "App1app1", 
          schema="TEST", 
          port = "1433"
      )
      
      execute(
          connectionDetails,
          resultsSchema="results",
          studyName="STUDY",
          sourceName="sourceName"
      )
  ```
4. Once the execution finished, the results will placed as ZIP files inside the tempdirectory of the R session. Please send them back to the study coordinator.
