# Book Store Application

## Overview
The Book Store application is an online book selling platform designed to provide users with a seamless experience for purchasing books from various categories and vendors. The project aims to enhance user experience, improve shipping efficiency, and ensure system reliability. Key features include a Split Payment Option, AI-driven customer support, and machine learning for demand prediction.

## System Requirements
### Hardware
- Minimum: 4GB RAM, 2-core CPU, 10GB free disk space
- Recommended: 8GB RAM, 4-core CPU, 20GB free disk space

### Software
- **Operating System**: Windows 10/11, macOS, or Linux
- **Backend**: .NET Core 6.0 or higher
- **Frontend**: Node.js (v16 or higher), npm
- **Database**: Microsoft SQL Server 2019 or higher
- **Browser**: Chrome, Firefox, or Edge (latest versions)
- **Tools**: Git, Docker (optional for containerization), Visual Studio 2022 or VS Code

## Installation Steps
1. **Clone the Repository**
   ```bash
   git clone [Insert Repository Link]
   cd bookstore
   ```

2. **Set Up the Backend**
   - Navigate to the backend directory: `cd backend`
   - Restore .NET dependencies: `dotnet restore`
   - Update the database connection string in `appsettings.json` (see Configuration section)
   - Apply database migrations: `dotnet ef database update`

3. **Set Up the Frontend**
   - Navigate to the frontend directory: `cd frontend`
   - Install dependencies: `npm install`
   - Build the frontend: `npm run build`

4. **Set Up the Database**
   - Ensure SQL Server is running
   - Create a database named `BookStoreDB`
   - Run the provided SQL scripts in `database/scripts` to set up tables and seed data

5. **(Optional) Set Up Docker**
   - Ensure Docker is installed
   - Build and run the application: `docker-compose up --build`

## Configuration
1. **Backend Configuration**
   - Edit `appsettings.json` in the backend directory:
     ```json
     {
       "ConnectionStrings": {
         "DefaultConnection": "Server=localhost;Database=BookStoreDB;Trusted_Connection=True;"
       },
       "Jwt": {
         "Key": "[Your-Secret-Key]",
         "Issuer": "BookStoreAPI",
         "Audience": "BookStoreUsers"
       }
     }
     ```
   - Replace `[Your-Secret-Key]` with a secure key for JWT authentication

2. **Frontend Configuration**
   - Edit `frontend/.env`:
     ```env
     REACT_APP_API_URL=http://localhost:5000/api
     ```
   - Update the API URL if the backend is hosted elsewhere

3. **Third-Party Services**
   - Configure API keys for payment gateways (Stripe/PayPal), Map Integration, and notification services (SendGrid/Twilio) in `appsettings.json` or environment variables

## Execution Guide
1. **Run the Backend**
   - Navigate to the backend directory: `cd backend`
   - Start the server: `dotnet run`
   - The API will be available at `http://localhost:5000`

2. **Run the Frontend**
   - Navigate to the frontend directory: `cd frontend`
   - Start the development server: `npm start`
   - The application will be available at `http://localhost:3000`

3. **Access the Deployed Version**
   - If deployed, access the web application at: [Insert Deployment Link]

4. **Run Tests**
   - Backend unit tests: `dotnet test` (uses NUnit/XUnit)
   - Frontend tests: `npm test`
   - API tests: Import the Postman collection from `docs/postman_collection.json`

## API Documentation
The API is documented using Swagger (OpenAPI). To access:
1. Start the backend server
2. Navigate to `http://localhost:5000/swagger`
3. Key endpoints include:
   - `/api/auth/register`: Register a new user
   - `/api/auth/login`: Authenticate a user
   - `/api/orders`: Place or retrieve orders
   - `/api/vendors`: Manage vendor profiles
   - `/api/shipping`: Manage shipping tasks

Detailed endpoint descriptions and request/response schemas are available in the Swagger UI.

## Project Structure
```
bookstore/
├── backend/                  # .NET Core Web API
├── frontend/                 # React.js frontend
├── database/                 # SQL scripts and schema
├── docs/                     # API documentation and Postman collection
├── tests/                    # Unit and integration tests
└── docker-compose.yml        # Docker configuration
```

## Contributing
- Follow the GitFlow branching strategy (main, develop, feature/*, bugfix/*)
- Submit pull requests with detailed descriptions
- Adhere to .NET and JavaScript coding standards

## License
This project is licensed under the MIT License.

## Contact
For issues or inquiries, contact the project team:
- Mustafa Amr Ibrahim
- Shahd Ahmed Arafa
- Rahma Nasr
- Youssef Mohamed Zanaty
- Ahmed Khaled