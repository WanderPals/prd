# Design and Implementation

## Frontend

### Key Libraries, Languages, and Components

#### Languages:
- **Kotlin**: Primary language for Android development.

#### Frameworks and Libraries:
- **Jetpack Compose**: Modern toolkit for building native UI.
- **Material Components for Android**: For implementing Material Design UI.
- **Android Jetpack Components**: For modern Android development.
  - **LiveData**: Observable data holder class.
  - **ViewModel**: Manages UI-related data in a lifecycle-conscious way.
  - **Navigation Component**: For handling navigation.
- **Retrofit**: HTTP client for making API requests.
- **Glide**: Image loading library.
- **Coroutines**: For asynchronous programming.
- **Hilt**: Dependency injection framework.
- **Google Maps and Places API**: For integrating location and place search functionalities.
- **Ktor**: For notifications. 

#### Components:
- **Activity**: Represents a single screen with a user interface.
- **Fragment**: A portion of UI within an Activity.
- **Composable Functions**: Used in Jetpack Compose for defining UI components.
- **ViewModel**: Manages UI-related data.
- **LiveData**: Handles data in a lifecycle-aware manner.

### Essential Screens

#### Home Screen:
- Welcome message.
- Buttons to create a new trip or view existing trips.

#### Trip List Screen:
- List of trips the user is part of, displayed using a RecyclerView or Jetpack Compose equivalent.
- Option to view trip details or create a new trip.

#### Trip Detail Screen:
- Detailed itinerary displayed using various Views (e.g., TextView, ImageView) or Composable functions.
- List of participants.
- Options to edit trip details (for owners/admins).

#### Trip Creation Screen:
- Form to enter trip details like destination, dates, and participants.
- Save and cancel buttons.

#### Profile Screen:
- User information (name, email).
- List of trips the user is involved in.
- Option to edit profile details.

#### Login/Signup Screen:
- Forms for user authentication.
- Switch between login and signup.

#### Dashboard Screen:
- Shows a resume of the other screens related to the trip.
- Central point of navigation of the App.

#### Suggestion Screen:
- List of all suggestions made by the member of the trip.
- Option to vote for a suggestion, comment on it, delete it or edit it.
- Option to create a new suggestion.

#### Suggestion Creation Screen:
- Form to enter suggestion details like title, description, address, dates and duration.
- Save and cancel buttons.

#### Agenda Screen:
- List all accepted suggestions in the form of an Agenda.
- Option to delete an accepted suggestion.

#### Finance Screen:
- List all expenses involved in the trip.
- Option to see the detail of an expense or create a new one.
- Option to settle debt between users.

#### Expense Creation Screen:
- Form to enter expense details like title, who paid, when and for who.
- Save and cancel buttons.

#### Map Screen:
- Display a Map centered around the destination of the trip.
- Option to pin location locally for later use, share real time location with others and create suggestion from pinned location.

#### Feed Screen:
- List all events that happened in the trip.
- Option to create Announcements to notify all user from a trip of something.

## Backend

1. **User Authentication and Management:**
    - **Components**: Registration, login, password recovery, multi-factor authentication.
    - **Description**: Handles user authentication, secure login processes, and user profile management.

2. **Trip Management System:**
    - **Components**: Trip creation, trip details management, itinerary planning.
    - **Description**: Manages the creation, updating, and deletion of trips. Facilitates itinerary and activity scheduling.

3. **Roles and Permissions:**
    - **Components**: Role assignment, permission management.
    - **Description**: Manages the assignment of different roles (Owner, Admin, Member, Viewer) and ensures appropriate access control.

4. **Activity Planning and Scheduling:**
    - **Components**: Activity suggestions, voting system, scheduling tools.
    - **Description**: Allows users to suggest, vote on, and schedule activities as part of the trip planning process.

5. **Notification System:**
    - **Components**: Real-time notifications, reminders, alerts.
    - **Description**: Sends notifications to users about updates, changes, and reminders related to their trips.

6. **Location Sharing System:**
    - **Components**: Real-time location updates, privacy controls.
    - **Description**: Enables real-time location sharing among trip participants with privacy settings.

7. **File Storage and Sharing:**
    - **Components**: Document upload, storage, sharing.
    - **Description**: Facilitates the storage and sharing of important trip-related documents like itineraries, tickets, and photos.

8. **Finance Management:**
    - **Components**: Expense tracking, cost splitting, budget management,currency management.
    - **Description**: Tracks expenses, splits costs among trip participants, and manages trip budgets.

9. **Activity Recommendations/Discoverability:**
    - **Components**: Activity suggestions, recommendation engine.
    - **Description**: Provides activity recommendations based on trip destination and user preferences.

