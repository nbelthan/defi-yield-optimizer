# Vercel Deployment Guide for DeFi Yield Optimizer

This guide will walk you through deploying the DeFi Yield Optimizer application to Vercel.

## Prerequisites

1. A GitHub account
2. A Vercel account (you can sign up for free at https://vercel.com using your GitHub account)

## Step 1: Prepare Your Repository

1. Create a new GitHub repository
2. Upload the application files to your repository
   - You can do this by cloning the repository locally, copying the files, and pushing them
   - Or by using GitHub's web interface to upload the files directly

## Step 2: Deploy to Vercel

1. Log in to your Vercel account at https://vercel.com
2. Click on "Add New..." and select "Project"
3. Import your GitHub repository
   - You may need to install the Vercel GitHub app if you haven't already
   - Select the repository you created in Step 1
4. Configure your project:
   - Framework Preset: Vite
   - Build Command: `pnpm install && pnpm run build` (this should be auto-detected)
   - Output Directory: `dist` (this should be auto-detected)
   - Install Command: `pnpm install` (this should be auto-detected)
5. Environment Variables:
   - Add the following environment variables:
     - Name: `VITE_DEEPSEEK_API_KEY`
     - Value: `sk-8c2cf3f9013a49cab08fa296ae4df9d5`
   - (Optional) Add another environment variable:
     - Name: `VITE_API_BASE_URL`
     - Value: `https://api.llama.fi`
6. Click "Deploy"

Vercel will now build and deploy your application. Once the deployment is complete, you'll be provided with a URL where your application is hosted (e.g., https://defi-yield-optimizer.vercel.app).

## Step 3: Verify Deployment

1. Visit the provided URL to ensure your application is working correctly
2. Test the main features:
   - Filtering options
   - Risk assessment
   - LLM-generated explanations
   - Dark/light mode toggle

## Troubleshooting

If you encounter any issues during deployment:

1. Check the build logs in Vercel for any errors
2. Ensure all environment variables are correctly set
3. Verify that the vercel.json file is properly configured
4. If CORS issues occur, you may need to add appropriate headers in the vercel.json file

## Updating Your Application

To update your application after making changes:

1. Push the changes to your GitHub repository
2. Vercel will automatically detect the changes and redeploy your application

## Custom Domain (Optional)

If you want to use a custom domain:

1. Go to your project settings in Vercel
2. Navigate to the "Domains" section
3. Add your custom domain and follow the instructions to configure DNS settings
