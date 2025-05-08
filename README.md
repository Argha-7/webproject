# Free Fire Tournament Website

A comprehensive Free Fire tournament management platform designed to streamline competitive gaming experiences. The application provides robust tournament organization, user management, and transaction capabilities with integrated payment solutions.

## Key Features

- Tournament management with filtering and searching
- Registration system with Free Fire ID integration
- Wallet-based payment system with conditional entry
- Win proof submission and verification
- User profile and dashboard
- Admin panel with analytics
- Transaction history and wallet management

## Technologies Used

- **Frontend**: React, TypeScript, Shadcn UI, TailwindCSS
- **Backend**: Node.js, Express
- **Database**: PostgreSQL
- **ORM**: Drizzle ORM
- **Form Validation**: Zod
- **API Calls**: Tanstack Query
- **Authentication**: Passport.js

## Deployment Instructions for Render.com

### Prerequisites

1. Create an account on [Render.com](https://render.com)
2. Create a PostgreSQL database on Render or use an external database service like Neon

### Step 1: Clone and Prepare the Repository

1. Clone this repository to your local machine or directly connect your GitHub repository to Render.com

### Step 2: Set Up PostgreSQL Database

1. Create a PostgreSQL database on Render.com or use a service like Neon, ElephantSQL, etc.
2. Copy your database connection string, you'll need it for the environment variables

### Step 3: Deploy on Render.com

#### Option 1: Using the Render Dashboard

1. Log in to your Render.com account
2. Select "New Web Service"
3. Connect your GitHub repository
4. Configure the service:
   - **Name**: Choose a name for your service
   - **Runtime**: Node
   - **Build Command**: `npm install && npm run build`
   - **Start Command**: `npm start`
5. Add environment variables:
   - `NODE_ENV`: `production`
   - `DATABASE_URL`: Your PostgreSQL connection string
   - `SESSION_SECRET`: A secure random string
   - `STRIPE_SECRET_KEY`: Your Stripe secret key (if using Stripe)
   - `VITE_STRIPE_PUBLIC_KEY`: Your Stripe public key (if using Stripe)
6. Click "Create Web Service"

#### Option 2: Using a Blueprint

1. Render.com supports deployment from a blueprint file. This repository includes a `render.yaml` file.
2. In your Render dashboard, go to "Blueprints"
3. Connect your repository
4. Render will detect the `render.yaml` file and create the services defined in it
5. You'll still need to set up the environment variables in the dashboard after deployment

### Step 4: Database Migration

Once the service is deployed, you need to run database migrations:

1. In your Render.com dashboard, select your web service
2. Go to "Shell"
3. Run `npm run db:push` to create the database schema
4. Run `npm run db:seed` to seed initial data (optional)

### Step 5: Verify Deployment

1. Your application should now be accessible at the URL provided by Render.com
2. Verify that all features are working correctly

## Local Development

### Setup

1. Clone the repository
2. Copy `.env.example` to `.env` and fill in the environment variables
3. Install dependencies: `npm install`
4. Run database migrations: `npm run db:push`
5. Seed database (optional): `npm run db:seed`
6. Start the development server: `npm run dev`

### Build for Production

1. Run: `npm run build`
2. The production build will be available in the `dist` directory

## Environment Variables

- `DATABASE_URL`: PostgreSQL connection string
- `SESSION_SECRET`: Secret for session cookie encryption
- `STRIPE_SECRET_KEY`: Stripe secret key (optional)
- `VITE_STRIPE_PUBLIC_KEY`: Stripe public key (optional)