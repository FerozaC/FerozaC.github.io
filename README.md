# Feroza Chishty - Portfolio Website

A modern, single-page premium portfolio application showcasing frontend development expertise with responsive design, dark mode support, and functional email contact form.

🌐 **Live**: https://ferozac.github.io/

## ✨ Features

- **Single-Page Application** - Smooth scrolling with no page reloads
- **Responsive Design** - Mobile-first approach with adaptive layouts (h-72 mobile, h-96 desktop)
- **Dark Mode** - Toggle between light and dark themes with localStorage persistence
- **Tech Stack Grid** - 12+ technologies with Font Awesome icons (React, JavaScript, HTML5, CSS3, Tailwind, Next.js, Git, GraphQL, SQL, etc.)
- **Timeline** - Education and experience timeline with visual indicators
- **Contact Form** - EmailJS integration for direct email submissions with validation
- **Modern UI** - Glassmorphic navbar, smooth animations, 3D shadows
- **Accessibility** - Semantic HTML, ARIA labels, keyboard navigation

## 🎨 Design System

### Color Palette
- **Hero Purple**: `#2A0845` - Deep purple gradient background
- **Cream**: `#FDFBF7` - Main background (light mode)
- **Dark Purple**: `#0f051a` - Background (dark mode)
- **Magenta**: `#E91E63` - Primary CTA buttons
- **Cyan**: `#00BCD4` - Secondary accents

### Typography
- **Serif**: Playfair Display (headings, prominent text)
- **Sans-serif**: Plus Jakarta Sans (body text, navigation)

## 🛠️ Tech Stack

### Frontend
- **HTML5** - Semantic markup
- **Tailwind CSS** - Utility-first CSS framework (CDN)
- **Vanilla JavaScript** - No frameworks, lightweight interactions
- **Font Awesome 6** - Icon library (CDN)

### Backend Integration
- **EmailJS** - Client-side email service (v4.0 via CDN)

## 📋 Page Structure

### 1. **Navbar**
- Sticky glassmorphic navigation
- Dark mode toggle (moon icon)
- Mobile-responsive hamburger menu
- Smooth scroll links to sections

### 2. **Hero Section**
- Deep purple gradient background
- Large serif headline + subheading
- Two CTA buttons: "See my projects" (magenta) and "Resume" (outline)
- Avatar placeholder with responsive sizing

### 3. **About Section**
- Professional background and expertise summary
- Full-stack experience overview
- UI/UX principles and soft skills

### 4. **Tech Stack**
- 12 technology cards in grid layout
- Font Awesome icons for each tech
- Hover animations with lift effect
- Color-coded gradient backgrounds

### 5. **Projects (Under Construction)**
- Placeholder for future projects showcase
- Visual construction asset
- CTA button linking to contact

### 6. **Education & Experience**
- Vertical timeline with purple nodes
- 7 milestones:
  - National Certificate (Umuzi)
  - SheCodes Certifications
  - Bachelor of Arts (Nelson Mandela University)
  - Golden Key International Honour Society
  - Software Development Internship
  - Junior Software Developer role

### 7. **Contact**
- Contact image on left (mobile: top)
- Email form on right (mobile: bottom)
- Real-time character counter (0-500)
- Form validation with error messages
- Social links (GitHub, LinkedIn, Email)
- Copyright notice

## 🚀 Setup & Installation

