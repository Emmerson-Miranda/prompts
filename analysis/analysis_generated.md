# Requirements Analysis Document for Tic-Tac-Toe Web Application with Google Login

## **1. Document Control**

### 1.1. Document Information
- **Document Title**: Tic-Tac-Toe Web Application Requirements Analysis  
- **Version**: 1.0  
- **Date**: YYYY-MM-DD  
- **Authors**: [Your Name/Role]  
- **Reviewers/Approvers**: [Reviewer Name/Role]  

### 1.2. Revision History
| Version | Date       | Author(s)         | Description of Changes   | Reviewer(s)   |
|---------|------------|-------------------|---------------------------|---------------|
| 1.0     | YYYY-MM-DD | [Your Name]       | Initial draft             | [Reviewer]    |

### 1.3. Document Purpose
The purpose of this document is to define the formal and technical requirements for the development of a responsive, Google-login-based Tic-Tac-Toe web application. It ensures that stakeholders and developers have a shared understanding of the functional scope, non-functional properties, and expected outcomes. This application is intended as a casual game for entertainment, targeting global Google account users, starting with a focus on European users.

---

## **2. Executive Summary**

The Tic-Tac-Toe web application will allow users with Google accounts to play a single-player game for fun. The application will feature responsive design, accessible interfaces compatible with WCAG 2.2 Level A guidelines, and maintain a global leaderboard system. The application will collect minimal user data (name and country) during Google login and will initially target European users in its first stage. Future iterations will implement multiplayer features beyond the current scope.

---

## **3. Project Scope**

### 3.1. Goals
- Create an engaging and accessible Tic-Tac-Toe game that allows any Google user to play.  
- Focus on single-player functionality (local games).  
- Build a global leaderboard to encourage friendly competition across users.

### 3.2. In-Scope Features
- Google login functionality.  
- Single-player Tic-Tac-Toe gameplay.  
- Responsive design compatible with mobile and desktop.  
- A leaderboard displaying the top game scores with player names and countries.

### 3.3. Out-of-Scope Features
- Multiplayer features, such as player vs. player (random opponent) and user challenges.  
- Offline game functionality.  
- Advanced leaderboard features (e.g., filtering by friends or regions).  

### 3.4. Assumptions
- All users will have a valid Google account to log in.  
- Players will always be connected to the internet.  

### 3.5. Constraints
- Maximum expected concurrent users is 100 in the initial rollout.  
- Data privacy regulations (GDPR) must be adhered to for European users.  
- Application should be deployed on AWS infrastructure.

---

## **4. Stakeholder Analysis**

### 4.1. Stakeholder Identification
| Stakeholder Name/Group | Role/Responsibility                  | Involvement Level        |
|-------------------------|--------------------------------------|--------------------------|
| Google Account Users    | End users who play the application  | High                     |
| Product Owner           | Define requirements and priorities  | High                     |
| Development Team        | Build and deploy the application    | High                     |
| QA Team                 | Test functionality and quality      | Medium                   |
| AWS Provider            | Hosting and infrastructure support  | Medium                   |

### 4.2. Stakeholder Needs and Objectives
- **End Users**: Enjoyable gaming experience, minimal barriers to entry (Google login), and competitive leaderboards.  
- **Product Owner**: A scalable, maintainable application meeting accessibility standards.  
- **Development Team**: Clear requirements and a pipeline for ongoing updates.  
- **QA Team**: Defined acceptance criteria for functional and non-functional testing.  
- **AWS Provider**: Reliable hosting and support for scaling.  

---

## **5. Functional Requirements**

### 5.1. Use Cases/User Stories

#### Use Case 1: Google Login  
- **Actors**: End User, Google OAuth system.  
- **Preconditions**: User has a valid Google account.  
- **Triggers**: User clicks on "Login with Google."  
- **Main Flow**:
  1. Redirect user to Google OAuth endpoint.
  2. Authenticate user via Google.
  3. Collect user name and country (if accessible).
  4. Redirect back to the application dashboard.
- **Postconditions**: User is authenticated and can start the game.

#### Use Case 2: Play Tic-Tac-Toe  
- **Actors**: End User.  
- **Preconditions**: User is logged in.  
- **Main Flow**:
  1. User chooses to start a new game.
  2. User interacts with the Tic-Tac-Toe board to play.
  3. Application validates moves and checks for game completion.
  4. If the user wins, their score is incremented by 1.
- **Postconditions**: Game result is displayed; updated score is sent to the leaderboard.

#### Use Case 3: View Leaderboard  
- **Actors**: End User.  
- **Preconditions**: User is logged in.  
- **Main Flow**:
  1. User accesses the leaderboard from the main menu.
  2. Application retrieves and displays top scores (name, points, and country).

### 5.2. Functional Requirements List
| Requirement ID | Description                              | Priority (H/M/L) | Related Use Case(s) | Notes/Dependencies |
|-----------------|------------------------------------------|------------------|----------------------|--------------------|
| FR-01          | Enable Google login for users.           | High             | UC-01               | OAuth API          |
| FR-02          | Single-player Tic-Tac-Toe gameplay.      | High             | UC-02               |                    |
| FR-03          | Display global leaderboard.              | Medium           | UC-03               | Database updates   |

---

## **6. Non-Functional Requirements**

- **Performance**: Must support 100 concurrent users with low latency.  
- **Scalability**: Scalable within AWS infrastructure to support future features.  
- **Security**: User data collected must comply with GDPR.  
- **Accessibility**: Meet WCAG 2.2 Level A standards.  
- **Usability**: Intuitive design, optimized for responsive mobile and desktop use.  
- **Localization**: Display application text in the user’s default browser language.

---

## **7. Technical Requirements**

### 7.1. Architecture
- **Proposed Architecture**: Client-server architecture.  
  - **Frontend**: ReactJS.  
  - **Backend**: Java (Spring Boot).  
  - **Database**: PostgreSQL hosted on AWS RDS.  
- **Hosting**: AWS with CI/CD for automated updates.

### 7.2. Technology Stack
- **Frontend**: ReactJS.  
- **Backend**: Java/Spring Boot.  
- **Database**: PostgreSQL.  

### 7.3. Integration Requirements
- **Google OAuth**: For login and user info.  

### 7.4. Data Requirements
- User data: Name, Country.  
- Leaderboard data: Name, Points, and Country.

---

## **8. Risk Analysis**

| Risk ID | Risk Description                   | Probability (H/M/L) | Impact (H/M/L) | Mitigation Strategy         |
|---------|------------------------------------|---------------------|----------------|-----------------------------|
| R-01    | Privacy concerns with user data    | Medium              | High           | Implement GDPR compliance.  |
| R-02    | OAuth integration issues           | Low                 | High           | Test OAuth thoroughly.      |
| R-03    | Scalability for more users         | Medium              | Medium         | Use a scalable AWS setup.   |

---

## **9. Acceptance Criteria**
- Any European user can log in with a Google account.  
- Application displays text in the user’s language.  
- Users can successfully play Tic-Tac-Toe.  
- Users can see the leaderboard and navigate seamlessly back to the game page.  
- Completing a game increments their score on the leaderboard.

---

## **10. Glossary**
- **OAuth**: Open Authorization, a standard protocol for enabling secure login.  
- **WCAG**: Web Content Accessibility Guidelines.  
- **SSDL**: Secure Software Development Lifecycle.  

---

## **11. Appendices**
- None at this stage.

**End of Document**