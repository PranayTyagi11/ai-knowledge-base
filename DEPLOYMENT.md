# Deployment Guide

## Backend Deployment (Railway)

### Prerequisites
- Railway account
- Supabase database
- AWS S3 bucket
- Cohere API account

### Environment Variables
- SUPABASE_URL=your_supabase_url
- SUPABASE_KEY=your_supabase_key
- AWS_ACCESS_KEY_ID=your_aws_key
- AWS_SECRET_ACCESS_KEY=your_aws_secret
- S3_BUCKET_NAME=your_bucket_name
- COHERE_API_KEY=your_cohere_key
- AWS_REGION=your_aws_region

### Deployment Steps
1. Connect GitHub repository to Railway
2. Set root directory to backend folder
3. Configure environment variables
4. Deploy automatically on git push

## Frontend Deployment (Netlify)

### Build Configuration
- **Build Command**: `npm run build`
- **Publish Directory**: `dist`
- **Environment**: Set backend URL in build process

### Deployment Steps
1. Build project: `npm run build`
2. Drag dist folder to Netlify
3. Configure domain and SSL settings

## Infrastructure Setup

### AWS S3 Configuration
1. Create S3 bucket with private access
2. Configure CORS policies for web access
3. Set up IAM user with S3 permissions
4. Generate access keys for application use

### Supabase Setup
1. Create new project
2. Enable pgvector extension
3. Run database schema initialization
4. Configure Row Level Security policies

### Domain Configuration
- Backend: Automatic Railway domain
- Frontend: Custom Netlify subdomain
- SSL: Automatic certificate provisioning