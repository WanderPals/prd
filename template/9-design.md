# Design and Implementation

## Frontend


## Backend

**Decompose the MVP into Functional Blocks:**

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

**What Data Are You Collecting/Managing?**

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

**How Is It Organised?**

*Database Structure:*
- **Users Table**: Stores user profile information, authentication credentials, and roles.
- **Trips Table**: Contains trip details, including destination, dates, description, and associated participants.
- **Activities Table**: Holds information about suggested activities and votes.
- **Notifications Table**: Logs notification messages and delivery status.
- **Locations Table**: Tracks real-time location data with associated privacy settings.
- **Files Table**: Manages uploaded documents and their access permissions.
- **Finance Table**: Records expenses, cost splitting details, and budget information.

**Where Is It Stored?**

*Primary Storage:*
- **Database**: A relational database (e.g., PostgreSQL, MySQL) to store structured data such as user profiles, trip details, activities, notifications, and finance data.
- **File Storage**: A cloud storage service (e.g., AWS S3, Google Cloud Storage) to store documents and media files.

**How Is It Shared/Copied/Cached?**

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

## Infrastructure and Deployment

*How is the application developed, tested and deployed?*

*Any special infrastructure requirements.*


## Test Plan

*How is the application developed, tested and deployed?*

*Any special infrastructure requirements.*


The application is developed using a combination of frontend and backend technologies. It undergoes rigorous testing, including unit tests, integration tests, and end-to-end tests, to ensure functionality and reliability. Continuous Integration (CI) and Continuous Deployment (CD) pipelines are utilized to automate testing and deployment processes. The application is deployed on smartphones via standard app distribution platforms such as Google Play Store.

- **Configuring Tests in the Build Process**: Integrate test execution into the build process with Gradle. Configure build steps to automatically execute both unit and integration tests during deployment.

- **Using Gradle to Run Tests**: Configure Gradle tasks to run tests. Leverage Gradle plugins, such as the 'java' plugin, to automate test execution as part of the deployment process.

- **Continuous Integration (CI) and Continuous Deployment (CD)**: Automate test execution within a CI/CD pipeline. Set up triggers to run tests whenever new code is validated, and integrate test results seamlessly into the deployment process.
  
- **Writing Unit and Integration Tests**: Utilize testing frameworks : JUnit for backend unit tests and Kaspresso for Android UI tests. Additionally, write integration tests to validate interactions between various components.
  
- **Regression Testing**: Conduct regression tests to ensure that new updates or changes do not negatively impact existing functionality. Automate regression tests where possible to streamline the testing process.
  
- **End-to-End Testing**: Perform end-to-end tests to validate real-world application behavior. Tools like Espresso for Android testing can simulate user interactions and verify UI functionality.

- **Using Mockito for Mock Testing**: Employ Mockito, a Java library, to create mock objects that simulate external dependencies. This isolation technique aids in unit testing by ensuring that each component behaves as expected in isolation.

- **Beta Testing**: Prior to full deployment, conduct beta testing by releasing a pre-release version of the application to a limited group of users or a closed user group. Collect feedback from beta testers regarding usability, functionality, and any issues encountered.

- **Testing on Production-Like Environments**: Validate test reliability by running tests in environments resembling production. Utilize virtualization tools or containers to replicate production configurations and ensure accurate testing.