## Data Model

*User Data:*
- Profile information (name, email, phone number, profile picture)
- Authentication credentials (hashed passwords)
- Role and permissions

*Trip Data:*
- Trip details (destination, dates, description)
- Itinerary and scheduled activities
- List of participants and their roles

*Activity Data:*
- Activity suggestions
- Votes and preferences

*Notification Data:*
- Notification messages
- Delivery status

*Location Data:*
- Real-time location coordinates
- Privacy settings

*File Data:*
- Uploaded documents (itineraries, tickets, photos)
- Access permissions

*Finance Data:*
- Expense records
- Cost splitting details
- Budget information

*Database Structure:*
- **Users Table**: Stores user profile information, authentication credentials, and roles.
- **Trips Table**: Contains trip details, including destination, dates, description, and associated participants.
- **Activities Table**: Holds information about suggested activities and votes.
- **Notifications Table**: Logs notification messages and delivery status.
- **Locations Table**: Tracks real-time location data with associated privacy settings.
- **Files Table**: Manages uploaded documents and their access permissions.
- **Finance Table**: Records expenses, cost splitting details, and budget information.

*Primary Storage:*
- **Database**: A relational database (e.g., PostgreSQL, MySQL) to store structured data such as user profiles, trip details, activities, notifications, and finance data.
- **File Storage**: A cloud storage service (e.g., AWS S3, Google Cloud Storage) to store documents and media files.

*Data Sharing:*
- **API Endpoints**: RESTful APIs to enable communication between the frontend and backend, facilitating data retrieval and updates.
- **Role-Based Access Control**: Ensures that data is shared based on user roles and permissions.

*Data Caching:*
- **In-Memory Caching**: Use of caching solutions (e.g., Redis, Memcached) to cache frequently accessed data and reduce database load.
- **Content Delivery Network (CDN)**: Distributes static files (documents, media) to improve access speed and reduce server load.

*Data Copying:*
- **Backup and Replication**: Regular backups and database replication to ensure data redundancy and disaster recovery.
- **Data Syncing**: Synchronization mechanisms to ensure data consistency across different components and services.


## Security Considerations

Ensuring the security of the WanderPals application is paramount. The following security considerations address potential risks and outline measures to protect user data, application integrity, and overall system security.

### Data Security

1. Encryption:

* Data in Transit: All data transmitted between the client and server is encrypted using TLS (Transport Layer Security) to prevent interception and tampering.
* Data at Rest: Sensitive data stored in databases is encrypted using AES (Advanced Encryption Standard) with a 256-bit key to protect against unauthorized access.

2. Authentication and Authorization:

* User Authentication: Implementing robust authentication mechanisms such as OAuth 2.0, enabling secure third-party authentication providers (e.g., Google, Facebook).
* Multi-Factor Authentication (MFA): Encouraging the use of MFA for an added layer of security.
* Role-Based Access Control (RBAC): Utilizing RBAC to ensure that users only have access to functionalities and data necessary for their role.

3. Secure APIs:

* API Security: Securing APIs with proper authentication and authorization mechanisms. Using API gateways to manage and monitor API traffic, enforce rate limiting, and prevent abuse.
* Input Validation: Ensuring all inputs are validated and sanitized to protect against injection attacks such as SQL injection, XSS (Cross-Site Scripting), and CSRF (Cross-Site Request Forgery).

### Application Security

1. Secure Coding Practices:

* Code Reviews: Conducting regular code reviews to identify and rectify security vulnerabilities.
* Static Analysis: Using static analysis tools to detect potential security flaws during the development phase.

2. Dependency Management:

* Vulnerability Scanning: Regularly scanning third-party libraries and dependencies for known vulnerabilities and applying patches promptly.
* Minimal Permissions: Granting the minimal required permissions to all third-party libraries and services.

3. Security Testing:

* Penetration Testing: Conducting periodic penetration tests to identify and mitigate vulnerabilities.
* Automated Security Testing: Integrating automated security testing tools in the CI/CD pipeline to detect vulnerabilities early in the development process.

### Network Security

1. Firewalls and Intrusion Detection:

* Network Firewalls: Implementing network firewalls to filter incoming and outgoing traffic based on predetermined security rules.
* Intrusion Detection Systems (IDS): Using IDS to monitor network traffic for suspicious activities and potential threats.

2. Secure Configurations:

* Least Privilege Principle: Applying the principle of least privilege to all network services and components.
* Configuration Management: Ensuring secure configurations for all servers, databases, and network devices, and regularly auditing configurations for compliance.

