# Deployment Guide for Varaha Silks Backend

## Render Deployment

### 1. Build Command
The project now includes a build script that can be run with:
```bash
npm run build
```

### 2. Environment Variables for Render
Make sure to set these environment variables in your Render dashboard:

#### Required Variables:
- `NODE_ENV=production`
- `PORT=10000` (Render will override this)
- `CLIENT_URL=https://your-frontend-domain.com`

#### Razorpay Configuration:
- `RAZORPAY_KEY_ID=your_razorpay_key_id`
- `RAZORPAY_KEY_SECRET=your_razorpay_key_secret`

#### Firebase Configuration:
- `FIREBASE_PROJECT_ID=your_project_id`
- `FIREBASE_PRIVATE_KEY=your_private_key`
- `FIREBASE_CLIENT_EMAIL=your_client_email`

#### Shiprocket Configuration (if using):
- `SHIPROCKET_EMAIL=your_shiprocket_email`
- `SHIPROCKET_PASSWORD=your_shiprocket_password`

### 3. Render Configuration
- **Build Command**: `npm run build`
- **Start Command**: `npm start`
- **Node Version**: 18.x or higher

### 4. Important Notes
- The `firebase-service-account.json` file should not be committed to version control
- Use environment variables for Firebase configuration in production
- Make sure your CORS settings allow your frontend domain
- The server will run on the port provided by Render (usually 10000)

### 5. Health Check
After deployment, you can check if the server is running by visiting:
`https://your-render-app.onrender.com/api/health`

This should return a JSON response with status "ok".
