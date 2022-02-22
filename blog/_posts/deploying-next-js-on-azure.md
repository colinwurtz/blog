---
title: 'Deploying your Next JS app to Azure App Service'
excerpt: 'Detailed instructions and caveats for displaying your Next JS app to Azure App Service using Github Actions'
coverImage: '/assets/blog/hello-world/cover.jpg'
date: '2020-03-16T05:35:07.322Z'
author:
  name: Colin Wurtz
  picture: '/assets/blog/authors/tim.jpeg'
ogImage:
  url: '/assets/blog/hello-world/cover.jpg'
---

Goal: Quickly spin up a Next JS web app and deploy to Azure App Service. Bonus points for continuous deployment using Github Actions for automation and the ability to deploy the static app from a sub directory. 


## Prerequisites

- Azure account with active subscription
- Github account
- Git/Node JS 14 installed

## Step 1 - Initialize Github repo

```bash
mkdir notes
cd notes
git init
echo "# blog" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/colinwurtz/blog.git
git push -u origin main
```

## Step 2 - Spin up NextJS app

Using `create-next-app`:

```
npx create-next-app --example blog-starter-typescript
```

## Step 3 - Go to Azure Portal and create App Service

Create new App Service. Pick Node 14 LTS as the runtime with a Linux Plan. If you don't already have an App Service Plan created, you'll need to create one here.

![image info](/public/assets/blog/nextjs-azure/create-app-service.png)

