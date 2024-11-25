# Voting-Application-Overview
A secure and role-based voting system built using JavaScript and Node.js with Express for backend routing, MongoDB as the database, and Mongoose for object data modeling. It includes middleware for authentication and validation, ensuring a seamless and secure user experience.


# Voting Application

A secure and user-friendly voting application that allows users to register, view candidates, cast votes, and check live vote counts. The application implements role-based access control to ensure the integrity of the voting process, with specific features for users and administrators.

---

## Key Features

### 1. User Authentication
- **Sign-Up (`POST /signup`)**: Create a new account using a unique Aadhaar card number and password.
- **Log-In (`POST /login`)**: Log in using Aadhaar card number and password for authentication.

### 2. Voting
- **Candidate List (`GET /candidates`)**: View a list of available candidates.
- **Cast Vote (`POST /vote/:candidateId`)**: Vote for a specific candidate. A user can vote only once.
- **Live Vote Counts (`GET /vote/counts`)**: View real-time vote counts for all candidates, sorted in descending order by vote count.

### 3. User Profile Management
- **Profile Information (`GET /profile`)**: Access the user's profile details.
- **Change Password (`PUT /profile/password`)**: Update the user's password securely.

### 4. Admin Management
The admin role is restricted to managing the candidate list and is prohibited from voting.
- **Create Candidate (`POST /candidates`)**: Add a new candidate to the list.
- **Update Candidate (`PUT /candidates/:candidateId`)**: Modify details of an existing candidate.
- **Delete Candidate (`DELETE /candidates/:candidateId`)**: Remove a candidate from the list.

### 5. Security Features
- Each user is identified by a unique government-issued Aadhaar card number.
- Passwords are securely stored and can be updated through a protected route.
- Role-based access control ensures that users and admins have specific, non-overlapping permissions.

---

## Roles and Permissions

### User:
- Register and log in using Aadhaar card number and password.
- View the candidate list and cast one vote.
- Change their password.
- Cannot vote more than once.

### Admin:
- Manage the candidate list (create, update, delete candidates).
- Cannot vote.

---

## API Endpoints

### User Authentication
| Method | Endpoint       | Description                     |
|--------|----------------|---------------------------------|
| POST   | `/signup`      | Register a new user account.   |
| POST   | `/login`       | Log in with Aadhaar and password.|

### Voting
| Method | Endpoint                  | Description                           |
|--------|---------------------------|---------------------------------------|
| GET    | `/candidates`             | Retrieve the list of candidates.     |
| POST   | `/vote/:candidateId`      | Submit a vote for a specific candidate.|

### Vote Counts
| Method | Endpoint                  | Description                                 |
|--------|---------------------------|---------------------------------------------|
| GET    | `/vote/counts`            | Get live vote counts sorted by vote count. |

### User Profile
| Method | Endpoint                  | Description                      |
|--------|---------------------------|----------------------------------|
| GET    | `/profile`                | Access user's profile details.  |
| PUT    | `/profile/password`       | Update the user's password.     |

### Admin Candidate Management
| Method | Endpoint                  | Description                           |
|--------|---------------------------|---------------------------------------|
| POST   | `/candidates`             | Add a new candidate.                 |
| PUT    | `/candidates/:candidateId`| Edit details of an existing candidate.|
| DELETE | `/candidates/:candidateId`| Remove a candidate from the list.    |

---

## Application Workflow

1. **User Registration and Authentication**:
   - New users sign up with their Aadhaar card number and password.
   - Registered users log in with their Aadhaar card number and password.

2. **Voting Process**:
   - Authenticated users view the list of candidates.
   - Users can cast one vote for their preferred candidate.

3. **Live Vote Counts**:
   - Users can check live vote counts sorted by the number of votes.

4. **Admin Role**:
   - Admins can manage the candidate list but cannot vote.

5. **Security**:
   - Aadhaar card number ensures unique identification for each user.
   - Passwords are securely managed and can be updated as needed.

---

## Tech Stack

- **Backend**: Node.js/Express (or similar)
- **Database**: MongoDB/MySQL (or similar)
- **Authentication**: Aadhaar-based unique identification and role-based access control
- **Frontend**: React/Angular/Vue (or similar)

---

## How to Run the Application

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/voting-application.git
