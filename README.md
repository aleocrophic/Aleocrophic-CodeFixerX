# Aleocrophic CodeFixerX

<div align="center">
  <h1>🌸 Aleocrophic CodeFixerX 🌸</h1>
  <p><em>Ultimate AI-Powered Code Analysis & Debugging Platform</em></p>
  <p>
    <img src="https://img.shields.io/badge/React-18-blue" alt="React 18" />
    <img src="https://img.shields.io/badge/TypeScript-5-blue" alt="TypeScript 5" />
    <img src="https://img.shields.io/badge/Next.js-15-black" alt="Next.js 15" />
    <img src="https://img.shields.io/badge/Tailwind-4-cyan" alt="Tailwind CSS 4" />
    <img src="https://img.shields.io/badge/Firebase-10-yellow" alt="Firebase" />
  </p>
</div>

## 📖 Overview

**Aleocrophic CodeFixerX** is a comprehensive AI-powered development assistant that helps developers debug, optimize, and enhance their code across multiple programming languages. Built with cutting-edge technology and designed for both beginners and enterprise developers.

### 🚀 Key Features

- **🔍 Omni Debugger**: Advanced syntax and logic error detection
- **🛡️ Security Auditor**: Comprehensive vulnerability scanning (SQLi, XSS, etc.)
- **⚡ Performance Optimizer**: Code performance enhancement suggestions
- **📚 Code Explainer**: Deep code analysis and documentation generation
- **👥 Pair Programmer**: AI-powered collaborative coding assistant
- **🔄 Legacy Resurrection**: Modernize outdated codebases (Apex Edition)
- **🚀 CI/CD Integrator**: Automated pipeline configuration (Apex Edition)
- **🎨 Experimental UI**: Auto-generate React components (Apex Edition)

## 🏗️ Architecture

### Frontend Stack
- **React 18** with TypeScript 5 for type-safe development
- **Next.js 15** with App Router for optimal performance
- **Tailwind CSS 4** with shadcn/ui components for modern UI
- **Firebase Authentication** for secure user management
- **Lucide React** for beautiful icons

### Backend Services
- **Google Firebase** (Authentication & Firestore)
- **Google Gemini AI** for advanced code analysis
- **Real-time database** for code history and user preferences

### Infrastructure
- **Serverless architecture** for scalability
- **Progressive Web App** capabilities
- **Multi-language support** (7 languages)
- **Responsive design** for all devices

## 🌍 Multi-Language Support

| Language | Flag | Native Support |
|----------|------|----------------|
| English | 🇺🇸 | ✅ |
| Indonesia | 🇮🇩 | ✅ |
| 日本語 | 🇯🇵 | ✅ |
| العربية | 🇸🇦 | ✅ |
| Русский | 🇷🇺 | ✅ |
| Deutsch | 🇩🇪 | ✅ |
| Español | 🇪🇸 | ✅ |

## 📦 Installation

### Prerequisites
- Node.js 18+ 
- npm or yarn
- Google Firebase project

### Setup Instructions

1. **Clone the repository**
```bash
git clone https://github.com/your-username/aleocrophic-codefixerx.git
cd aleocrophic-codefixerx
```

2. **Install dependencies**
```bash
npm install
```

3. **Firebase Configuration**
   - Create a Firebase project at https://console.firebase.google.com
   - Enable Authentication (Google Sign-In)
   - Create Firestore Database
   - Copy your Firebase config and update `firebaseConfig` in `src/app/page.tsx`

4. **Environment Setup**
```bash
# Create .env.local file
echo "NEXT_PUBLIC_FIREBASE_API_KEY=your_api_key" >> .env.local
echo "NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com" >> .env.local
echo "NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id" >> .env.local
echo "NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_project.appspot.com" >> .env.local
echo "NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id" >> .env.local
echo "NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id" >> .env.local
```

5. **Run the development server**
```bash
npm run dev
```

6. **Open your browser**
```
http://localhost:3000
```

## 🔧 Configuration

### Firebase Setup
1. Go to Firebase Console
2. Create a new project or use existing one
3. Enable Authentication → Sign-in method → Google
4. Create Firestore Database in test mode
5. Copy configuration to your app