### Prerequisites
- Web browser with JavaScript enabled (HTTP/HTTPS, not file://)
- EmailJS account (free tier available at https://www.emailjs.com/)

### Local Development

#### Option 1: Python HTTP Server ⭐ Recommended
```bash
cd /path/to/FerozaC.github.io
python -m http.server 8000
# Open http://localhost:8000
```

#### Option 2: Node.js HTTP Server
```bash
npx http-server
```

#### Option 3: VS Code Live Server
- Install "Live Server" extension in VS Code
- Right-click `index.html` → "Open with Live Server"

### EmailJS Configuration

1. **Create EmailJS Account**
   - Sign up at https://www.emailjs.com/ (free tier available)

2. **Add Email Service**
   - Dashboard → Email Services → Add Service
   - Select your email provider (Gmail, Outlook, etc.)
   - Verify connection
   - **Copy Service ID**

3. **Create Email Template**
   - Dashboard → Email Templates → Create Template
   - Set template variables:
     ```
     Name: {{from_name}}
     Email: {{from_email}}
     Message: {{message}}
     To Email: {{to_email}}
     ```
   - **Copy Template ID**

4. **Get API Credentials**
   - Dashboard → Account → API Keys
   - **Copy Public Key**

5. **Update index.html** (around line 810)
   ```javascript
   emailjs.init({
       publicKey: 'YOUR_PUBLIC_KEY_HERE'
   });

   emailjs.send('YOUR_SERVICE_ID_HERE', 'YOUR_TEMPLATE_ID_HERE', {
       from_name: name,
       from_email: email,
       message: message,
       to_email: 'your-email@example.com'
   })
   ```

## 📋 Contact Form Validation

### Client-Side Validation
- **Name**: Minimum 2 characters (UX validation only)
- **Email**: Must contain "@" symbol (basic format check)
- **Message**: 10-500 characters with real-time counter
- **Color Feedback**: Counter turns orange at 80% capacity

### Security Notes
- Client-side validation is **UX only**
- Real spam protection is server-side via **EmailJS backend**
- Credentials are visible in source (this is normal for static sites)
- EmailJS enforces rate limiting and validation on their servers

## 🎨 Customization

### Colors
Edit Tailwind config (index.html, line ~54):
```javascript
colors: {
    'hero-purple': '#2A0845',
    'cream': '#FDFBF7',
    'accent-magenta': '#E91E63',
    'accent-cyan': '#00BCD4',
}
```

### Dark Mode Colors
Edit CSS (index.html, line ~220-280):
```css
html.dark body {
    background-color: #0f051a;
    color: #FDFBF7;
}
html.dark .bg-white {
    background-color: #1a0f2e;
}
```

### Images
Replace in `./images/` folder:
- `avatar.png` - Hero section (currently visible)
- `under_construction.png` - Projects section
- `contact_me.png` - Contact section

Images resize responsively:
- Mobile: 288px height
- Desktop: 384px height

### Social Links
Edit contact section (line ~650):
```html
<a href="https://github.com/YOUR_USERNAME">GitHub</a>
<a href="https://linkedin.com/in/YOUR_PROFILE">LinkedIn</a>
<a href="mailto:your-email@example.com">Email</a>
```

## 📁 File Structure

```
FerozaC.github.io/
├── index.html              # Single-page application
├── README.md              # Documentation
├── images/
│   ├── avatar.png         # Hero avatar (responsive)
│   ├── under_construction.png
│   └── contact_me.png
└── styles/                # CSS (embedded in index.html)
```

## 🔒 Security & Best Practices

### Credentials Visibility
- **EmailJS Public Key**: Intentionally public (client-side use only)
- **Service/Template IDs**: Used client-side (semi-public, acceptable)
- Secret keys are never exposed

### Server-Side Protection
EmailJS provides backend security:
- Rate limiting per IP address
- Email validation and filtering
- Spam detection
- CORS protection

### GitHub Best Practices
- All credentials safely exposed in static site (expected)
- For sensitive future APIs, use GitHub Secrets + Actions
- Keep `.env.example` in repo, `.env` in `.gitignore`

## 📱 Responsive Design

### Breakpoints
- **Mobile**: < 768px
- **Tablet**: 768px - 1024px
- **Desktop**: > 1024px

### Image Sizing
```tailwind
Mobile:  h-72    (288px)
Desktop: lg:h-96 (384px)
object-cover object-[60%_center]  /* Crops from right to hide watermarks */
```

## 🌙 Dark Mode

### How It Works
1. Click moon icon (top right navbar)
2. Toggles `html.dark` class
3. CSS switches colors using `html.dark selector`
4. Preference saved to localStorage (`darkMode` key)
5. Persists across browser sessions

### Supported Elements
- Body background
- Text colors
- Card backgrounds
- Input fields
- Timeline elements
- Navigation links

## 🔄 Performance

- **No build process**: Pure HTML/CSS/JS
- **CDN resources**: Tailwind, Font Awesome, EmailJS
- **Minimal dependencies**: Static site
- **Smooth scrolling**: Native browser + CSS
- **Lazy loading**: Images load on view

## 🚀 Deployment to GitHub Pages

### Automatic Deployment
1. Push changes to `main` branch
2. Site updates automatically (within ~1 minute)
3. View at: https://ferozac.github.io

### Custom Domain
1. Create `CNAME` file with your domain
2. Update DNS at your registrar
3. Verify in repository settings → Pages

## 🐛 Troubleshooting

### EmailJS Not Sending
**Issue**: Form submits but no email received
- Open browser console (F12 → Console)
- Check for error messages with "emailjs" keyword
- Verify credentials are correct
- Test on `http://` or `https://` (not `file://`)
- Check EmailJS dashboard for rate limits

### Images Not Displaying
- Verify relative paths: `./images/filename.png`
- Check file format and size
- Ensure images exist in folder
- Clear browser cache (Ctrl+Shift+Delete)

### Dark Mode Not Persisting
- Check if localStorage is enabled in browser
- Clear browser storage and reload
- Verify CSS dark mode styles are present
- Test in private/incognito mode

### Mobile Layout Issues
- Check viewport meta tag is present
- Verify Tailwind responsive classes (sm:, md:, lg:)
- Test in real device or browser DevTools

## 📊 Browser Support

- Chrome/Edge: ✅ Full support
- Firefox: ✅ Full support
- Safari: ✅ Full support
- IE 11: ❌ Not supported (uses modern ES6)

## 📝 Commits & Git Workflow

```bash
# View recent commits
git log --oneline -5

# View changes
git status

# Stage and commit
git add index.html
git commit -m "Update portfolio section"
```

## ✅ Testing Checklist

- [ ] Links scroll to correct sections
- [ ] Dark mode toggles and persists
- [ ] Form validates inputs
- [ ] Character counter works
- [ ] Responsive on mobile (375px)
- [ ] Responsive on tablet (768px)
- [ ] Responsive on desktop (1024px+)
- [ ] EmailJS sends test emails
- [ ] Images load correctly
- [ ] Email form resets after submission

## 📚 Resources

- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [Font Awesome Icons](https://fontawesome.com/icons)
- [EmailJS Docs](https://www.emailjs.com/docs/)
- [MDN Web Docs](https://developer.mozilla.org/)
- [Can I Use?](https://caniuse.com/) - Browser support

## 📄 License

Open source - Feel free to use as inspiration for your own portfolio.

---

**Last Updated**: June 17, 2026
**Version**: 2.0 (Single-page redesign with modern UI)
**Status**: ✅ Production ready
