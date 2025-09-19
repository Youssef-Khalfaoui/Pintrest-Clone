# 📌 Pinterest Clone

A full-stack Pinterest-inspired social media platform built with React, Redux Toolkit, Sanity CMS, and Material-UI. Features responsive design, Google OAuth authentication, real-time content management, and seamless integration with Pexels API for high-quality images.

![Pinterest Clone](https://img.shields.io/badge/Status-Live-success)
![React](https://img.shields.io/badge/React-19.1.1-blue)
![Redux](https://img.shields.io/badge/Redux-2.9.0-purple)
![Sanity](https://img.shields.io/badge/Sanity-4.8.1-red)
![License](https://img.shields.io/badge/License-MIT-green)

## 🌟 Live Demo

**🚀 [View Live Application](https://pintrestiiclone.netlify.app/)**

## ✨ Key Features

### 🔐 **Authentication & User Management**
- **Google OAuth Integration** - Seamless sign-in with Google accounts
- **Manual Registration** - Email/password authentication with bcrypt encryption
- **Persistent Sessions** - Automatic login state management
- **User Profiles** - Personalized profile pages with avatar support

### 🖼️ **Content Management**
- **Pin Creation & Saving** - Create and save pins from external sources
- **Pexels Integration** - Access to millions of high-quality stock photos
- **Category Organization** - Browse content by categories (Nature, Food, Travel, etc.)
- **Search Functionality** - Advanced search with auto-suggestions and trending queries
- **Masonry Layout** - Pinterest-style responsive grid layout

### 💬 **Social Features**
- **Comments System** - Real-time commenting on pins
- **Save Collections** - Organize saved pins in personal collections
- **User Interactions** - Like, save, and share functionality
- **Related Content** - Discover similar pins and recommendations

### 📱 **User Experience**
- **Fully Responsive Design** - Optimized for desktop, tablet, and mobile devices
- **Smooth Animations** - CSS transitions and loading states
- **Infinite Scrolling** - Seamless content discovery
- **Progressive Loading** - Optimized image loading and caching
- **Dark/Light Theme Support** - Modern UI with theme switching

### 🛠️ **Technical Features**
- **Real-time Updates** - Live content synchronization
- **Optimistic UI Updates** - Instant feedback for user actions
- **Error Handling** - Comprehensive error boundaries and fallbacks
- **Performance Optimization** - Code splitting and lazy loading
- **SEO Friendly** - Meta tags and social sharing optimization

## 🏗️ Architecture

```
Pintrest-Clone/
├── client/                 # React Frontend Application
│   ├── public/            # Static assets
│   ├── src/
│   │   ├── components/    # Reusable UI components
│   │   ├── containers/    # Page-level components
│   │   ├── features/      # Redux slices and logic
│   │   ├── api/          # API integration layers
│   │   └── utils/        # Helper functions
└── Server/                # Sanity CMS Backend
    ├── schemaTypes/       # Content models
    ├── sanity.config.js   # Sanity configuration
    └── package.json       # Backend dependencies
```

## 🚀 Technology Stack

### **Frontend**
- **React 19.1.1** - Modern React with hooks and concurrent features
- **Redux Toolkit 2.9.0** - State management with RTK Query
- **React Router DOM 7.8.2** - Client-side routing and navigation
- **Styled Components 6.1.19** - CSS-in-JS styling solution
- **Material-UI 7.3.2** - Component library and design system
- **React OAuth Google** - Google authentication integration

### **Backend & CMS**
- **Sanity 4.8.1** - Headless CMS for content management
- **Sanity Studio** - Content management interface
- **Sanity Client** - API client for data fetching

### **External APIs**
- **Pexels API** - High-quality stock photography
- **Google OAuth 2.0** - User authentication service

### **Development Tools**
- **Create React App** - Build toolchain and development server
- **ESLint** - Code linting and quality assurance
- **Prettier** - Code formatting
- **React Testing Library** - Component testing framework

## 📦 Installation & Setup

### Prerequisites
- **Node.js** (v16 or higher)
- **npm** or **yarn** package manager
- **Git** for version control
- **Sanity CLI** for CMS management

### 1. Clone Repository
```bash
git clone https://github.com/Youssef-Khalfaoui/Pintrest-Clone.git
cd Pintrest-Clone
```

### 2. Setup Frontend (Client)
```bash
cd client
npm install

# Create environment file
cp .env.example .env

# Add your API keys to .env
REACT_APP_PEXELS_API_KEY=your_pexels_api_key
REACT_APP_GOOGLE_CLIENT_ID=your_google_client_id
REACT_APP_SANITY_TOKEN=your_sanity_token
```

### 3. Setup Backend (Sanity)
```bash
cd ../Server
npm install

# Install Sanity CLI globally (if not already installed)
npm install -g @sanity/cli

# Login to Sanity
sanity login

# Deploy Sanity Studio (optional)
sanity deploy
```

### 4. Configure CORS Settings
```bash
# Add your domain to Sanity CORS settings
sanity cors add https://your-domain.com --credentials
sanity cors add http://localhost:3000 --credentials
```

### 5. Start Development Servers
```bash
# Terminal 1: Start React development server
cd client
npm start

# Terminal 2: Start Sanity Studio (optional)
cd Server
npm run dev
```

## 🌍 Environment Variables

### Client (.env)
```env
# Pexels API for stock photos
REACT_APP_PEXELS_API_KEY=your_pexels_api_key

# Google OAuth credentials
REACT_APP_GOOGLE_CLIENT_ID=your_google_client_id

# Sanity CMS credentials
REACT_APP_SANITY_TOKEN=your_sanity_token
```

### Getting API Keys

1. **Pexels API Key**
   - Visit [Pexels API](https://www.pexels.com/api/)
   - Create account and generate API key

2. **Google OAuth Client ID**
   - Go to [Google Cloud Console](https://console.cloud.google.com/)
   - Create new project or select existing
   - Enable Google+ API
   - Create OAuth 2.0 credentials

3. **Sanity Token**
   - Visit [Sanity.io](https://www.sanity.io/)
   - Create project and get project ID
   - Generate API token with appropriate permissions

## 📱 Responsive Design

The application is fully responsive with breakpoints optimized for:

- **Desktop** (1200px+) - Full featured layout
- **Tablet** (768px - 1199px) - Adapted navigation and grid
- **Mobile** (320px - 767px) - Single-column layout and mobile navigation

### Key Responsive Features
- **Masonry Grid**: Adapts from 5 columns to 1 column
- **Navigation**: Collapsible sidebar on mobile
- **Forms**: Touch-friendly inputs and buttons
- **Images**: Optimized loading and sizing
- **Typography**: Scaled for readability across devices

## 🔧 API Integration

### Sanity CMS Queries
```javascript
// Fetch pins with related data
const pinsQuery = `*[_type == "pin" && defined(image.asset)] | order(_createdAt desc) {
  _id,
  title,
  about,
  destination,
  category,
  image {
    asset -> {
      _id,
      url
    }
  },
  postedBy -> {
    _id,
    userName,
    image
  },
  save[] {
    userId,
    postedBy -> {
      _id,
      userName
    }
  },
  "saveCount": count(save)
}`;
```

### Pexels API Integration
```javascript
// Search photos with pagination
const searchPhotos = async (query, page = 1) => {
  const response = await fetch(
    `https://api.pexels.com/v1/search?query=${query}&per_page=20&page=${page}`,
    {
      headers: {
        Authorization: process.env.REACT_APP_PEXELS_API_KEY
      }
    }
  );
  return response.json();
};
```

## 🚀 Deployment

### Frontend Deployment (Netlify)
```bash
# Build production version
cd client
npm run build

# Deploy to Netlify (drag & drop build folder or use CLI)
npm install -g netlify-cli
netlify deploy --prod --dir=build
```

### Backend Deployment (Sanity)
```bash
cd Server
sanity deploy
```

### Environment Setup for Production
1. Add environment variables in Netlify dashboard
2. Configure Sanity CORS for production domain
3. Update Google OAuth authorized origins
4. Test all API integrations in production

## 📊 Performance Optimizations

### Frontend Optimizations
- **Code Splitting** - Dynamic imports for route-based splitting
- **Image Optimization** - Responsive images and lazy loading
- **Caching Strategy** - Redux persist for offline capability
- **Bundle Analysis** - Webpack bundle analyzer integration

### Backend Optimizations
- **CDN Integration** - Sanity's global CDN for assets
- **Query Optimization** - Efficient GROQ queries
- **Caching Headers** - Proper cache control setup

## 🧪 Testing

```bash
# Run all tests
cd client
npm test

# Run tests with coverage
npm test -- --coverage

# Run tests in CI mode
npm test -- --ci --coverage --watchAll=false
```

### Testing Strategy
- **Unit Tests** - Component and utility function testing
- **Integration Tests** - API integration and user flow testing
- **E2E Tests** - Critical user journey automation
- **Visual Regression** - UI consistency testing

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Development Guidelines
- Follow existing code style and conventions
- Write tests for new features
- Update documentation as needed
- Ensure responsive design compliance
- Test across different browsers and devices

## 🐛 Known Issues & Roadmap

### Current Issues
- [ ] CORS configuration for production deployment
- [ ] Mobile popup positioning for OAuth
- [ ] Image optimization for large uploads

### Future Enhancements
- [ ] **Push Notifications** - Real-time activity notifications
- [ ] **Advanced Search** - AI-powered content discovery
- [ ] **Video Support** - Video pin creation and playback
- [ ] **Social Features** - Follow users and collaborative boards
- [ ] **Analytics Dashboard** - User engagement insights
- [ ] **PWA Features** - Offline capability and app installation
- [ ] **AI Integration** - Smart content recommendations
- [ ] **API Rate Limiting** - Enhanced security measures

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Youssef Khalfaoui**
- GitHub: [@Youssef-Khalfaoui](https://github.com/Youssef-Khalfaoui)
- LinkedIn: [Your LinkedIn Profile](https://linkedin.com/in/your-profile)
- Email: youssefkhalfaoui30@gmail.com

## 🙏 Acknowledgments

- **Pinterest** - Original inspiration and design concepts
- **Pexels** - High-quality stock photography API
- **Sanity.io** - Excellent headless CMS platform
- **Material-UI** - Comprehensive React component library
- **React Community** - Amazing open-source ecosystem
- **Netlify** - Seamless deployment and hosting platform

## 📸 Screenshots

### Desktop View
![Desktop Home Page](https://via.placeholder.com/800x600/f0f0f0/333?text=Desktop+Home+View)

### Mobile View  
![Mobile View](https://via.placeholder.com/400x800/f0f0f0/333?text=Mobile+View)

### Pin Details
![Pin Details](https://via.placeholder.com/800x600/f0f0f0/333?text=Pin+Details+Page)

---

⭐ **Star this repository if you found it helpful!**

🔗 **[Live Demo](https://pintrestiiclone.netlify.app/)** | 📚 **[Documentation](#)** | 🐛 **[Report Bug](https://github.com/Youssef-Khalfaoui/Pintrest-Clone/issues)**