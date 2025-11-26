https://www.perforce.com/blog/alm/how-write-software-requirements-specification-srs-document
# Software Requirements Specification

## Social Media Usage Tracker Application

**Version:** 1.0  
**Date:** October 7, 2025  
**Project:** Social Media Usage Tracker  
**Platform:** .NET MAUI 8.0+  
**Author:** Development Team

---

## 1. Introduction

### 1.1 Purpose

This Software Requirements Specification (SRS) document should provide a complete description of the Maui Screen Time mobile application. The document describes all functional and non-functional requirements necessary for the completion of version 1.0 of the application. This SRS is intended for use by all developers, testers, project managers, and stakeholders involved in the development and deployment of the app.

This application aims to help users understand their mobile media consumption in relation to its physical impact on the natural world, and to provide a gamified solution to reduce personal screen time to the benefit of both personal, and wider ecological and cultural health. It reveals usage patterns and offers personal carbon offset goals by tracking usage time and across multiple social media platforms and connecting users with local tree planting initiatives, while maintaining strict GDPR compliance and user privacy standards.

### 1.2 Intended Audience

This document is intended for the use of:

- **Software Developers**: As a guideline to understanding both implementation requirements and technical specifications
- **Quality Assurance Teams/Testers**: For the purpose of developing test plans and acceptance criteria
- **Project Managers**: In order to plan resources, project timelines, and outline deliverables
- **UI/UX Designers**: For creating user interface designs and layouts that meet necessary functional requirements
- **Legal**: To create GDPR policy and verify its compliance with regulation
- **Stakeholders**: To more clearly understand the proposed project scope and capabilities
- **Technical Writers**: To aid in developing accurate and useful user documentation

### 1.3 Intended Use

The Maui Screen Time app is designed to be used by:


- **Primary Users**: Individual Android mobile device users who want to monitor and reduce their social media usage, and understand it in a wider context of real-world physical impact
- **Use Context**: Daily personal use for breaking addictive social media habits, self-awareness and general digital wellbeing
- **Use Environment**: Personal smartphones and tablets running Android 5.0+ (API 21+)

### 1.4 Product Scope

**In Scope:**

- Local tracking of social media application usage time
- Conversion of app usage minutes into CO2eq
- Weekly usage reports for documenting use increases and decreases
- Local tree planting coordination, rewards for meeting screen time reduction goal
- GDPR-compliant consent management
- Local SQLite database storage
- Daily and weekly usage statistics and summaries
- Monitoring 5+ major social media platforms ( could do Facebook, Instagram, Twitter/X, TikTok, Snapchat, LinkedIn, Pinterest, Reddit, Discord, WhatsApp)
- User data deletion and consent withdrawal
- Cross-platform support (Android primary, iOS limited)

**Out of Scope:**

- Cloud synchronization or backup
- Multi-device data aggregation
- Third-party API integrations
- Social media content analysis
- Screen recording or screenshot capture
- Network traffic monitoring
- Browser-based social media tracking
- Push notifications and reminders (future enhancement)
- Usage goals and limits enforcement (future enhancement)
- Detailed analytics and data visualization (future enhancement)

### 1.5 Definitions and Acronyms

| Term                 | Definition                                                         |
| -------------------- | ------------------------------------------------------------------ |
| **API**              | Application Programming Interface                                  |
| **GDPR**             | General Data Protection Regulation (EU Regulation 2016/679)        |
| **MAUI**             | Multi-platform App UI - Microsoft's cross-platform framework       |
| **SRS**              | Software Requirements Specification                                |
| **SQLite**           | Self-contained, serverless, zero-configuration database engine     |
| **Usage Stats**      | Android API for accessing application usage statistics             |
| **Foreground Time**  | Time an application is visible and active on screen                |
| **Consent**          | Explicit user permission for data collection and processing        |
| **Right to Erasure** | GDPR right allowing users to request deletion of their data        |
| **Data Retention**   | Period for which data is stored before automatic deletion          |
| **Local Storage**    | Data stored on the device without transmission to external servers |

---

## 2. Overall Description

### 2.1 User Needs

