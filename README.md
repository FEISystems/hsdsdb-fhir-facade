# hsdsdb-fhir-facade

a) PostgreSQL Database setup 

* Download PostgreSQL database version 9 or later: https://www.postgresql.org/download/ (choose right version for the OS)
* Install PostgreSQL database 
* Create user account "hsds" and set the password "hsds2fhir" (or any other that can be specified in Mirth)
* Use HSDS_DB_TEST_backup.dump from the database folder of this repository using the following command: 
  type HSDS_DB_TEST_backup.dump  | psql -U hsds -h localhost -p 5432 -d HSDS-DB-TEST
* Run pgAdmin to make sure that user "hsds" account is able to connect to this new database HSDS-DB-TEST


b) Mirth Connect setup 

* Download and install Java if it is not already installed: https://www.java.com/download/ie_manual.jsp
* Download and install Mirth Connect 3.10.1: https://mirthdownloadarchive.s3.amazonaws.com/index.html?prefix=connect/3.10.1.b280/ (choose right version for the OS)
* Run Mirth Connect Server Manager and Mirth Connect Service
* Open Mirth Connect Administrator to make sure the Mirth is running successfully
* Refer to Mirth Connect User Guide for more detailed reference: https://www.nextgen.com/-/media/files/nextgen-connect/nextgen-connect-310-user-guide.pdf
* Download FHIR Extension for Mirth Connect 3.10.1 
* Follow Mirth FHIR Extension setup guide: https://techno-soft.com/fhir-setup-on-mirth-connect.html/ 
* Refer to Mirth FHIR Connector Guide if more information needed: https://docs.nextgen.com/bundle/Connect_FHIR_Connector_User_Guide/page/topics/c_overview_fhir_UG.html


c) Setup HSDSDB-FHIR-Facade 

* Open Mirth Connect Administrator desktop 
* Use Import Channel from "Channels" section to import HSDS_FHIR_Listener_Facade.xml (imported as HSDS_FHIR_Listener_Facade channel name)
* Modify SourceConnector settings to change port if needed (default setting is 8080 which should be open for connectivity) 
* Update deployScript to update any database connection variable (especially facadeDBUsername and facadeDBPassword based on Database setup above) 
