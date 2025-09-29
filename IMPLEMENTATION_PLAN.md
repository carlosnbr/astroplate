# Codebravo Blog Implementation Plan

This comprehensive implementation plan will get your blog "Codebravo" launched today with the tagline "From code to craft. Mastering modern development."

## Phase 1: Local Configuration & Personalization

### 1.1 Primary Configuration File
The main configuration file is located at `src/config/config.json`. This file contains all the site settings including title, description, and author information.

**Required modifications to `src/config/config.json`:**

```json
{
  "site": {
    "title": "Codebravo",
    "base_url": "https://codebravo.dev",
    "base_path": "/",
    "trailing_slash": false,
    "favicon": "/images/favicon.png",
    "logo": "/images/logo.png",
    "logo_darkmode": "/images/logo-darkmode.png",
    "logo_width": "150",
    "logo_height": "30",
    "logo_text": "Codebravo"
  },
  "settings": {
    "search": true,
    "sticky_header": true,
    "theme_switcher": true,
    "default_theme": "system",
    "pagination": 2,
    "summary_length": 200,
    "blog_folder": "blog"
  },
  "params": {
    "contact_form_action": "#",
    "copyright": "© 2025 Codebravo. All rights reserved."
  },
  "metadata": {
    "meta_author": "carlosnbr",
    "meta_image": "/images/og-image.png",
    "meta_description": "From code to craft. Mastering modern development."
  }
}
```

### 1.2 Social Media Configuration
Social media links are configured in `src/config/social.json`. Add a comment in this file noting that social media links will be added later as specified in your customization notes.

### 1.3 Logo and Favicon Images
Replace the following image files in the `/public/images/` directory with your own branded versions:

- `/public/images/favicon.png` - Site favicon (typically 32x32 or 16x16 pixels)
- `/public/images/logo.png` - Main logo for light theme
- `/public/images/logo-darkmode.png` - Logo variant for dark theme
- `/public/images/avatar.png` - Author avatar image
- `/public/images/og-image.png` - Open Graph image for social sharing

### 1.4 Author Configuration
Create a new author file at `src/content/authors/carlosnbr.md`:

```markdown
---
title: Carlos Bravo
email: your-email@codebravo.dev
image: "/images/avatar.png"
description: "Full-stack developer passionate about modern web technologies and sharing knowledge with the developer community."
social:
  - name: github
    icon: FaGithub
    link: https://github.com/carlosnbr

  - name: twitter
    icon: FaTwitter
    link: https://twitter.com/carlosnbr

  - name: linkedin
    icon: FaLinkedin
    link: https://linkedin.com/in/carlosnbr
---

Passionate software developer with expertise in modern web technologies, cloud architecture, and developer tooling. I love sharing knowledge and helping other developers grow in their craft.
```

### 1.5 About Page Update
Update `src/content/about/-index.md` with your information:

```markdown
---
title: "Hey, I am Carlos Bravo!"
meta_title: "About"
description: "Learn more about Carlos Bravo and the Codebravo blog"
image: "/images/avatar.png"
draft: false
---

Hi! I'm Carlos Bravo, a passionate software developer who believes that great code is both functional and beautiful. Through Codebravo, I share insights about modern development practices, emerging technologies, and lessons learned from real-world projects.

From code to craft - that's my philosophy. I believe that writing software is as much an art as it is a science, and I'm excited to share this journey with you.
```

## Phase 2: Content Preparation

### 2.1 Remove Demo Content
Navigate to the blog directory and remove all existing demo posts:

```bash
cd src/content/blog/
rm post-1.md post-2.md post-3.md post-4.md
```

### 2.2 Create Your First Blog Post
Create a new file `src/content/blog/why-i-started-this-blog.md` with the following content:

```markdown
---
title: "Why I Started This Blog"
meta_title: ""
description: "Sharing my journey from code to craft and why I'm passionate about modern development"
date: 2025-09-28T10:00:00Z
image: "/images/banner.png"
categories: ["Personal", "Development"]
author: "carlosnbr"
tags: ["blogging", "development", "career"]
draft: false
---

Hello, world! Welcome to Codebravo - my corner of the internet where I share insights about modern software development, lessons learned from real projects, and thoughts on the craft of coding.

## Why Codebravo?

The name "Codebravo" comes from my belief that great software development is both technical skill and creative expression. "Code" represents the technical foundation - the syntax, algorithms, and systems we build. "Bravo" acknowledges the artistry - the elegant solutions, user experience, and pride we take in our work.

## What to Expect

Here you'll find:
- **Technical deep-dives** into modern frameworks, tools, and practices
- **Career insights** from my journey as a developer
- **Project case studies** sharing real-world lessons
- **Community spotlights** on tools and people making a difference

## My Mission

I'm here to bridge the gap between "just make it work" and "make it beautiful." I believe that understanding the fundamentals while embracing modern practices leads to better software and happier developers.

Whether you're just starting your coding journey or you're a seasoned developer looking to level up, I hope you'll find something valuable here.

Thanks for stopping by!

*Carlos Bravo*
```

### 2.3 Update Homepage Content
Update `src/content/homepage/-index.md` to reflect your blog's identity:

