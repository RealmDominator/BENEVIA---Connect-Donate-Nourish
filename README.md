# Benevia Frontend 🎨 
### Beautiful, Responsive, Impact-Driven Interface

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![PWA](https://img.shields.io/badge/PWA-Ready-5A0FC8?style=flat)](https://web.dev/progressive-web-apps/)

> A lightweight, fast, and accessible single-page application built with vanilla JavaScript. No frameworks, no bloat—just pure performance and user experience.

---

## 🌟 Overview

The Benevia frontend is a modern web application designed with a mobile-first approach, ensuring seamless experiences across all devices. Built with progressive enhancement principles, it works beautifully even in low-bandwidth environments common in rural India.

---

## ✨ Features

### 🎯 Core Functionality

- *User Authentication*
  - Secure login/registration system
  - Role-based dashboard (Individual, Restaurant, NGO)
  - Profile management with image upload
  - Password reset functionality

- *Donation Management*
  - Real-time donation counter with live updates
  - Donation form with image upload
  - QR code generation and display
  - Donation history with filtering
  - Status tracking (Pending, Verified, Completed)

- *Social Impact Feed*
  - Instagram-style post creation and display
  - Like, comment, and share functionality
  - Image and video support
  - Success story showcases
  - Trending impact stories

- *Emergency Response*
  - One-tap emergency request button
  - Location-based SOS broadcasting
  - Real-time status updates
  - Priority notification system

- *Location Services*
  - Interactive map integration
  - Nearby NGO/donation center finder
  - Route optimization display
  - Geolocation-based suggestions

- *Leaderboards & Recognition*
  - Top donors showcase (Daily, Monthly, Quarterly, Annual)
  - Achievement badges and milestones
  - Organization rankings
  - Social sharing of accomplishments

### 🎨 UI/UX Features

- Smooth scroll animations
- Loading states and skeleton screens
- Toast notifications for user feedback
- Modal dialogs for confirmations
- Infinite scroll for feeds
- Image lazy loading
- Dark mode support (coming soon)
- Multi-language support (planned)

---

## 📁 File Structure


frontend/
│
├── 📄 index.html                    # Main application entry point
│   │
│   ├── 📁 images/
│   │   ├── logo.svg                 # Sampoorna logo

---

## 🚀 Quick Start

### Prerequisites

You only need a modern web browser and a simple HTTP server. No build tools or dependencies required!

### Option 1: Python (Recommended)

bash
# Navigate to frontend directory
cd frontend

# Start server (Python 3)
python3 -m http.server 3000

# Or Python 2
python -m SimpleHTTPServer 3000


### Option 2: Node.js

bash
# Install http-server globally (one-time)
npm install -g http-server

# Start server
http-server -p 3000


### Option 3: PHP

bash
# Start PHP's built-in server
php -S localhost:3000


### Option 4: Direct Browser Access

Simply open `index.html` in your web browser. Note: Some features like API calls may not work without a proper server due to CORS restrictions.

### Access the Application

Open your browser and navigate to:

http://localhost:3000


---

## ⚙️ Configuration

### API Endpoint Configuration

Update the API base URL in `assets/js/config.js`:

javascript
const CONFIG = {
  API_BASE_URL: 'http://localhost:5001/api',  // Development
  // API_BASE_URL: 'https://api.benevia.org/api',  // Production
  
  API_TIMEOUT: 30000,
  MAX_FILE_SIZE: 5 * 1024 * 1024, // 5MB
  ALLOWED_IMAGE_TYPES: ['image/jpeg', 'image/png', 'image/jpg'],
  
  MAP_API_KEY: 'your_map_api_key_here',
  
  PAGINATION: {
    POSTS_PER_PAGE: 10,
    DONATIONS_PER_PAGE: 15
  }
};


### Environment-Specific Settings

For production deployment, update:
- API endpoints in `config.js`
- PWA manifest URLs in `manifest.json`
- Service worker cache URLs in `service-worker.js`

---

## 🔌 API Integration

### API Service Layer

All API calls are managed through `assets/js/api.js`:

javascript
// Example API call
const donations = await api.get('/donations');
const newDonation = await api.post('/donations', donationData);
const updated = await api.put(/donations/${id}, updateData);
await api.delete(/donations/${id});


### Authentication

Token-based authentication is handled automatically:

javascript
// Login
const response = await auth.login(email, password);

// Check authentication status
if (auth.isAuthenticated()) {
  // User is logged in
}

// Logout
auth.logout();


### Error Handling

API errors are handled gracefully with user-friendly messages:

javascript
try {
  const data = await api.get('/endpoint');
} catch (error) {
  toast.error(error.message || 'Something went wrong');
}


---

## 🌐 Browser Support

| Browser | Version |
|---------|---------|
| Chrome | Last 2 versions |
| Firefox | Last 2 versions |
| Safari | Last 2 versions |
| Edge | Last 2 versions |
| Opera | Last 2 versions |
| Samsung Internet | Last 2 versions |

**Mobile Support:**
- iOS Safari 12+
- Chrome for Android
- Samsung Internet
- Firefox Mobile

---

## 🧪 Testing

### Manual Testing Checklist

- [ ] Registration and login flow
- [ ] Donation creation and verification
- [ ] Social feed posting and interactions
- [ ] Emergency request submission
- [ ] Profile update functionality
- [ ] Responsive design on all devices
- [ ] PWA installation and offline mode
- [ ] Form validation and error handling
- [ ] Image upload and display

### Testing Tools

bash
# Lighthouse audit
lighthouse http://localhost:3000 --view

# Mobile device testing
# Use Chrome DevTools device emulation

# Accessibility testing
# Use axe DevTools browser extension


---

## 🚀 Deployment

### Static Hosting Platforms

**Netlify** (Recommended)
bash
# Install Netlify CLI
npm install -g netlify-cli

# Deploy
netlify deploy --prod --dir=frontend


**Vercel**
bash
# Install Vercel CLI
npm install -g vercel

# Deploy
vercel --prod frontend/


**GitHub Pages**
bash
# Push to gh-pages branch
git subtree push --prefix frontend origin gh-pages
```

### Production Checklist

- [ ] Update API endpoints to production URLs
- [ ] Minify CSS and JavaScript
- [ ] Optimize and compress images
- [ ] Update manifest.json URLs
- [ ] Configure service worker cache
- [ ] Set up custom domain
- [ ] Enable HTTPS
- [ ] Configure CDN (optional)
- [ ] Set up analytics
- [ ] Test PWA installation

---

## 📝 Best Practices

### JavaScript

- Use ES6+ features (const, let, arrow functions)
- Follow async/await pattern for promises
- Implement proper error handling
- Use meaningful variable names
- Add JSDoc comments for functions
- Keep functions small and focused

### CSS

- Use CSS variables for theming
- Follow BEM or similar naming convention
- Mobile-first media queries
- Avoid !important declarations
- Use flexbox and grid for layouts
- Minimize use of IDs for styling

### HTML

- Semantic HTML5 elements
- Proper heading hierarchy
- Alt text for images
- ARIA labels where needed
- Meta tags for SEO
- Proper form labels

---

## 🐛 Troubleshooting

### Common Issues

*Problem*: API calls not working  
*Solution*: Check if backend server is running and CORS is configured

*Problem*: Images not loading  
*Solution*: Verify file paths and ensure server is running (not just opening HTML)

*Problem*: Service Worker not updating  
*Solution*: Clear browser cache or increment service worker version

*Problem*: PWA not installable  
*Solution*: Ensure HTTPS, valid manifest.json, and registered service worker

---

## 🤝 Contributing

We welcome contributions to improve the frontend! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch
3. Follow existing code style
4. Test on multiple browsers
5. Submit a pull request

---

## 📞 Support

For frontend-specific issues or questions:

- *Issues*: [GitHub Issues](https://github.com/yourusername/sampoorna/issues)
- *Email*: ptripathi2511@gmail.com
- *Documentation*: Check /docs folder for detailed guides

---

## 📜 License

MIT License - See [LICENSE](../LICENSE) file for details

---

<div align="center">

*Benevia Frontend* - Designed with ❤️ for humanity

Built with vanilla JavaScript • No frameworks • Pure performance

[⭐ Star on GitHub](https://github.com/yourusername/Benevia) | [🐛 Report Bug](https://github.com/yourusername/Benevia/issues) | [💡 Suggest Feature](https://github.com/yourusername/Benevia/issues)

</div>
