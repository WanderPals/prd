# Non-Functional Requirements

## Security, Privacy, and Data Retention Policies

### Applicable Laws and Regulations
1. **General Data Protection Regulation (GDPR):**
    - Applies to users in the European Union. Ensures that user data is handled with strict privacy and security measures.
2. **Children's Online Privacy Protection Act (COPPA):**
    - Ensures that any data collected from children under 13 is handled appropriately.

### Internal Policies
1. **Data Encryption:**
    - All sensitive data (personal information, payment details) must be encrypted both in transit and at rest.
2. **Access Control:**
    - Implement role-based access control (RBAC) to ensure that only authorized personnel have access to sensitive data.
3. **Regular Audits:**
    - Conduct regular security audits and vulnerability assessments to identify and mitigate risks.
4. **Data Minimization:**
    - Collect only the data necessary for the functionality of the app and avoid collecting excessive or irrelevant information.
5. **User Consent:**
    - Ensure explicit user consent is obtained before collecting or processing personal data.

### Privacy Features Needed from the Phone
1. **Location Services:**
    - Users must have the option to share their location in real-time during trips, but it should be easily toggleable to respect their privacy.
2. **Camera and Storage Access:**
    - For sharing photos and documents, with explicit permissions required to access these features.
3. **Notifications:**
    - Ensure users can control notification settings to avoid intrusive alerts.

## Adoption, Scalability, and Availability

### Traffic Patterns
1. **Steady Growth:**
    - Expect a gradual increase in user base as the app gains popularity.
2. **Seasonal Spikes:**
    - Anticipate higher traffic during peak travel seasons (summer vacations, holidays) and weekends.
3. **Event-based Bursts:**
    - Expect bursts of traffic when new features are launched or during promotional campaigns.

### Design Considerations for Bursty Traffic
1. **Elastic Scalability:**
    - Use cloud-based infrastructure (e.g., AWS, Google Cloud) that can automatically scale resources up or down based on traffic demands.
2. **Load Balancing:**
    - Implement load balancers to distribute traffic evenly across servers, ensuring no single server is overwhelmed.
3. **Caching:**
    - Use caching strategies (e.g., CDN, in-memory caches) to reduce load on the servers and improve response times for frequently accessed data.
4. **Asynchronous Processing:**
    - Offload time-consuming tasks (e.g., data analysis, notifications) to background processes to keep the main application responsive.
5. **Redundancy and Failover:**
    - Set up redundant servers and failover mechanisms to ensure high availability and minimize downtime in case of server failures.
