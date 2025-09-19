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
