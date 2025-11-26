Create a requirements document that agrees, with respect to all stakeholders involved, the purpose of the project.
https://community.fabric.microsoft.com/t5/Desktop/Business-Requirement-Document-Template/td-p/4292114

Do it first and then see what other LO points can be added into it, or drawn from it.
# **Business Requirement Document (BRD)**

## **Project Details**

- **Project Name**:
- **Project ID**:
- **Project Manager**:
- **Document Author**:
- **Date of Creation**:
- **Last Updated**:

---

## **1. Executive Summary**

- **Objective**:  
    The objective is to create a background health app that integrates into the phones ecosystem, converts the screentime of individual apps into CO2eq per cumulative sessions of use and compares user emissions with familiar quantifiable events in nature (e.g. "equivalent to CO2 consumed by x trees a year"). 
    The end-goal is to empower the user to make more informed decisions about their media consumption by providing a greater context to otherwise seemingly non-physical activities.
    The goal is to gamify the experience by storing and comparing previous sessions of use and incentivising the user by encouraging competition on breaking previous records. 
    The goal is to help to reduce habitual media and social media overuse and reconnect users with an awareness of the physical environment, with hopes of reducing/alleviating mental illness associated with phone overuse and also creating the beginnings of lasting positive change towards the environment. 

    subtly interrupt the flow of functions as a subtle buffer between users and social media apps, to help mitigate everyday overuse. The goal is to try to reduce habitual media and social media overuse by providing users a passive insight into their phone habits. Much like inbuilt pedometers, the hope is to empower users with an insight into their actions and by creating a greater context around them, allowing more informed decisions about phone use and app consumption to be made. 

Takes the time spent and converts into CO2eq so users can see thier 
suggestions for things you can do instead, scavenger hunt like go outside and find something purple, get a 10 minute walk . that time saved can build up the amount of co2eq saved 

- **Business Need**:  
    (Why is this report required? What business problem does it solve?)
- **Stakeholders**:
    - Primary Users:
    - Phone user demographics
    - older users probably care more, younger users probably more affected. Sweet spot could be 25 - 50 year olds? Data for that? Mental and physical health stats, need to engage with the environment stats and ages
    - Decision-Makers:
    - Delivery staff? Dev team, investing bodies
    - Data Owners:
    - Dev team, End-users

---

## **2. Scope of Work**

- **In-Scope**:  
    - The app should act as a subtle background mobile health app. 
    - It should quietly track the screen time of specific phone applications (Facebook, Instagram etc) 
    - It should store this sensitive data safely in a database and handle it in accordance with GDPR.
	- It should use (and reference) both accepted greenhouse gas (GHG) emission calculations and reputable data about the applications use to calculate habitual user app use into relative CO2 emissions. 
	- The app should use the stored data to compare with previous app use and quantify these findings into familiar and encouraging metrics with the hopes of engaging and grounding the user (e.g. "by spending x amount less time on TikTok, you've done the work of y trees in a year!")
- **Out-of-Scope**:  
    (Define any exclusions or limitations of the project.)

---

## **3. Key Requirements**

### **3.1 Functional Requirements**

- **Data Sources**:  
    (Specify the data sources that will feed into Power BI, e.g., databases, Excel files, APIs.)
    - Device App Usage (needs permissions, use app statistic API)
    - Database (TBD)
- **Metrics & KPIs**:  
    (List of metrics/KPIs to be calculated and displayed.)
- **Reports/Dashboards**:  
    (Types of reports/dashboards required, e.g., Sales Performance, Financial Analysis.)
- **Data Refresh Frequency**:  
    (Specify how often the data will be updated in Power BI.)
- **User Roles and Permissions**:  
    End User will have to give app permissions to track data from their phone
