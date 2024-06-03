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

