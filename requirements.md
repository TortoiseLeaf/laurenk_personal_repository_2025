### Fucntional

1. App Launch and Initialisation. The system should initialise the database, check for permissions and verify user consent upon the app launch
2. Permission request, the system should use Android api to request usage permissions through the device system settings
3. Consent Management, the system should present a clear privacy notice and receive explicit user consent before tracking any personal data
4. Usage Data Collection (Android api) The system should collect usage statistics like foreground time from the Android UsageStatsManager api for a predetermined list of social media applications
5. Social media app detection, the system should identify and only track a predetermined list of social media apps
6. Data Storage, System should store all usage data locally on the device
7. Daily, Weekly usage display, App should display the current day or weeks usage statistics including daily and weekly total time spent per application
8. Data Insights, daily and weekly total usage should be compared with previous entries to report any increase/decrease in app usage 
9. Data and Insights should be mapped and displayed clearly and understandably to the user
10. Usage Time formatting, the system should convert milliseconds into hours and minutes for readability
11. Consent Withdrawal the system should allow for users to withdraw their consent at any time for data collection.
12. Data deletion, the system should allow users to delete their data at any time
13. Data retention, the system should only retain personal data for as long as is necessary for the app to function
14. Consent versioning, the app should track policy versions users have consented to, in order to ask for consent on updated data policies
15. Error handling, the system should handle errors gracefully and direct users to potential fixes within the app, or return empty datasets when errors occur to prevent system crashes.
16. Loading indicators, the app should show loading indicators to show the application is running and not broken
17. Total usage calculation, the app should show the sum of each tracked apps usage
18. CO2 calculation, the app should show the sum of CO2eq accumulated by app usage
19. Natural World Comparisons, a data table of natural world CO2 events should be accessed to present users with natural CO2 sink events, approximate to their decrease in CO2e emissions
20. Reporting, user daily and weekly decrease in app usage should show in CO2e and log to local data table, displaying by order descending as a "personal best" score board
21. Tree Scoring, app should accumulate user decrease in CO2 and when target "Xge" is met, "Tree Planted" database value is increased by 1

22. Tree Planting, app should report monthly to an external db where trees planted by all users can be totalled and the information passed on to forestry team

### non-functional
Performance -
- Low Resource Consumption, app should avoid impacting device battery and overall performance
- Reasonable Start up Time, app should launch within 4 seconds when tapped
- Low Crash Rate, app should handle errors gracefully by returning empty datasets on failed database operations, and providing users with useful error messages as an alternative to system crashes.
- Accurate Data Collection, app should collect data accurately, ideally without missing session information.
- Timely data delivery, app should deliver up-to-date (to the day) and relevant usage tracking

Security - 
- All personal data should be stored in a private storage directory, inaccessible to other applications.
- Ideally no direct, unprocessed personal data will be transmitted over any network connection
- Sensitive data will not be logged in system or debug logs in production
- Database queries should use parameterized statements
- The app should use proper disposal patterns for database connections to prevent memory leaks (!)
- User consent should be logged with timestamps for tamper-proofing and app auditing
- The app should operate with POLP (Principle of Least Privilege) to prevent unnecessary exposure of sensitive data

Usability (ICO)
- Logical flow, app structure and layout should be logical, intuitive and easy to navigate
- The privacy notice should include a summarized cliff-notes version easily understandable by the user.
- Text should remain at a standardized size ratio for readability
- Critical actions like data deletion should require confirmation before execution
- Tracked app usage data should be readable, simple and understandable within the layout