- Self-awareness Users need to understand how much time they spend on social media to make informed decisions about their habits
- Awareness of CO2eq cost, Users need to understand the physical cost of their digital habits within the context of the natural world
- Awareness of the natural world, Users need to be reminded of their proximity to the real and natural world, to the benefit of their mental and physical health and to the benefit of the greater ecosystem
- Tree planting Goals, Users need tangible static goals to gamify their screen time reduction efforts, that translate into real-world positive actions like tree planting.
- Privacy Protection, Users need confidence in that their personal data is stored locally and securely and is not shared with third parties, to respect their privacy rights.
- Data Control, Users need to be able to both access and delete their own personal data at any time, as is required of GDPR compliance.
- Simple Interface, Users need an intuitive and uncomplicated user interface which displays information clearly and directly
- Data use Transparency, Users need to clearly understand what data is collected, why, how it is processed and for how long it is kept.
- Consent Management, Users need to be able to give and withdraw consent for data collection at any time
- Accurate Tracking, Users need data tracking to be reliable and accurate in order to have statistics that accurately reflect their media and social media usage.
- Multi-platform support, Users need the app to work across the different social media platforms they use


### 2.2 Assumptions and Dependencies

**Assumptions:**

- Users will have Android 5.0+ (API 21+) devices
- Users will be willing to grant permissions for data collection
- Users will understand basic smartphone use
- Targeted Social media apps will be installed through official app stores
- User Devices will have sufficient storage space (Min 50MB?)
- Users read and understand English (initial version)
- Users will be 18+ and have legal capacity to provide consent 


**Dependencies:**

- .NET MAUI 9.0+ framework and runtime
- Android UsageStatsManager api (android)
- SQLite database engine
- Platform-specific permission system (Android app ops)
- Device file system access for local db storage
- Google play store distribution
- GDPR Compliance framework and legal review


---

## 3. System Features and Requirements

### 3.1 Functional Requirements

#### 3.1.1 Numbered and Described Requirements



#### 3.1.2 EARS Format Requirements

**Event-Response Requirements:**
1. On app launch, system should check for permissions and display the permission prompt if not granted
2. When user clicks "I consent/Grant permissions" the system saves the consent record with a timestamp and version to enable data collection. The system should open the devices usage access settings screen.
3. When the user clicks "Revoke consent" the app will mark consent as withdrawn, delete all usage data and hide or wipe the statistics UI
4. When the app is accessed without data permissions granted, the app shall render as empty and issue a warning.
5. Every 30 days the app shall delete the data records of the previous 30 days.
6. When a database operation fails, the system should log and display the error
7. If the device platform denies permission, the app should display a message explaining how to grant permissions manually
8. If consent is withdrawn, the system should set the WithdrawnDate field and prevent future data processing or collection.
9. When displaying usage time, the app should convert milliseconds to hours and minutes
10. When displaying usage CO2eq, the app should convert app usage minutes into CO2eq
11. When app usage CO2eq meets an equivalent value in the nature facts data table, the relevant natural event shall display
12. When users reduction in screen time meets the tree planting goal, a value gets added to the "Trees planted" personal scoreboard
13. At the end of every 30 day period, "Trees planted" scoreboard information is relayed to UHI forestry students, and trees equivalent to the amount in the scoreboard are planted.
14. When querying the Android stats usage api, the app should only process apps in the predetermined social media list
15. When the database file does not exist, the system will create it with an appropriate schema 


#### %% 3.1.3 Behavior-Driven Development (Gherkin Format) %%