### Incident Response and Monitoring

1. Logging and Monitoring:

* Comprehensive Logging: Implementing comprehensive logging of all user activities, system events, and security-related incidents.
* Real-Time Monitoring: Using real-time monitoring tools to detect and respond to security incidents promptly.

2. Incident Response Plan:

* Preparation: Developing and maintaining an incident response plan outlining procedures for detecting, responding to, and recovering from security incidents.
* Training: Regularly training the development and operations teams on incident response protocols and best practices.

### Privacy and Compliance

1. Data Privacy:

* User Consent: Ensuring user consent for data collection, processing, and storage, in compliance with data protection regulations.
* Data Minimization: Collecting only the necessary data required for the application’s functionality.

2. Regulatory Compliance:

* GDPR and CCPA: Ensuring compliance with data protection regulations such as GDPR (General Data Protection Regulation) and CCPA (California Consumer Privacy Act).
* Periodic Audits: Conducting periodic security audits and assessments to ensure ongoing compliance with relevant regulations and standards.

By addressing these security considerations, WanderPals aims to create a secure and trustworthy environment for its users, protecting their data and ensuring the integrity and availability of the application.

## Infrastructure and Deployment

### Deployment Strategy

The application is deployed on smartphones via standard app distribution platforms such as Google Play Store. Before full deployment, beta testing is conducted by releasing a pre-release version to a limited group of users to gather feedback on usability and functionality.

### Development Environment

The application development process leverages a blend of frontend and backend technologies. Android Studio serves as the primary IDE for developing the Android application, ensuring an integrated development environment tailored for efficient coding and debugging.

### Infrastructure Requirements

To support development and deployment, the following infrastructure is required:

1. Cloud Services: Utilizing AWS, Google Firebase, or Azure for backend services, including authentication, database management, storage, and analytics.
2. Version Control: Using GitHub for version control and collaboration.
3. CI/CD Tools: Employing CI/CD tools to manage automated builds, tests, and deployments.
4. Virtualization: Running tests in production-like environments using virtualization tools or containers to replicate production configurations and ensure accurate testing.
5. Communication and Project Management: Using tools like Slack and Trello for team communication and project management.

### Special Infrastructure Considerations

* Elastic Scalability: Implementing cloud-based infrastructure that can automatically scale resources based on traffic demands.
* Load Balancing: Using load balancers to distribute traffic evenly across servers to prevent any single server from becoming overwhelmed.
* Caching: Employing caching strategies such as CDNs and in-memory caches to reduce server load and improve response times.

This comprehensive infrastructure and deployment strategy ensures the application is developed, tested, and deployed efficiently, maintaining high standards of quality and performance.

## Test Plan

The application is developed using a combination of frontend and backend technologies. It undergoes rigorous testing, including unit tests, integration tests, and end-to-end tests, to ensure functionality and reliability. Continuous Integration (CI) and Continuous Deployment (CD) pipelines are utilized to automate testing and deployment processes.

- **Configuring Tests in the Build Process**: Integrate test execution into the build process with Gradle. Configure build steps to automatically execute both unit and integration tests during deployment.

- **Using Gradle to Run Tests**: Configure Gradle tasks to run tests. Leverage Gradle plugins, such as the 'java' plugin, to automate test execution as part of the deployment process.

- **Continuous Integration (CI) and Continuous Deployment (CD)**: Automate test execution within a CI/CD pipeline. Set up triggers to run tests whenever new code is validated, and integrate test results seamlessly into the deployment process.
  
- **Writing Unit and Integration Tests**: Utilize testing frameworks : JUnit for backend unit tests and Kaspresso for Android UI tests. Additionally, write integration tests to validate interactions between various components.
  
- **Regression Testing**: Conduct regression tests to ensure that new updates or changes do not negatively impact existing functionality. Automate regression tests where possible to streamline the testing process.
  
- **End-to-End Testing**: Perform end-to-end tests to validate real-world application behavior. Tools like Espresso for Android testing can simulate user interactions and verify UI functionality.

- **Using Mockito for Mock Testing**: Employ Mockito, a Java library, to create mock objects that simulate external dependencies. This isolation technique aids in unit testing by ensuring that each component behaves as expected in isolation.

- **Beta Testing**: Prior to full deployment, conduct beta testing by releasing a pre-release version of the application to a limited group of users or a closed user group. Collect feedback from beta testers regarding usability, functionality, and any issues encountered.

- **Testing on Production-Like Environments**: Validate test reliability by running tests in environments resembling production. Utilize virtualization tools or containers to replicate production configurations and ensure accurate testing.


