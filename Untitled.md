# Software Requirements Document

## Project Information

**Project Name:** EcoScreen

**Project Owner:** This Company Inc.

**Version:** 1.0

**Date:** June 24, 2025

## 1. Introduction

The purpose of this document is to outline requirements for the development of the EcoScreen app tracker, a mobile application created to track the screentime of a users social media use, convert that into CO2eq using accepted metrics and display the results to the user as visual comparisons with events found in the natural world. This document will function as a guide for both the development team and all stakeholders involved to ensure all necessary features and functionalities are explained transparently and implemented, to provide end-users with comprehensive insights into their social media consumption and to help restore an awareness of their relationship to the physical world, while gently encouraging more healthy phone usage and consideration for the climate.

## 2. Scope

The scope of EcoScreen app tracker includes the following:

**Feature 1: Real-time app usage tracking and monitoring**

- Track the cumulative usage of individual social media apps
- Provide an insight into patterns of behaviour/ regular app consumption
- 

// THESE CAN BE MORE BENEFITS THAN FEATURES (?)

**Feature 2: Convert individual app-use into CO2eq emissions**

- Safely store and handle screentime data in accordance with GDPR
- Use accepted GHG Conversion Metrics to calculate CO2eq emissions of app usage
- Compare app emissions with familiar natural events ("x mins = y trees")
- 
- Present that provide insight, greater context, awareness of physical activity

**Feature 3: Data Analytics and Reporting**

- Show cumulative app usage between daily, weekly, monthly increments
- Provide comparative analytics between periods of use 
- Create visuals with charts and graphs to communicate natural CO2eq comparisons
- 
- Compare usage between this and previous week 
- Usage and progress equated to natural events  



**Feature 4: Digital Wellness Tools**

- Empower users to have better control over their social media habits
- Encourage curiosity about the natural world, promoting better health
- Offers a CBT-like break in the cycle of use, promoting mindfulness
- 
- Set app usage limits and time-based restrictions
- Configure break reminders and mindful usage notifications
- Implement focus modes and app blocking capabilities

## 3. Functional Requirements

### 3.1 Real-time app usage tracking and monitoring

- **Requirement 1.1:** The system will track the time spent using each installed social media application within an accuracy of 5 seconds
- **Requirement 1.2:** The system will record each session duration and timestamps for individual social media app use
- **Requirement 1.3:** The system will accumulate individual app screentime and total each session per day
- **Requirement 1.4:** The system will store this personal data in accordance with GDPR

### 3.2 Convert individual app-use into CO2eq emissions

- **Requirement 2.1:** The system will store and handle personal user data in accordance with GDPR laws and regulations (what does that look like and write it here)
- **Requirement 2.2:** The system will use accepted GHG conversion metrics to calculate the CO2eq emissions of individual app use
- **Requirement 2.3:** The system will provide greater context of app use by comparing CO2eq results with events occurring in the natural world.
- **Requirement 2.4:** The system shall allow users to export usage data in CSV format for external analysis (?)

THESE TWO ARE THE SAME? 2 AND 3 RIGHT?
### 3.3 Data Analytics and Reporting

- **Requirement 3.1:** The system will accumulate social media app use and display it as daily, weekly, and monthly increments with visual representations
- **Requirement 3.2:** The system will provide usage analysis by comparing current usage patterns with historical data, (by day, week, month? /over customizable time periods)
- **Requirement 3.3:** The system shall calculate and display usage metrics including average session length, most used apps, and peak usage hours
- **Requirement 3.4:** The system shall allow users to export usage data in CSV format for external analysis

### 3.3 Digital Wellness Tools

- **Requirement 3.1:** The system shall allow users to set daily time limits for individual apps or app categories with customizable enforcement levels
- **Requirement 3.2:** The system shall provide configurable break reminders and mindful usage notifications based on usage patterns
- **Requirement 3.3:** The system shall implement focus modes that can temporarily block distracting apps during specified time periods

## 4. Non-Functional Requirements

- **Requirement 4.1:** The application shall have minimal impact on device battery life, consuming no more than 2% of total battery capacity per day during normal operation
- **Requirement 4.2:** The system shall maintain 99.5% uptime for data collection services and respond to user interactions within 2 seconds
- **Requirement 4.3:** The application shall be compatible with Android 8.0+ and iOS 13.0+ devices
- **Requirement 4.4:** The system shall handle data collection for up to 500 installed apps without performance degradation