```gherkin
Feature: User Consent Management
  As a user concerned about privacy
  I want to control whether my data is collected
  So that I can comply with my privacy preferences

  Scenario: First-time user provides consent
    Given the application is launched for the first time
    And no consent record exists in the database
    When the user views the main screen
    Then a privacy notice should be displayed
    And the consent button should be visible
    And usage statistics should be hidden

  Scenario: User grants consent
    Given the privacy notice is displayed
    When the user clicks "I Consent"
    Then a consent record should be saved with current timestamp
    And the consent version should be recorded as "1.0"
    And the privacy notice should be hidden
    And usage statistics should become visible

  Scenario: User revokes consent
    Given the user has previously granted consent
    And usage data exists in the database
    When the user clicks "Revoke Consent"
    Then the consent withdrawal date should be recorded
    And all usage data should be deleted from the database
    And the privacy notice should be displayed again
    And usage statistics should be hidden

Feature: Usage Data Collection
  As a user wanting to track my habits
  I want the app to collect my social media usage
  So that I can see how much time I spend

  Scenario: Collecting usage data with permission
    Given the user has granted usage access permission
    And the user has provided consent
    When the system queries usage statistics
    Then data should be retrieved for all tracked social media apps
    And the data should include usage time in milliseconds
    And the data should include launch counts
    And the data should be saved to the local database

  Scenario: Attempting to collect data without permission
    Given the user has NOT granted usage access permission
    When the system attempts to query usage statistics
    Then no data should be collected
    And a permission request UI should be displayed
    And the user should see instructions to grant permission

  Scenario: Attempting to collect data without consent
    Given the user has granted usage access permission
    But the user has NOT provided consent
    When the system attempts to query usage statistics
    Then no data should be collected
    And a warning should be logged
    And the consent request UI should be displayed

Feature: Data Display and Refresh
  As a user tracking my usage
  I want to see my current day's statistics
  So that I can understand my social media consumption

  Scenario: Viewing today's usage statistics
    Given the user has granted all permissions and consent
    And usage data exists for today
    When the user views the main screen
    Then the total usage time should be displayed in minutes
    And each social media app should be listed
    And each app should show usage time in minutes
    And each app should show the number of launches
    And apps should be sorted by usage time (highest first)

  Scenario: Refreshing usage data
    Given the user is viewing usage statistics
    When the user clicks the "Refresh" button
    Then the system should query the latest usage data
    And the database should be updated
    And the displayed statistics should reflect new data
    And a loading indicator should be shown during the process

Feature: Data Retention and Cleanup
  As a privacy-conscious user
  I want old data to be automatically deleted
  So that my storage footprint is minimized

  Scenario: Automatic data cleanup
    Given usage data older than 90 days exists
    When new usage data is saved to the database
    Then the system should identify records older than 90 days
    And those old records should be deleted
    And recent records should remain intact

  Scenario: Immediate deletion on consent withdrawal
    Given the user has 30 days of usage data
    When the user revokes consent
    Then all 30 days of data should be immediately deleted
    And the database should contain zero usage records
    And only the consent withdrawal record should remain
```

### 3.2 Non-Functional Requirements

#### 3.2.1 Performance Requirements

- Low Resource Consumption, app must efficiently manage memory and CPU to avoid negatively impacting device battery and overall performance
- Fast Start up Time, app should launch within 2 seconds when tapped
- Low Crash Rate, app should handle errors gracefully by returning empty datasets on failed database operations, and providing users with useful error messages as an alternative to system crashes.
- Smooth rendering, app should render frames quickly, ideally under 16 milliseconds for 60fps to ensure a smooth user experience.
- Accurate Data Collection, app must collect data accurately, without missing session information.
- Timely data delivery, app should deliver data in a timely manner to provide relevant and up-to-date screen time insights.
- Memory Usage, memory usage should not exceed 100MB during a 90-day dataset
- Data Maintenance, the app should handle concurrent database operations without corrupting data

#### 3.2.2 Security Requirements

- All personal data shall be stored in a private storage directory and be inaccessible to other applications.
- Database shall use SQLite's built-in security features like proper file permissions for read/write permissions
- No direct, unprocessed personal data will be transmitted over any network connection
- Sensitive data will not be logged in system or debug logs in production
- The app will validate all user inputs to prevent SQL injections
- Database queries should use parameterized statements
- The app should use proper disposal patterns for database connections to prevent memory leaks
- User consent should be logged with timestamps for tamper-proofing and app auditing
- The app should operate with the least-privilege principle to prevent unnecessary exposure of sensitive data

#### 3.2.3 
Usability Requirements

- Logical flow, the app structure and layout should be logical, intuitive and easy to navigate
- Task-based Testing should ensure users can achieve basic in-app tasks with ease and without getting lost
- The privacy notice should include a summarized cliff-notes version easily understandable by the user.
- Text should remain at a standardized size ratio for readability
- Critical actions like data deletion shall require confirmation before their execution
- Tracked app usage data should be readable, simple and understandable within the layout

Reliability Requirements

- the app should handle errors gracefully without crashing
- the app should recover from database connection failures with retry operations
- Database corruption should be detected on app start up and trigger automatic recovery procedures. (Blue/Green deployment?)
- The app should log critical errors for debugging while protecting user privacy
- Platform API failures should result in empty datasets and error messages instead of crashes

### 3.3 External Interface Requirements

#### 3.3.1 User Interfaces

The application shall provide a mobile-optimized touch interface with the following screens:

- **Consent Screen**: Displays policy and permissions prompt and consent controls with "I Consent" button
- **Permission Request Screen**: Shows permission status and "Grant Permission" button that opens system settings
- **Dashboard Screen**: Displays today's total usage time and list of social media apps with individual usage statistics
- **Data Controls**: Contains "Revoke Consent" button

All UI elements shall follow platform-specific design guidelines (Material Design for Android, Human Interface Guidelines for iOS).

#### 3.3.2 Hardware Interfaces

The application shall interface with device hardware through the operating system:

- **Android**: Access to UsageStatsManager API for reading app usage statistics
- **Storage**: Read/write access to device's local application data directory for SQLite database storage
- **Display**: Support for mobile screen sizes from 4.5" to 7" with touch input

#### 3.3.3 Software Interfaces

The application shall interface with the following software components:

- **.NET MAUI Framework 8.0+**: Primary application framework
- **SQLite Database Engine**: Local data storage (version 3.x)
- **Android UsageStatsManager API**: System service for retrieving app usage data (Android API Level 21+)
- **iOS Screen Time API**: Limited usage data access (iOS 15+, requires special entitlements)

#### 3.3.4 Communication Interfaces

The application shall operate entirely offline with no network communication requirements:

- **No Internet Connection Required**: All data processing occurs locally
- **No External APIs**: No communication with external servers or cloud services
- **No Data Transmission**: User data remains exclusively on the device
- **Local Database Only**: All storage uses SQLite on local device storage
### 3.4 System Features


**Permission management**
Critical priority. Manages device-level permissions required for the usage tracking. App launch requests permissions from the system if needed.

**Consent Management**
Critical priority. Manages user consent in compliance with GDPR requirements. User provides or revokes consent, the system records the decision and the system enables or disables user data tracking.


**Usage Data Collection Engine**
High priority. Collects usage data from Android stats API. App launches, system queries platform API and the system processes and stores the data.


**Local Data Storage System** 
Critical priority. Manages SQLite database for local data access. The data needs storage, system writes to SQLite and the system maintains the data integrity.


**Usage Statistics Display & CO2eq Comparison**
High priority. Presents usage to users in a readable format. Converts the minutes into CO2eq. App launches, user data is queried, minutes are converted into CO2eq and displayed alongside minutes and hours of use per app.


**Data Deletion System**
Critical priority. Handles the data deletion for users per GDPR compliance. Consent revoked or data expires, system deletes records and confirms deletion.


---

## 4. Other Requirements

### 4.1 Database Requirements

**DB-001**: The database shall use SQLite version 3.x or higher.

**DB-002**: The database file shall be named "usage_tracking.db3" and located in the application's LocalApplicationData directory.

**DB-003**: The database schema shall include the following tables:

- **AppUsages**: Stores usage records
    - Id (INTEGER, PRIMARY KEY, AUTOINCREMENT)
    - PackageName (TEXT, NOT NULL)
    - AppName (TEXT, NOT NULL)
    - Category (TEXT, DEFAULT 'Social Media')
    - Date (DATETIME, NOT NULL)
    - UsageTimeMilliseconds (INTEGER)
    - LaunchCount (INTEGER)
    - CreatedAt (DATETIME, NOT NULL)
    - LastUpdated (DATETIME)
    - UserConsented (BOOLEAN)
    - ScheduledForDeletion (DATETIME)
- **UserConsents**: Stores consent records
    - Id (INTEGER, PRIMARY KEY, AUTOINCREMENT)
    - HasConsented (BOOLEAN, NOT NULL)
    - ConsentDate (DATETIME, NOT NULL)
    - ConsentVersion (TEXT)
    - CanProcessData (BOOLEAN)
    - WithdrawnDate (DATETIME)
    - DataRetentionDays (INTEGER)

**DB-004**: The database shall maintain an index on (PackageName, Date) for AppUsages table to optimize common queries.

**DB-005**: The database shall use transactions for multi-record operations to ensure data consistency.

**DB-006**: The database shall enforce referential integrity through proper foreign key constraints where applicable.

**DB-007**: The database schema shall be created automatically on first application run using Entity Framework migrations.

**DB-008**: The database shall support concurrent read operations while ensuring write operation atomicity.

### 4.2 Legal and Regulatory Requirements

**LR-001: GDPR Compliance** The application shall comply with all applicable provisions of the General Data Protection Regulation (EU 2016/679), including:

- The app should comply with GDPR Article 6 (Lawfulness of processing) through explicit consent.
- The app should comply with GDPR Article 7 (Conditions for consent) with direct and understandable consent requests.
- The app should comply with GDPR Article 15 (Right of access) by displaying all stored user data.
- The app should comply with GDPR Article 17 (Right to erasure) through users ability to completely delete their data.
- The app should comply with GDPR Article 5 (Principles relating to processing) by prioritising data minimization and implementing storage limitation.
- The app should comply with Google Play Store policies regarding data collection disclosure
- The app should comply with Android permissions model and usage access guidelines
- The app should comply with accessibility standards (WCAG 2.1 Level AA minimum).

%% **LR-002: Privacy Notice** The application shall provide a privacy notice that includes:

