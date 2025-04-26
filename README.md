# User Management System

![Project Banner](https://via.placeholder.com/1200x400?text=User+Management+System) <!-- Add your actual banner image -->

## Table of Contents
- [Project Overview](#project-overview)
- [Key Features](#key-features)
- [Technology Stack](#technology-stack)
- [Team Structure](#team-structure)
- [Installation Guide](#installation-guide)
- [API Documentation](#api-documentation)
- [Development Workflow](#development-workflow)
- [Testing](#testing)
- [License](#license)

## Project Overview

### Objective
A collaborative full-stack application built with Node.js/MySQL backend and Angular 17 frontend that implements secure authentication, role-based authorization, and complete CRUD operations for user management.

## Key Features

### Backend Features
- ✅ Secure email registration with verification
- 🔒 JWT authentication with refresh tokens
- 👥 Role-based authorization (Admin/User)
- 🔑 Password recovery system (forgot/reset)
- 🛠️ Comprehensive user management (CRUD)
- 📧 Nodemailer integration for email services

### Frontend Features
- ✍️ User registration with validation
- 🔐 JWT authenticated login/logout
- 👤 Profile management dashboard
- 🏛️ Administrative control panel
- 🧪 Fake backend for development/testing
- 🎨 Responsive UI design

## Technology Stack

### Backend
| Technology | Purpose |
|------------|---------|
| Node.js | Runtime environment |
| Express | Web application framework |
| MySQL | Relational database |
| JWT | Authentication tokens |
| Bcrypt | Password hashing |
| Nodemailer | Email services |

### Frontend
| Technology | Purpose |
|------------|---------|
| Angular 17 | Frontend framework |
| TypeScript | Primary language |
| RxJS | State management |
| Bootstrap | UI components |
| Font Awesome | Icons |

## Team Structure

| Role | Member | Responsibilities |
|------|--------|------------------|
| Group Leader | Felix Jr. Ragas | 
| Backend Developer | Jamaica Lapad |
| Backend Developer | Felix Jr. Ragas | 
| Frontend Developer | Jovan Gocela | 
| Frontend Developer | Recamel Flores | 
| Tester | Felix Jr. Ragas | 


## Installation Guide

### Prerequisites
- Node.js v16+
- MySQL v8.0+
- Angular CLI v17
- Git

### Backend Setup
1. Clone repository:
   ```bash
   git clone https://github.com/BrylDG/user-management-system.git
   cd backend
   
2. Install dependencies:
bash
npm install

3.Configure environment:
bash
cp .env.example .env

4.Database setup:
bash
npm run migrate

5.Start server:
bash
npm start

###Frontend Setup
1.Navigate to frontend:
bash
cd ../frontend

2.Install dependencies:
bash
npm install

3.Run development server:
bash
ng serve
Access at: http://localhost:4200   

## API Documentation

### Authentication

| Endpoint                   | Method | Parameters               | Description                     |
|----------------------------|--------|--------------------------|---------------------------------|
| `/accounts/register`       | POST   | `email`, `password`, `name` | Register new user               |
| `/accounts/verify-email`   | POST   | `token`                  | Verify email address            |
| `/accounts/authenticate`   | POST   | `email`, `password`      | User login                      |
| `/accounts/refresh-token`  | POST   | `refreshToken`           | Get new access token            |
| `/accounts/forgot-password`| POST   | `email`                  | Initiate password reset         |
| `/accounts/reset-password` | POST   | `token`, `newPassword`   | Complete password reset         |

### User Management

| Endpoint          | Method | Access        | Parameters          | Description            |
|-------------------|--------|---------------|---------------------|------------------------|
| `/accounts`       | GET    | Admin         | -                   | List all users         |
| `/accounts/{id}`  | GET    | Owner/Admin   | -                   | Get user details       |
| `/accounts/{id}`  | PUT    | Owner/Admin   | `name`, `email`, etc | Update user            |
| `/accounts/{id}`  | DELETE | Admin         | -                   | Delete user            |

## Fake Backend Implementation

For development and testing purposes, you can enable a fake backend that intercepts HTTP requests and returns simulated responses.

### Setup Instructions

1. Open `src/app/app.module.ts`
2. Add the fake backend provider:

```typescript
import { fakeBackendProvider } from './_helpers/fake-backend';

@NgModule({
  providers: [
    // Add this to your providers array
    fakeBackendProvider
  ]
})

### Testing the Fake Backend

1. Start the frontend development server:

bash
ng serve

2.The fake backend will now intercept API calls and return mock responses

###License
This project is licensed under the MIT License - see the LICENSE file for details.
