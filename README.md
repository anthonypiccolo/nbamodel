VuePress website for NBA Betting Model.

# Build & Deployment steps

1. Clone repo
2. Move to Cloned folder
3. Move to docs folder
4. Run **"firebase init"** command
5. Choose existing GCP project
6. Set public  directory to **"src/.vuepress/dist"**
8. Configure as a SPA (rewrite all urls to /index.html)?
9. Run **"npm i"** to install npm package
10. Run **"npm run build"** to build for production
11. Finally, Run **"firebase deploy --only hosting"**
12. Done!!!!
