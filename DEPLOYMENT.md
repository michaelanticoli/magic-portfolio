# 🚀 Deployment Guide for Magic Portfolio

Your portfolio is **ready to launch**! All personal information, projects, and content have been populated. Follow these simple steps to deploy your site.

## ✅ Pre-Deployment Checklist

- [x] Personal information populated in `src/resources/content.tsx`
- [x] Social links configured (GitHub, LinkedIn, Email, MoonTuner, Quantumelodies, Instagram)
- [x] Project files created in `src/app/work/projects/`
- [x] Configuration set in `src/resources/once-ui.config.ts`
- [x] Images present in `public/images/`

## 🌐 Deploy to Vercel (Recommended - 5 minutes)

Vercel is the easiest way to deploy Next.js applications and is made by the creators of Next.js.

### Option 1: One-Click Deploy

1. Click this button:
   
   [![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fmichaelanticoli%2Fmagic-portfolio&project-name=portfolio&repository-name=portfolio)

2. Log in with your GitHub account
3. Vercel will automatically detect Next.js and configure everything
4. Click "Deploy"
5. Your site will be live in ~2 minutes!

### Option 2: Deploy via Vercel Dashboard

1. Go to [vercel.com](https://vercel.com)
2. Click "Add New..." → "Project"
3. Import your `michaelanticoli/magic-portfolio` repository
4. Vercel will auto-detect settings:
   - **Framework Preset**: Next.js
   - **Build Command**: `npm run build`
   - **Output Directory**: (auto-detected)
5. Click "Deploy"

### Option 3: Deploy via Vercel CLI

```bash
# Install Vercel CLI
npm i -g vercel

# Navigate to your project
cd /path/to/magic-portfolio

# Deploy
vercel

# Follow the prompts to link your project
```

## 🎨 Deploy to Netlify

1. Go to [netlify.com](https://netlify.com)
2. Click "Add new site" → "Import an existing project"
3. Connect to GitHub and select `michaelanticoli/magic-portfolio`
4. Configure build settings:
   - **Build command**: `npm run build`
   - **Publish directory**: `.next`
5. Click "Deploy site"

## 🐙 Deploy to GitHub Pages (Static Export)

If you want to use GitHub Pages:

1. Update `next.config.mjs` to enable static export:
   ```js
   const nextConfig = {
     output: 'export',
     images: {
       unoptimized: true,
     },
   }
   ```

2. Build the static site:
   ```bash
   npm run build
   npm run export
   ```

3. Deploy the `out` folder to GitHub Pages

## 🔧 Environment Variables (Optional)

If you want to password-protect certain routes:

1. In your deployment platform, add environment variable:
   - **Key**: `PAGE_ACCESS_PASSWORD`
   - **Value**: Your desired password

2. Configure protected routes in `src/resources/once-ui.config.ts`

## 📝 Post-Deployment Steps

### 1. Update Base URL (Optional)

If using a custom domain, update in `src/resources/once-ui.config.ts`:

```typescript
const baseURL: string = "https://yourdomain.com";
```

### 2. Update Calendar Link (Optional)

If you use Cal.com or similar, update in `src/resources/content.tsx`:

```typescript
calendar: {
  display: true,
  link: "https://cal.com/yourusername",
},
```

### 3. Set Up Custom Domain (Optional)

**Vercel:**
1. Go to Project Settings → Domains
2. Add your custom domain
3. Update DNS records as instructed

**Netlify:**
1. Go to Site Settings → Domain management
2. Add custom domain
3. Update DNS records

### 4. Configure Newsletter (Optional)

If you want to enable newsletter signup, update Mailchimp settings in `src/resources/once-ui.config.ts`:

```typescript
const mailchimp: MailchimpConfig = {
  action: "https://YOUR-MAILCHIMP-URL/subscribe/post?parameters",
  // ... rest of config
};
```

## 🎯 Branches

- **Main branch**: Use for production deployment
- **Current branch** (`copilot/launch-portfolio-site`): Ready to merge to main

To deploy this branch:
1. Merge this PR to main, OR
2. Configure your deployment to use the `copilot/launch-portfolio-site` branch

## 📊 Monitoring Your Site

After deployment:

- **Vercel**: Check Analytics in your project dashboard
- **Netlify**: Check Analytics and Deploy logs
- Test all routes: `/`, `/about`, `/work`, `/blog`, `/gallery`

## 🆘 Troubleshooting

### Build fails with Google Fonts error
This is expected in sandboxed environments. Vercel/Netlify have internet access and will fetch fonts successfully.

### Images not loading
Ensure all image paths in MDX files match the actual files in `public/images/`

### Routes not working
Check that routes are enabled in `src/resources/once-ui.config.ts`

## 🎉 You're Ready to Launch!

Your portfolio is fully configured with:
- ✅ Personal information
- ✅ Social links  
- ✅ Project showcases
- ✅ Professional styling
- ✅ SEO optimization
- ✅ Responsive design

Just deploy and share! 🚀