```yaml
---
# Banner
banner:
  title: "From Code to Craft: Mastering Modern Development"
  content: "Welcome to Codebravo - your guide to building better software, advancing your career, and finding joy in the craft of development."
  image: "/images/banner.png"
  button:
    enable: true
    label: "Read My Latest Posts"
    link: "/blog"

# Features (update to reflect your blog's focus)
features:
  - title: "Modern Development Practices"
    image: "/images/service-1.png"
    content: "Deep dives into modern frameworks, tools, and development practices that help you build better software."
    bulletpoints:
      - "React, Next.js, and modern frontend development"
      - "Cloud architecture and deployment strategies"
      - "Developer productivity tools and workflows"
      - "Code quality and testing best practices"
    button:
      enable: true
      label: "Explore Topics"
      link: "/categories"

  - title: "Career Growth Insights"
    image: "/images/service-2.png"
    content: "Navigate your development career with insights from real-world experience and industry trends."
    bulletpoints:
      - "Career progression strategies"
      - "Technical leadership principles"
      - "Remote work and team collaboration"
      - "Continuous learning approaches"
    button:
      enable: true
      label: "Career Posts"
      link: "/tags/career"

  - title: "Community & Craft"
    image: "/images/service-3.png"
    content: "Celebrating the art and community of software development."
    bulletpoints:
      - "Open source contributions and community building"
      - "Code review culture and collaboration"
      - "Developer wellness and work-life balance"
      - "Industry trends and future directions"
    button:
      enable: true
      label: "Join the Conversation"
      link: "/contact"
---
```

## Phase 3: Git & Vercel Deployment

### 3.1 Initialize Git Repository
```bash
# Navigate to project root
cd /Users/carlosbravo/Documents/Projects/astroplate

# Initialize new git repository (this removes existing git history)
rm -rf .git
git init

# Add all project files
git add .

# Create initial commit
git commit -m "Initial commit: Set up Codebravo blog with personalized content"
```

### 3.2 Connect to GitHub Repository
```bash
# Connect to your new GitHub repository
git remote add origin https://github.com/carlosnbr/codebravo-blog.git

# Push to main branch
git branch -M main
git push -u origin main
```

### 3.3 Deploy to Vercel
Follow these steps to deploy your blog to Vercel:

1. **Sign in to Vercel**: Go to [vercel.com](https://vercel.com) and sign in with your GitHub account
2. **Import Project**: Click "Import Project" and select your `codebravo-blog` repository from GitHub
3. **Configure Project**:
   - **Project Name**: `codebravo-blog` (or your preferred name)
   - **Framework Preset**: Astro (should be auto-detected)
   - **Root Directory**: `./` (leave as default)
   - **Build Command**: `yarn build` (or `npm run build`)
   - **Output Directory**: `dist` (leave as default)
   - **Install Command**: `yarn install` (or `npm install`)
4. **Deploy**: Click "Deploy" - Vercel will automatically build and deploy your site
5. **Wait for Deployment**: The deployment process typically takes 2-3 minutes
6. **Access Your Site**: Once complete, Vercel will provide you with a deployment URL (e.g., `https://codebravo-blog.vercel.app`)

**Note**: Default Vercel settings work perfectly for Astro projects, so no additional configuration is needed.

## Phase 4: Connecting the codebravo.dev Domain

### 4.1 Add Custom Domain in Vercel
1. **Open Vercel Dashboard**: Go to [vercel.com/dashboard](https://vercel.com/dashboard)
2. **Select Your Project**: Click on your `codebravo-blog` project
3. **Go to Settings**: Click on the "Settings" tab
4. **Navigate to Domains**: Click on "Domains" in the left sidebar
5. **Add Domain**: Click "Add Domain" and enter `codebravo.dev`
6. **Configure Domain**: Select "Add" to proceed with domain configuration

### 4.2 Get DNS Records from Vercel
After adding the domain in Vercel:

1. **Wait for Configuration**: Vercel will check your domain configuration
2. **View DNS Records**: Vercel will display the required DNS records (either A records or CNAME record)
3. **Copy Records**: Note down the exact DNS records provided by Vercel

### 4.3 Configure DNS in Cloudflare
1. **Access Cloudflare Dashboard**: Go to [dash.cloudflare.com](https://dash.cloudflare.com) and log in
2. **Select Your Domain**: Choose `codebravo.dev` from your domain list
3. **Go to DNS Settings**: Click on "DNS" in the top navigation
4. **Add DNS Records**: For each record provided by Vercel:
   - **Type**: A (for IP addresses) or CNAME (for domain alias)
   - **Name**: Copy exactly as shown in Vercel (usually `@` for root domain)
   - **Value**: Copy the IP address or target domain from Vercel
   - **TTL**: Auto (or 300 seconds)
   - **Proxy Status**: DNS only (uncheck the orange cloud proxy)

### 4.4 Verify and Go Live
1. **Wait for Propagation**: DNS changes can take up to 24 hours to propagate globally
2. **Verify in Vercel**: Return to your Vercel project dashboard and check domain status
3. **SSL Certificate**: Vercel will automatically provision an SSL certificate
4. **Site Goes Live**: Once DNS propagates and SSL is ready, your site will be accessible at `https://codebravo.dev`

**Note**: The DNS configuration process typically takes 5-30 minutes to start working, but can take up to 24 hours for full global propagation.

---

**Congratulations!** Following this plan will get your Codebravo blog up and running today. The existing visual theme has been preserved as requested, focusing instead on configuration, content, and deployment. You can always customize the visual elements later once the blog is live and functioning.
