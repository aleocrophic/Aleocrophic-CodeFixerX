# 🔧 Vercel Configuration Fix

## Problem
Error: `The 'functions' property cannot be used in conjunction with the 'builds' property`

## Solution
Update your `vercel.json` to use only the `framework` property:

### ❌ Before (Causes Error)
```json
{
  "version": 2,
  "builds": [
    {
      "src": "package.json",
      "use": "@vercel/next"
    }
  ],
  "functions": {
    "src/app/api/**/*.ts": {
      "maxDuration": 30
    }
  }
}
```

### ✅ After (Fixed)
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

## Why This Works

1. **Modern Next.js Support**: Vercel automatically detects and optimizes Next.js applications
2. **Framework Detection**: Using `"framework": "nextjs"` tells Vercel to use built-in Next.js optimization
3. **Simplified Configuration**: No need for complex `builds` or `functions` configuration
4. **API Routes**: Next.js API routes work automatically without additional configuration

## Deployment Steps

1. Update your `vercel.json` with the fixed configuration
2. Push to your repository
3. Deploy to Vercel (automatic or manual)

## Environment Variables

Add these in Vercel Dashboard → Project Settings → Environment Variables:
- `NEXT_PUBLIC_FIREBASE_API_KEY`
- `NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN`
- `NEXT_PUBLIC_FIREBASE_PROJECT_ID`
- `NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET`
- `NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID`
- `NEXT_PUBLIC_FIREBASE_APP_ID`

## Verification

After deployment, your application should:
- ✅ Build successfully without errors
- ✅ Deploy correctly to Vercel
- ✅ Handle API routes automatically
- ✅ Support Firebase authentication
- ✅ Work with all Next.js features

---

**Note**: For Next.js 15 with App Router, the simplified configuration is recommended and fully supported by Vercel.