- Identity of data controller
- Purpose of data processing
- Legal basis for processing (consent)
- Data retention period
- User rights (access, rectification, erasure, restriction)
- Contact information for privacy inquiries

**LR-003: Age Restrictions** The application shall be rated for users 18+ years of age in compliance with digital age of consent regulations.

**LR-004: Platform Store Compliance** The application shall comply with:

- Google Play Developer Policy (for Android distribution)
- Apple App Store Review Guidelines (for iOS distribution)
- Platform-specific privacy and data collection disclosure requirements

**LR-005: Accessibility Compliance** The application shall comply with:

- Web Content Accessibility Guidelines (WCAG) 2.1 Level AA
- Section 508 of the Rehabilitation Act (US)
- EN 301 549 (EU)

**LR-006: Data Protection Impact Assessment** A Data Protection Impact Assessment (DPIA) shall be conducted and documented before deployment to production.

**LR-007: Terms of Service** The application shall provide clear Terms of Service that include:

- Scope of service
- User responsibilities
- Limitations of liability
- Governing law and jurisdiction
- Dispute resolution process %%

### 4.3 Internationalization and Localization

**IL-001**: The initial version (v1.0) shall support English (en-US) language only.

**IL-002**: The application architecture shall support future localization through resource files and string externalization.

**IL-003**: All user-facing strings shall be stored in resource files (.resx) rather than hard-coded in source code.

**IL-004**: Date and time formats shall use culture-aware formatting (CultureInfo) to support future localization.

**IL-005**: Numeric formats (usage time, percentages) shall use culture-aware formatting.

**IL-006**: The UI layout shall accommodate text expansion of up to 40% for future translations.

**IL-007**: Icons and images shall be culture-neutral and avoid culture-specific symbols.

**IL-008**: Future versions should support:

- Spanish (es-ES, es-MX)
- German (de-DE)
- French (fr-FR)
- Italian (it-IT)
- Portuguese (pt-BR)
- Japanese (ja-JP)
- Chinese Simplified (zh-CN)

**IL-009**: Right-to-left (RTL) language support (Arabic, Hebrew) shall be considered in future versions but is not required for v1.0.

**IL-010**: Time zones shall be handled using UTC internally with conversion to local time for display.

### 4.4 Risk Management (FMEA Matrix)

| Risk ID | Failure Mode                        | Potential Effects                        | Severity (1-10) | Occurrence (1-10) | Detection (1-10) | RPN | Mitigation Strategy                                                         | Responsible Party   |
| ------- | ----------------------------------- | ---------------------------------------- | --------------- | ----------------- | ---------------- | --- | --------------------------------------------------------------------------- | ------------------- |
| R-001   | User denies usage access permission | No data collection possible              | 8               | 7                 | 2                | 112 | Clear UI explaining permission necessity; easy access to settings           | Development Team    |
| R-002   | User does not provide consent       | Cannot legally collect data              | 9               | 5                 | 1                | 45  | Clear, compelling privacy notice; transparent data practices                | UX Design / Legal   |
| R-003   | Database corruption                 | Data loss; app crashes                   | 9               | 2                 | 3                | 54  | Implement database integrity checks; backup mechanisms; recovery procedures | Development Team    |
| R-004   | Platform API failure                | Missing usage data                       | 6               | 3                 | 2                | 36  | Graceful error handling; retry logic; user notification                     | Development Team    |
| R-005   | Memory leak in long-running app     | App slowdown; device performance issues  | 7               | 4                 | 5                | 140 | Proper disposal patterns; memory profiling; automated testing               | QA Team             |
| R-006   | GDPR non-compliance                 | Legal liability; app removal from stores | 10              | 2                 | 4                | 80  | Legal review; compliance checklist; regular audits                          | Legal / Compliance  |
| R-007   | iOS functionality limitations       | Feature disparity; user confusion        | 6               | 8                 | 2                | 96  | Clear documentation of platform differences; alternative solutions          | Product Management  |
| R-008   | Database size growth                | Storage exhaustion; app crashes          | 7               | 6                 | 3                | 126 | Automatic data retention enforcement; user notifications                    | Development Team    |
| R-009   | Privacy policy changes              | Need to re-obtain consent                | 5               | 4                 | 1                | 20  | Consent versioning system; clear communication to users                     | Legal / Development |
| R-010   | Unauthorized data access            | Privacy breach                           | 10              | 1                 | 2                | 20  | Secure storage; permission enforcement; security audits                     | Security Team       |
| R-011   | App store rejection                 |                                          |                 |                   |                  |     |                                                                             |                     |