- The system requests permission to track usage of certain apps on the device
- The system requests permission to send push notifications to the user(?)
- User can select the apps to track(?) and the frequency of reports(?)
- The App silently tracks phone use in the background (app should not need to be open to do this, it should happen automatically)
- The App sends this data once a day/ once per session of phone use(?) to the database.
- The recorded app tracking data should accumulate
- The recorded data is used to convert minutes in apps to CO2eq (based on fixed, reputable sources)
- The app displays the results of these calculations 
- The app displays the calculated data, quantified into familiar comparisons like "this was equivalent to a tree/x square feet of plankton/ other natural events"
- The user opens the app to check
- The app prompts the user with a push notification(? kind of against the point of it being unintrusive)
- Users should be able to delete the app and request their data is deleted (look at gdpr for sensitive data)
- 

### **3.2 Non-Functional Requirements**

- **Performance**:  
    - Expected loading times
    - App should not drain battery, be as performant and battery efficient as possible
    - App should not slow down other phone processes
    - App should run silently in the background and be unnoticeable
- **Scalability**:  
    (Requirements for future data growth and additional users.)
    - Database should hold lots of data, be accessible, reliable and performant under load 
    - Could in future include leader boards. Could begin with personal bests and flesh that out to include others? Need a username or UID for that. (UID automatically generated, but how do users prove ownership for their data? could request it? but then significant device data could be shared. Maybe the UID can be shown in the app. ("Congrats! Welcome user 223")
- **Security**:  
    (Define data security and compliance requirements, e.g., GDPR.)
    - GDPR for sensitive data
	    - collecting
	    - handling
	    - deleting

---

(==follow PascalCase for classes, methods, and constant names, and camelCase for local variables and method parameters==)
## **4. Data Requirements**

- **Data Fields**:  
	- appName - human-readable name of application being tracked for usage
	- packageName - name of the identifier of the app "com.instagram.android"
	- category - category of the app (necessary?)
	- dateTime - specific date of app usage
	- usageTimeMilliseconds - total time spent in app in ms
	- createdAt - timestamp when record is first created
	- lastUpdated - timestamp when record was last updated
	- LaunchCount - number of times app launched (necessary?)
	
	- convertedCo2eq - individual app usage data calculated to CO2eq
	- 
	
	- hasConsented - user has given permissions
	- consentDate - date consent was given
	- consentVersion - version of T&C's agreed to
	- canProcessData - explicit permission to process their data
	- withdrawnDate - when consent is withdrawn?
	- dataRetentionDays - number of days data will be retained, when will be deleted

    (List the data fields and their descriptions required for reporting.)
- **Data Transformation**:  
    (Describe any transformations or calculations required.)
- **Data Quality**:  
    (Specify expectations for data accuracy and completeness.)

---

## **5. Visualization Requirements**

- **Report Layout**:  
    (Outline the design and layout preferences for dashboards and reports.)
- **Filters and Interactions**:  
    (Specify dynamic filters, drill-through, or cross-filtering needs.)
- **Visual Types**:  
    (Bar charts, line graphs, tables, maps, etc.)

---

## **6. Integration Requirements**

- **Source Systems**:  
    (Details of systems that will provide data, e.g., ERP, CRM.)
- **Output Channels**:  
    (Will the reports be embedded, shared via email, or accessed through the Power BI service?)

---

## **7. Success Criteria**

- **Key Deliverables**:  
    (List measurable outputs of the project, e.g., dashboards, datasets.)
- **Acceptance Criteria**:  
    (Define the criteria to consider the project successful.)

---

## **8. Risks and Assumptions**

- **Risks**:  
    (Potential challenges or risks that may impact the project.)
- **Assumptions**:  
    (Key assumptions for project planning and execution.)

---

## **9. Timeline and Milestones**

- **Start Date**:
- **End Date**:
- **Key Milestones**:  
    (E.g., Data model creation, report prototype, final delivery.)

---

## **10. Sign-Off**

- **Prepared By**:
    - Name:
    - Signature:
    - Date:
- **Approved By**:
    - Name:
    - Signature:
    - Date: