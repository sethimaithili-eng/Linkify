# Linkify
This backend API is developed using Node.js and Express.js, with MongoDB as the database. It enables contact management features such as creating contacts and intelligently merging them based on matching email addresses and phone numbers.
# Features
- Save and manage contact information using MongoDB.
- Automatically merge contacts when email addresses or phone numbers match.
- Fetch and view all stored contacts from the database.
# Tech Stack
- Node.js
- Express.js
- MongoDB with Mongoose ORM
- Render for application deployment
# Setup Instructions
- # Prerequisites
- Node.js installed (v14+ recommended)
- MongoDB Atlas or a local MongoDB instance
# Installation
1. Clone the repository
```bash
git clone https://github.com/sethimaithili-eng/Linkify.git
cd Linkify
```

2. Install dependencies
```bash
npm install
```

3. Create a `.env` file in the root directory and configure the environment variables
```env
MONGO_URI=your_mongodb_connection_string
PORT=10000
```
4. Start the server:
```bash
node index.js
```
## API Endpoints

### **1. Identify Contact (POST /identify)**
**Endpoint:**
```
POST /identify
```
**Description:**
- Accepts an email and/or phone number to create or merge contacts.

**Request Body:**
```json
{
  "name": "Rahul Verma",
  "email": "rahul.verma@gmail.com",
  "phone": "+919812345678"
}
```
**Response:**
```json
{
  "_id": "65c91a8e42d1bc0098fa1234",
  "name": ["Rahul Verma"],
  "emails": ["rahul.verma@gmail.com"],
  "phoneNumbers": ["+919812345678"],
  "secondaryContactIds": [],
  "updatedAt": "2025-04-01T08:15:30.000Z",
  "createdAt": "2025-04-01T08:15:30.000Z",
  "__v": 0
}
```
### **2. Get All Contacts (GET /identify)**
**Endpoint:**
```
GET /identify
```
**Description:**
- Retrieves all stored contacts from the database.