## 5. User Interface Design

- **Design 1:** The main dashboard shall feature a clean, intuitive layout displaying key metrics through interactive charts, usage summaries, and quick access to most-used apps with a card-based design approach
- **Design 2:** The app details view shall provide comprehensive information for individual applications including usage graphs, session history, and limit management controls with drill-down capabilities
- **Design 3:** The settings interface shall organize configuration options into logical groups (privacy, notifications, limits, data management) with clear visual hierarchy and accessibility compliance

## 6. System Architecture

- **Architecture 1:** The application shall follow a modular architecture with separate components for data collection, analytics processing, user interface, and data storage, utilizing local SQLite database for primary data storage
- **Architecture 2:** The system shall implement a background service architecture that operates independently of the main application UI, ensuring continuous data collection while minimizing resource consumption
- **Architecture 3:** The application shall use a plugin-based architecture for different operating systems (Android AccessibilityService, iOS Screen Time API) to ensure platform-specific optimization

## 7. Data Requirements

- **Requirement 7.1:** The system shall store app usage data locally on the device using encrypted SQLite database with automatic data retention policies (default 12 months)
- **Requirement 7.2:** The system shall maintain data integrity through regular backup procedures and provide data recovery mechanisms in case of application crashes or device issues
- **Requirement 7.3:** The system shall implement data compression techniques to minimize storage footprint while maintaining query performance for historical data analysis
- **Requirement 7.4:** The system shall provide optional cloud backup functionality with end-to-end encryption for data synchronization across multiple devices

## 8. Security Requirements

- **Requirement 8.1:** All user data shall be encrypted at rest using AES-256 encryption and transmitted using TLS 1.3 protocol for any network communications
- **Requirement 8.2:** The application shall implement privacy-by-design principles, ensuring no personally identifiable information is collected without explicit user consent, and providing granular privacy controls
- **Requirement 8.3:** The system shall require user authentication (biometric or PIN) for accessing detailed usage reports and sensitive settings modification
- **Requirement 8.4:** The application shall comply with GDPR, CCPA, and other applicable data protection regulations, including right to data deletion and portability

## 9. Performance Requirements

- **Requirement 9.1:** The application shall process and display usage statistics for up to 30 days of historical data within 3 seconds of user request
- **Requirement 9.2:** The background monitoring service shall consume no more than 50MB of RAM during normal operation and efficiently manage memory usage to prevent device slowdown
- **Requirement 9.3:** The application shall start up and display the main dashboard within 2 seconds on devices meeting minimum system requirements
- **Requirement 9.4:** The system shall handle concurrent usage tracking for up to 10 active applications without data loss or significant performance impact

## 10. Testing Requirements

- **Requirement 10.1:** The system shall undergo comprehensive unit testing with minimum 85% code coverage, integration testing for all major user workflows, and performance testing under various device conditions
- **Requirement 10.2:** The application shall be tested across different device models, operating system versions, and usage patterns to ensure consistent behavior and accuracy of data collection
- **Requirement 10.3:** Security testing shall include penetration testing, data encryption validation, and privacy compliance auditing by third-party security experts
- **Requirement 10.4:** User acceptance testing shall be conducted with diverse user groups to validate usability, accessibility, and feature effectiveness

## 11. Project Timeline

|Task|Start Date|End Date|
|---|---|---|
|Requirement Gathering|July 1, 2025|July 15, 2025|
|Design and Prototyping|July 16, 2025|August 15, 2025|
|Development Phase 1 (Core Features)|August 16, 2025|October 15, 2025|
|Development Phase 2 (Advanced Features)|October 16, 2025|November 30, 2025|
|Testing and Quality Assurance|December 1, 2025|December 31, 2025|
|Deployment and Launch|January 1, 2026|January 15, 2026|

## Revisions

|Version|Date|Description|
|---|---|---|
|1.0|June 24, 2025|Initial version with core requirements|
|1.1|[Date]|Updated functional requirements based on stakeholder feedback|

## Signatures

**Project Owner**: ___________________________________________________

**Project Manager**: ___________________________________________________

**Lead Developer**: ___________________________________________________

**QA Manager**: ___________________________________________________