### Custom API Key (Optional)
Users can bring their own Google Gemini API key for higher rate limits:
1. Go to Google AI Studio
2. Generate API key
3. Enter in Settings → Custom API Key

## 🚀 Deployment

### Vercel (Recommended)
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel --prod
```

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

## 📱 Usage Guide

### Getting Started

1. **Language Selection**: Choose your preferred language
2. **Authentication**: Sign in with Google or continue as guest
3. **Module Selection**: Choose from available analysis modules
4. **Code Input**: Paste your code for analysis
5. **Review Results**: Get AI-powered suggestions and fixes

### Lite vs Apex Edition

| Feature | Lite | Apex |
|--------|------|------|
| Basic Debugging | ✅ | ✅ |
| Security Scanning | ✅ | ✅ |
| Performance Analysis | ✅ | ✅ |
| Code Explanation | ✅ | ✅ |
| Pair Programming | ✅ | ✅ |
| Legacy Modernization | ❌ | ✅ |
| CI/CD Integration | ❌ | ✅ |
| Custom Commands | ❌ | ✅ |
| Advanced Simulation | ❌ | ✅ |
| Dynamic Documentation | ❌ | ✅ |
| UI Auto-Design | ❌ | ✅ |

### Unlock Apex Edition

1. Purchase license from: https://lynk.id/zetago-aurum/yjzz3v78oq13
2. Enter license key in upgrade section
3. Enjoy all premium features

## 🛠️ Development

### Project Structure
```
src/
├── app/
│   ├── page.tsx          # Main application component
│   ├── layout.tsx        # Root layout
│   └── globals.css       # Global styles
├── components/
│   └── ui/               # shadcn/ui components
├── lib/
│   ├── utils.ts          # Utility functions
│   └── db.ts             # Database connection
└── hooks/                # Custom React hooks
```

### Available Scripts
```bash
npm run dev          # Start development server
npm run build        # Build for production
npm run start        # Start production server
npm run lint         # Run ESLint
npm run db:push      # Push database schema
npm run db:generate  # Generate Prisma client
```

### Environment Variables
```env
NEXT_PUBLIC_FIREBASE_API_KEY=your_api_key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id
```

## 🔒 Security

### Data Privacy
- **Minimal Data Collection**: Only essential authentication and usage data
- **No Code Storage**: Source code is not permanently stored on servers
- **Ephemeral Processing**: Code snippets are processed temporarily by AI
- **User Control**: Full control over data deletion and history

### Security Features
- **Google Authentication**: Secure OAuth2 integration
- **API Key Protection**: Encrypted storage of custom API keys
- **Input Sanitization**: Protection against code injection
- **Rate Limiting**: Built-in protection against abuse

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

### Development Guidelines
- Follow TypeScript best practices
- Use ESLint for code quality
- Write meaningful commit messages
- Update documentation for new features
- Test thoroughly before submitting

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Special Thanks

<div align="center">

### Core Team
- **Rayhan Dzaky Al Mubarok** - Founder & Lead Architect
- **Takanashi Hoshino** - Spiritual Support (Blue Archive) 🌸
- **Aleocrophic Brand** - Identity & Design System

### Technologies & Services
- **Google Firebase** - Authentication & Database
- **Google Gemini AI** - Code Analysis Engine
- **Vercel** - Deployment Platform
- **GitHub** - Version Control

### Community
- All our beta testers and early adopters
- The open-source community for amazing tools
- Blue Archive fans for the inspiration 🌸

</div>

## 📞 Support

### Get Help
- **Documentation**: Check this README and in-app guide
- **Issues**: Report bugs on GitHub Issues
- **Features**: Request new features via GitHub Discussions
- **Email**: support@aleocrophic.com

### FAQ

**Q: Is my code stored permanently?**
A: No, code is processed temporarily and not stored permanently on our servers.

**Q: Can I use my own API key?**
A: Yes, you can enter your Google Gemini API key in Settings for higher rate limits.

**Q: What programming languages are supported?**
A: We support most major programming languages including JavaScript, Python, Java, C++, and more.

**Q: How do I unlock Apex features?**
A: Purchase a license from our official store and enter the key in the upgrade section.

---

<div align="center">
  <p><em>Made with ❤️ by Aleocrophic Systems</em></p>
  <p><em>Empowering developers worldwide with AI-powered tools</em></p>
</div>