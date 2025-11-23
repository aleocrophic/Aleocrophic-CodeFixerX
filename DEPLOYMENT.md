# Aleocrophic CodeFixerX - Deployment Guide

## Quick Start

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Start production server
npm start
```

## Environment Setup

Create a `.env.local` file with your Firebase configuration:

```env
NEXT_PUBLIC_FIREBASE_API_KEY=your_api_key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id
```

## Deployment Options

### Vercel (Recommended)

#### Option 1: Automatic Deployment
1. Connect your repository to Vercel
2. Add environment variables in Vercel dashboard
3. Deploy automatically

#### Option 2: Manual Deployment
```bash
# Build the application
npm run build

# Deploy using Vercel CLI
npm i -g vercel
vercel --prod
```

#### Vercel Configuration
The project uses a simplified `vercel.json`:

```json
{
  "framework": "nextjs",
  "env": {
    "NEXT_PUBLIC_FIREBASE_API_KEY": "@firebase-api-key",
    "NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN": "@firebase-auth-domain",
    "NEXT_PUBLIC_FIREBASE_PROJECT_ID": "@firebase-project-id",
    "NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET": "@firebase-storage-bucket",
    "NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID": "@firebase-messaging-sender-id",
    "NEXT_PUBLIC_FIREBASE_APP_ID": "@firebase-app-id"
  }
}
```

**Note**: This configuration resolves the Vercel error where `functions` and `builds` properties cannot be used together.

### Netlify

```bash
# Build the application
npm run build

# Deploy the .next folder
```

### Docker

```dockerfile
FROM node:18-alpine

WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production

COPY . .
RUN npm run build

EXPOSE 3000
CMD ["npm", "start"]
```

### Other Platforms

For any platform that supports Node.js:
1. Build: `npm run build`
2. Start: `npm start`
3. Deploy the application

## Environment Variables Setup

### Vercel Dashboard
1. Go to Project Settings → Environment Variables
2. Add the following variables:
   - `NEXT_PUBLIC_FIREBASE_API_KEY`
   - `NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN`
   - `NEXT_PUBLIC_FIREBASE_PROJECT_ID`
   - `NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET`
   - `NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID`
   - `NEXT_PUBLIC_FIREBASE_APP_ID`

### Firebase Setup Required
Before deployment, ensure:
1. Firebase Authentication is enabled
2. Google Sign-In provider is configured
3. Firestore Database is created
4. Your domain is added to authorized domains

## Features

- 🔍 AI-powered code debugging
- 🛡️ Security vulnerability scanning
- ⚡ Performance optimization
- 📚 Code explanation and documentation
- 🌍 Multi-language support (7 languages)
- 🎨 Modern UI with Tailwind CSS
- 🔐 Firebase authentication (Google + Guest)
- 📱 Responsive design

## Troubleshooting

### Build Errors
- Check Node.js version (requires 18+)
- Verify all dependencies are installed
- Check environment variables

### Runtime Errors
- Verify Firebase configuration
- Check Firebase project settings
- Ensure authorized domains are configured

### Login Issues
- Check Firebase Authentication settings
- Verify Google Sign-In is enabled
- Check authorized domains list

### Vercel Deployment Issues
- Ensure `vercel.json` only contains `framework` and `env` properties
- Remove any `functions` or `builds` properties
- Use the simplified configuration shown above

## License

MIT License - see LICENSE file for details