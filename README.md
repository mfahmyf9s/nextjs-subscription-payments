This starter kit provides a complete setup for high-performance SaaS applications, integrating user management, payment processing, and subscription handling.
Features

    Secure user management with Supabase
    Data access via PostgreSQL
    Stripe Checkout integration
    Automatic subscription status syncing through webhooks

View Demo
Architecture

Setup Instructions
Step 1: Deploy the Template

    Initiate Deployment
        Use the Vercel Deploy Button to create a new repository and set up a Supabase project.
        If automatic setup fails, create a Supabase account and a new project, then select the "Stripe Subscriptions" starter template in the SQL editor.

Step 2: Configure Authentication

    OAuth Setup
        Set up a GitHub OAuth app and configure Supabase to use it.
    Set Site URL
        In Supabase, navigate to auth > URL configuration and set your production URL (e.g., https://your-deployment-url.vercel.app).
    Vercel Environment Variables
        Add NEXT_PUBLIC_SITE_URL in Vercel settings.

Step 3: Database Initialization

    Run SQL Migrations
        If not set up automatically, navigate to the SQL Editor and execute the contents of the schema.sql file.

Step 4: Set Up Supabase Environment Variables

    Manual Setup
        Copy Supabase project API keys and URL into Vercel as NEXT_PUBLIC_SUPABASE_ANON_KEY, SUPABASE_SERVICE_ROLE_KEY, and NEXT_PUBLIC_SUPABASE_URL.

Step 5: Configure Stripe

    Create a Stripe Account
        Ensure "Test Mode" is enabled.
    Set Up Webhook
        Add an endpoint in Stripe for https://your-deployment-url.vercel.app/api/webhooks.
        Select all events to listen to and copy the signing secret for later use.

Step 6: Redeploy

    Redeploy your Vercel app to apply new environment variables.

Step 7: Create Products and Pricing

    Stripe Dashboard
        Create products and pricing plans as needed.
        Optionally, use fixtures to bootstrap test data using the Stripe CLI.

Step 8: Customer Portal Configuration

    Configure customer portal settings to allow customers to manage their subscriptions.

Step 9: Local Development

    Clone Repository
        Clone your GitHub repo locally.
    Install Dependencies
        Run pnpm install.
    Link Vercel Project
        Use Vercel CLI to link your project.

Step 10: Local Supabase Instance (Optional)

    Start Local Supabase
        Use Docker to run a local instance, and copy the necessary .env files.
    Link Local Database
        Use pnpm supabase:link to connect to your local database.

Step 11: Test Webhooks with Stripe CLI

    Log in to Stripe and start webhook forwarding to test locally.

Step 12: Run the Development Server

    Start your Next.js application with pnpm dev and navigate to http://localhost:3000.

Going Live

    Archive Test Products
        Archive all test mode products in Stripe.
    Configure Production Variables
        Switch to live mode in Stripe and update environment variables in Vercel.
    Redeploy
        Rebuild your application to apply changes.
    Verify Production Mode
        Test checkout with live mode Stripe keys to ensure everything is working.

Congratulations! You’re set to start earning recurring revenue! 🎉

Quick Deployment Guide for Next.js Subscription Payments Starter
Prerequisites

    Vercel Account
    Supabase Account
    Stripe Account

Deployment Steps
Step 1: Deploy on Vercel

    Click the Vercel Deploy Button to create a new repository with the template.
    Follow the prompts to set up a new Supabase project.

Step 2: Configure Authentication

    Set up a GitHub OAuth app.
    In Supabase, go to auth > URL configuration and set your production URL (e.g., https://your-deployment-url.vercel.app).
    In Vercel, add NEXT_PUBLIC_SITE_URL with the same URL.

Step 3: Initialize Database

    If not done automatically, navigate to the SQL Editor in Supabase and run schema.sql to initialize the database.

Step 4: Set Environment Variables

    Copy Supabase keys and URL:
        Add NEXT_PUBLIC_SUPABASE_ANON_KEY, SUPABASE_SERVICE_ROLE_KEY, and NEXT_PUBLIC_SUPABASE_URL to Vercel.

Step 5: Configure Stripe

    In Stripe, ensure Test Mode is enabled.
    Create a webhook endpoint: https://your-deployment-url.vercel.app/api/webhooks.
    Select all events to listen to and copy the signing secret.

Step 6: Redeploy Vercel

    Redeploy your application to apply the new environment variables.

Step 7: Create Products in Stripe

    Set up products and pricing in the Stripe Dashboard.

Step 8: (Optional) Configure Customer Portal

    Set up the customer portal to manage subscriptions.

Done!

Your subscription payments setup is now ready for use! 🎉