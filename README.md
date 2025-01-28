# Secret Keeper App 🔐

A secure web application that allows users to register, log in, and submit secrets anonymously or through their authenticated accounts. The app supports local authentication as well as Google OAuth 2.0 for seamless login. Secrets are stored securely in a PostgreSQL database.

## Features ✨

- **User Authentication**: Register and log in securely using email/password or Google OAuth.
- **Password Hashing**: Passwords are hashed using bcrypt for added security.
- **PostgreSQL Integration**: Secrets and user data are stored in a relational database.
- **Session Management**: Maintains user sessions using `express-session`.
- **Google OAuth 2.0**: Login with Google credentials.
- **Dynamic Routes**: Access secrets and submit new ones dynamically.
- **Secure Secret Submission**: Allows users to store their secrets privately in the database.

## Technologies Used 🛠️

- **Node.js**: Backend runtime environment.
- **Express.js**: Web application framework for routing and middleware.
- **PostgreSQL**: Database to store user and secret information.
- **Passport.js**: Authentication middleware for local and Google OAuth.
- **bcrypt**: Secure password hashing.
- **Multer**: File upload handling (if needed in future expansions).
- **dotenv**: For managing environment variables securely.

## Installation and Setup ⚙️

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/secret-keeper-app.git
   ```
2. Navigate to the project directory:
   ```bash
   cd secret-keeper-app
   ```
3. Install dependencies:
   ```bash
   npm install
   ```
4. Create a `.env` file in the root directory and add the following environment variables:
   ```env
   PG_USER=your_postgres_user
   PG_HOST=your_postgres_host
   PG_DATABASE=your_database_name
   PG_PASSWORD=your_postgres_password
   PG_PORT=your_postgres_port
   SESSION_SECRET=your_session_secret
   GOOGLE_CLIENT_ID=your_google_client_id
   GOOGLE_CLIENT_SECRET=your_google_client_secret
   ```
5. Start the PostgreSQL database and ensure the required `users` table exists:
   ```sql
   CREATE TABLE users (
     id SERIAL PRIMARY KEY,
     email VARCHAR(255) UNIQUE NOT NULL,
     password VARCHAR(255),
     secret TEXT
   );
   ```
6. Start the server:
   ```bash
   node app.js
   ```
7. Open your browser and visit: `http://localhost:3000`


## How It Works 🔍

1. **Register**: Users can create an account using their email and password.
2. **Log In**: Authenticate using email/password or Google OAuth.
3. **Submit Secrets**: Authenticated users can submit their secrets, which are stored in the database.
4. **View Secrets**: Users can view their secrets after logging in.

## Routes 🛣️

- `GET /`: Home page
- `GET /register`: Registration page
- `POST /register`: Handles new user registration
- `GET /login`: Login page
- `POST /login`: Handles user login
- `GET /logout`: Logs out the user
- `GET /secrets`: Displays secrets for authenticated users
- `GET /submit`: Secret submission page (requires authentication)
- `POST /submit`: Handles secret submissions
- `GET /auth/google`: Initiates Google OAuth login
- `GET /auth/google/secrets`: Redirects after Google login

## Future Enhancements 🔮

- Add email verification for registration.
- Support for uploading profile pictures.
- Enhanced UI/UX with modern design frameworks.

## Acknowledgments 🙌

Inspired by the concept of anonymously sharing secrets while prioritizing user privacy and security.

---

Happy coding! ✨
