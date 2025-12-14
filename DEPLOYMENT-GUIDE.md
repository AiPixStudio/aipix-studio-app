# AIpix Studio - Production Deployment

## Quick Start Guide

Your app is ready to deploy! Follow these steps to get live.

### What's Configured:
- ✅ Master Password: `Welcome2PortraitMagic`
- ✅ Cloud Run Backend: `https://holiday-magic-studio-633379690324.us-west1.run.app`
- ✅ Authentication: Email-based user separation
- ✅ Security: 1:1 data isolation per customer

### Deploy to Vercel (15 minutes):

1. **Create Vercel Account**
   - Go to: https://vercel.com/signup
   - Sign up with GitHub, GitLab, or Email
   - Free plan is perfect for this

2. **Upload Your Project**
   - Click "Add New Project"
   - Choose "Import Git Repository" OR "Deploy from CLI"
   - Upload all files from this `aipix-production` folder

3. **Configure Build Settings**
   - Framework Preset: Vite
   - Build Command: `npm run build`
   - Output Directory: `dist`
   - Install Command: `npm install`

4. **Deploy!**
   - Click "Deploy"
   - Wait 2-3 minutes
   - You'll get a URL like: `https://aipix-studio-xxxxx.vercel.app`

### Connect Your Domain (app.aipix.studio):

**In Hostinger:**
1. Log into your Hostinger account
2. Go to DNS Management for aipix.studio
3. Add a new CNAME record:
   - Type: `CNAME`
   - Name: `app`
   - Value: `cname.vercel-dns.com`
   - TTL: `14400` (or Auto)

**In Vercel:**
1. Go to your project Settings → Domains
2. Click "Add Domain"
3. Enter: `app.aipix.studio`
4. Vercel will verify DNS (takes 5-10 minutes)

### HighLevel Setup:

**Email Template to Send Customers:**
```
Subject: Welcome to AIpix Studio! 🎨

Hi [First Name],

Thank you for your purchase! You now have access to AIpix Studio.

Here's how to get started:

1. Visit: https://app.aipix.studio
2. Enter your access code: Welcome2PortraitMagic
3. Enter your email address: [Email]
4. Start creating amazing AI portraits!

Your email keeps your images private and organized - nobody else can access your work.

Questions? Reply to this email anytime!

Happy creating!
The AIpix Studio Team
```

**HighLevel Workflow:**
1. Trigger: "Stripe Payment Successful"
2. Action: Send Email (use template above)
3. Done! That's it!

### Testing:

1. Visit https://app.aipix.studio
2. Enter password: `Welcome2PortraitMagic`
3. Enter any email (use yours for testing)
4. Should see the app!
5. Try generating an image

### Troubleshooting:

**"Method Not Allowed" error:**
- This is normal for the Cloud Run URL if visited directly
- The app connects to it via API calls

**White screen:**
- Check browser console (F12)
- Usually means missing file - re-upload all files

**Can't connect to domain:**
- DNS takes 10-60 minutes to propagate
- Use the Vercel URL in the meantime

### Support:

Need help? Check:
- Vercel Docs: https://vercel.com/docs
- Hostinger DNS Guide: https://support.hostinger.com/en/articles/1583227-how-to-edit-dns-records

---

You're ready to launch! 🚀
