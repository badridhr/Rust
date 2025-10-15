# 🎮 Voltix x2 Solo - Rust Server Website

Modern and responsive website for Voltix x2 Solo Rust server, built with Next.js, React, Tailwind CSS, and Framer Motion.

## ✨ Features

- 🎨 Modern design with dark theme and rust orange accents
- 📱 Fully responsive (mobile, tablet, desktop)
- 🎭 Smooth animations with Framer Motion
- 🔄 Animated loader on page load
- 📊 Dynamic online player counter
- 🎯 Floating widget that follows scroll
- ⚡ Smooth scroll
- 🎮 Direct Steam server connection button
- 💳 VIP Kits store with payment integration (PayPal, Wise, RedotPay)

## 🚀 Installation

### Prerequisites

- Node.js 18+ installed
- npm or yarn

### Installation Steps

1. **Download the project**
   - Click the three dots in the top right
   - Select "Download ZIP"
   - Extract the ZIP file

2. **Install dependencies**
   \`\`\`bash
   npm install
   \`\`\`

3. **Configure your server**
   
   Modify the following files to add your information:
   
   - `components/hero.tsx`: Line 10 - Replace `YOUR_IP:PORT` with your server IP
   - `components/join-section.tsx`: Line 14 - Replace `YOUR_IP:PORT` with your server IP
   - `components/floating-widget.tsx`: Line 30 - Replace `YOUR_IP:PORT` with your server IP
   - `app/vip-kits/page.tsx`: Update payment integration with your actual payment gateway credentials

4. **Run the development server**
   \`\`\`bash
   npm run dev
   \`\`\`

5. **Open your browser**
   
   Go to [http://localhost:3000](http://localhost:3000)

## 🎨 Customization

### Colors

Modify colors in `app/globals.css`:

\`\`\`css
--color-primary: #d35400;  /* Main rust orange */
--color-accent: #e67e22;   /* Accent orange */
\`\`\`

### Content

- **Rules**: Modify `components/rules.tsx`
- **Server Info**: Modify `components/server-info.tsx`
- **Discord/Store Links**: Modify `components/join-section.tsx`
- **VIP Kits**: Modify `app/vip-kits/page.tsx`

### Online Players API

The player counter currently uses mock data. To connect a real API:

1. Open `hooks/use-player-count.ts`
2. Replace the `fetchPlayerCount()` function with your API call:

\`\`\`typescript
async function fetchPlayerCount() {
  const response = await fetch('https://your-api.com/players')
  const data = await response.json()
  return {
    online: data.online,
    max: data.max,
  }
}
\`\`\`

### Payment Integration

To integrate real payment gateways in the VIP Kits page:

1. Open `app/vip-kits/page.tsx`
2. In the `handleCheckout()` function, replace the alert with actual payment API calls:

\`\`\`typescript
// Example for PayPal
if (selectedPayment === 'PayPal') {
  // Redirect to PayPal checkout
  window.location.href = `https://paypal.com/checkout?amount=${kit.price}`
}
\`\`\`

## 📦 Deployment

### On Vercel (Recommended)

1. Click the "Publish" button in the top right
2. Follow the instructions to deploy on Vercel

### On Hostinger or other hosting

1. **Build the project**
   \`\`\`bash
   npm run build
   \`\`\`

2. **Export static files** (if needed)
   \`\`\`bash
   npm run export
   \`\`\`

3. **Upload files**
   - Upload the `out/` or `.next/` folder depending on your configuration
   - Configure your host to serve a Next.js application

## 📁 Project Structure

\`\`\`
├── app/
│   ├── globals.css          # Global styles and theme
│   ├── layout.tsx           # Main layout
│   ├── page.tsx             # Home page
│   └── vip-kits/
│       └── page.tsx         # VIP Kits store page
├── components/
│   ├── header.tsx           # Header with navigation
│   ├── hero.tsx             # Hero section with banner
│   ├── rules.tsx            # Rules section
│   ├── server-info.tsx      # Server information
│   ├── join-section.tsx     # Join section
│   ├── footer.tsx           # Footer
│   ├── floating-widget.tsx  # Floating widget
│   └── loader.tsx           # Animated loader
├── hooks/
│   └── use-player-count.ts  # Hook for player counter
└── README.md                # This file
\`\`\`

## 🛠️ Technologies Used

- **Next.js 15** - React Framework
- **React 19** - UI Library
- **Tailwind CSS v4** - CSS Framework
- **Framer Motion** - Animations
- **Lucide React** - Icons
- **TypeScript** - Static Typing

## 📝 Important Notes

- Replace `YOUR_IP:PORT` with your actual server IP in all files
- Configure your Discord and Store links in `components/join-section.tsx`
- Add your own API for the online player counter
- Images use placeholders - replace them with your own images
- Set up payment gateway credentials for the VIP Kits store
- The VIP Kits page includes a demo checkout flow - integrate with real payment APIs for production

## 🎯 Section Overview

1. **Header** - Sticky navigation with logo and menu
2. **Hero** - Large banner with Rust image, title, and connection button
3. **Rules** - Grid of 6 rules with icons and animations
4. **Server Info** - Server characteristics (type, map, wipe, mods)
5. **Join Section** - Discord, VIP Kits buttons and IP copy
6. **VIP Kits Store** - Complete store page with payment integration
7. **Footer** - Links and information
8. **Floating Widget** - Sticky widget with server status and connection button

## 💡 Support

For any questions or issues, don't hesitate to ask for help!

Happy gaming! 🎮🔥
