# API-Gateway
Finatic Labs API Gateway code


# Project Setup and Data Flow
Below is the summary of the data flow and the steps to get the project up and running.

## Data Flow Summary

1. **Frontend (React)** sends a request to the backend at: http://127.0.0.1:8000/backend/get-data/
   This is the backend server.

2. **Backend Server** sends a request to the API Gateway at: http://127.0.0.1:8000/api/fetch-data/
   This is the API gateway.
   

3. **API Gateway** sends a request to the Database API at: http://127.0.0.1:8000/database/get-data/


4. **Database API** fetches the data from **Supabase** and returns it to the API Gateway.

5. **API Gateway** sends the fetched data back to the **Backend Server**.

6. **Backend Server** sends the data to the **Frontend (React)** as a JSON response.

## How to Run the Project

To run the project locally, follow these steps. You'll need to open **three terminals** and activate the environment in all of them.

### Terminal 1: Power up the React Frontend

1. Navigate to the React frontend directory:
```bash
cd nbfc-client
```
2. Start the React development server:
```
npm start
```

### Terminal 2: Run Django Backend & API Gateway

1. Navigate to the Django backend directory:
```
cd nbfc_report
```

2. Run the Django development server:
```
python manage.py runserver
```

### Terminal 3: Run DB Shell (For Database Queries)
1. Navigate to the Django backend directory
```
cd nbfc_report
```

2. Open the Django database shell:
```
python manage.py dbshell
```

3. Once in the database shell, try running a sample query like:
```
select * from users;
```
This will verify that the database connection is working correctly.
