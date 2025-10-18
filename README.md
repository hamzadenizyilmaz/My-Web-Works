# My-Web-Works - hamzadenizyilmaz.com

Welcome to the official repository for my personal website, [hamzadenizyilmaz.com](https://hamzadenizyilmaz.com). This project is a modern, responsive portfolio website inspired by [erslly/erslly-v3](https://github.com/erslly/erslly-v3), designed to showcase my projects, skills, professional background, and contact information. This README provides a comprehensive, step-by-step guide to cloning, setting up, developing, and deploying the website, with additional details on customization, troubleshooting, and best practices for publishing to GitHub.

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the Development Server](#running-the-development-server)
- [Building for Production](#building-for-production)
- [Deploying to GitHub Pages](#deploying-to-github-pages)
- [Custom Domain Setup](#custom-domain-setup)
- [Folder Structure](#folder-structure)
- [Technologies Used](#technologies-used)
- [Customizing the Website](#customizing-the-website)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Project Overview
The `hamzadenizyilmaz.com` website is a personal portfolio built to present my work, including software projects, skills, and professional achievements. The project is based on a modern web development stack, leveraging tools and frameworks similar to those used in [erslly/erslly-v3](https://github.com/erslly/erslly-v3). It is optimized for performance, accessibility, and ease of maintenance, making it suitable for developers looking to create and deploy their own portfolio websites.

## Features
- **Responsive Design**: Adapts seamlessly to desktop, tablet, and mobile devices.
- **Portfolio Section**: Showcases projects with descriptions, images, and links.
- **About Page**: Details my background, skills, and experience.
- **Contact Form**: Allows visitors to reach out (if implemented).
- **Fast Load Times**: Optimized assets and modern build tools for performance.
- **SEO-Friendly**: Structured for better search engine visibility.
- **GitHub Pages Integration**: Easy deployment for free hosting.

## Prerequisites
Before setting up the project, ensure you have the following tools installed:
- **Git**: For version control and cloning the repository. Install from [git-scm.com](https://git-scm.com/).
- **Node.js (v16 or higher)**: For managing dependencies and running the development server. Download the LTS version from [nodejs.org](https://nodejs.org/).
- **npm**: Included with Node.js, used for package management.
- **A GitHub Account**: Required for hosting the repository and deploying to GitHub Pages.
- **Code Editor**: [Visual Studio Code](https://code.visualstudio.com/) is recommended for editing files.
- **Basic Command Line Knowledge**: Familiarity with terminal commands (e.g., `cd`, `git`, `npm`).
- (Optional) A custom domain and access to its DNS settings if you plan to use `hamzadenizyilmaz.com`.

## Installation
Follow these steps to set up the project on your local machine:

1. **Clone the Repository**  
   Open a terminal and clone the repository to your computer:
   ```bash
   git clone https://github.com/your-username/hamzadenizyilmaz-com.git
   ```
   Replace `your-username` with your actual GitHub username.

2. **Navigate to the Project Directory**  
   Change to the project folder:
   ```bash
   cd hamzadenizyilmaz-com
   ```

3. **Install Dependencies**  
   Install all required npm packages listed in `package.json`:
   ```bash
   npm install
   ```
   This command downloads dependencies like React, Vite, and other libraries. If you encounter errors, ensure Node.js is up to date and try clearing the npm cache:
   ```bash
   npm cache clean --force
   npm install
   ```

4. **Verify Installation**  
   Check that the `node_modules` folder and `package-lock.json` file are created in the project directory. This confirms successful installation.

## Running the Development Server
To preview and develop the website locally:
1. Start the development server using Vite (or the build tool used in your project):
   ```bash
   npm run dev
   ```
2. Open your browser and visit the URL shown in the terminal, typically `http://localhost:3000` or `http://localhost:5173` (Vite’s default port).
3. The server supports **hot module replacement (HMR)**, meaning changes to your code will automatically update the browser preview.
4. To stop the server, press `Ctrl + C` in the terminal.

## Building for Production
To create a production-ready version of the website:
1. Run the build command:
   ```bash
   npm run build
   ```
2. This generates optimized static files in the `dist` folder (or equivalent, depending on your build tool).
3. Preview the production build locally (optional):
   ```bash
   npm run preview
   ```
   This starts a local server to test the built files, typically at `http://localhost:4173`.

4. Verify the `dist` folder contains files like `index.html`, `assets/`, and other static resources.

## Deploying to GitHub Pages
To host your website on GitHub Pages for free:

1. **Install the `gh-pages` Package**  
   If not already included, install the `gh-pages` package as a dev dependency:
   ```bash
   npm install --save-dev gh-pages
   ```

2. **Configure `package.json`**  
   Add the following scripts to the `scripts` section of `package.json`:
   ```json
   "scripts": {
     "predeploy": "npm run build",
     "deploy": "gh-pages -d dist"
   }
   ```
   Add a `homepage` field at the top level of `package.json`:
   ```json
   "homepage": "https://your-username.github.io/hamzadenizyilmaz-com"
   ```
   Replace `your-username` with your GitHub username.

3. **Push the Repository to GitHub**  
   If you haven’t already, initialize a Git repository (if not already done) and push it to GitHub:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/your-username/hamzadenizyilmaz-com.git
   git push -u origin main
   ```

4. **Deploy to GitHub Pages**  
   Run the deploy command:
   ```bash
   npm run deploy
   ```
   This builds the project and pushes the `dist` folder to a `gh-pages` branch in your repository.

5. **Enable GitHub Pages**  
   - Go to your repository on GitHub (`https://github.com/your-username/hamzadenizyilmaz-com`).
   - Click the **Settings** tab.
   - Scroll to the **Pages** section.
   - Under **Source**, select the `gh-pages` branch and `/ (root)` folder.
   - Click **Save**.
   - After a few minutes, your website will be live at `https://your-username.github.io/hamzadenizyilmaz-com`.

6. **Verify Deployment**  
   Visit the URL above to ensure the website is live. Check the browser console (F12 → Console) for any errors if the site doesn’t load correctly.

## Custom Domain Setup
To use your custom domain (`hamzadenizyilmaz.com`):

1. **Create a CNAME File**  
   In the root of your project, create a file named `CNAME` (no extension) with the following content:
   ```
   hamzadenizyilmaz.com
   ```
2. Commit and push the `CNAME` file to the `gh-pages` branch:
   ```bash
   git add CNAME
   git commit -m "Add CNAME for custom domain"
   npm run deploy
   ```

3. **Configure DNS Settings**  
   Log in to your domain registrar (e.g., GoDaddy, Namecheap) and update the DNS settings:
   - Add a `CNAME` record:
     - Name: `www`
     - Value: `your-username.github.io`
   - Add `A` records pointing to GitHub Pages’ IP addresses:
     - Name: `@`
     - Values: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - (Optional) If you want to use the apex domain (`hamzadenizyilmaz.com`) without `www`, configure an `ALIAS` or `ANAME` record if supported by your registrar.

4. **Enable Custom Domain in GitHub Pages**  
   - In your repository’s **Settings** → **Pages**, under **Custom domain**, enter `hamzadenizyilmaz.com`.
   - Check **Enforce HTTPS** to ensure secure connections.
   - Save the settings.

5. **Wait for DNS Propagation**  
   DNS changes may take up to 24–48 hours to propagate. Use a tool like [dnschecker.org](https://dnschecker.org/) to verify.

## Folder Structure
Here’s a detailed breakdown of the project’s folder structure:
```
hamzadenizyilmaz-com/
├── public/                    # Static assets
│   ├── favicon.ico            # Website favicon
│   ├── images/                # Images used in the website
│   └── fonts/                 # Custom fonts (if any)
├── src/                       # Source code
│   ├── assets/                # Assets like images or icons used in code
│   ├── components/            # Reusable React components (e.g., Header, Footer)
│   ├── pages/                 # Page components (e.g., Home, About, Projects)
│   ├── styles/                # CSS, SCSS, or Tailwind CSS files
│   ├── App.js                 # Main React app component
│   ├── index.js               # Entry point for the React app
│   └── index.css              # Global styles
├── dist/                      # Production build output (generated)
├── .gitignore                 # Files/folders to ignore in Git
├── package.json               # Project metadata and dependencies
├── vite.config.js             # Vite configuration file
├── README.md                  # This documentation file
└── CNAME                      # Custom domain file (optional)
```

## Technologies Used
This project uses a modern web development stack inspired by `erslly/erslly-v3`:
- **React**: A JavaScript library for building interactive user interfaces.
- **Vite**: A fast build tool and development server with HMR support.
- **Node.js & npm**: For dependency management and running scripts.
- **Tailwind CSS** (optional): For responsive, utility-first styling.
- **GitHub Pages**: For free, reliable hosting.
- **ESLint** (optional): For code linting and maintaining code quality.
- **Prettier** (optional): For consistent code formatting.

## Customizing the Website
To personalize the website:
1. **Update Content**:
   - Edit `src/pages/` files to modify page content (e.g., `Home.js`, `About.js`).
   - Update `public/images/` to replace images like logos or project screenshots.
   - Modify `src/styles/` or `index.css` to adjust styles.

2. **Add New Pages**:
   - Create a new file in `src/pages/` (e.g., `Blog.js`).
   - Add routing in `src/App.js` using React Router (if used):
     ```jsx
     import { BrowserRouter, Routes, Route } from 'react-router-dom';
     import Blog from './pages/Blog';
     <BrowserRouter>
       <Routes>
         <Route path="/blog" element={<Blog />} />
       </Routes>
     </BrowserRouter>
     ```

3. **Update Metadata**:
   - Edit `public/index.html` to update the `<title>`, meta description, or favicon.
   - Example:
     ```html
     <title>Hamza Deniz Yılmaz - Portfolio</title>
     <meta name="description" content="Personal portfolio of Hamza Deniz Yılmaz showcasing projects and skills.">
     ```

4. **Add Analytics** (optional):
   - Integrate Google Analytics or similar by adding their script to `public/index.html`.
   - Example for Google Analytics:
     ```html
     <script async src="https://www.googletagmanager.com/gtag/js?id=UA-XXXXX-Y"></script>
     <script>
       window.dataLayer = window.dataLayer || [];
       function gtag(){dataLayer.push(arguments);}
       gtag('js', new Date());
       gtag('config', 'UA-XXXXX-Y');
     </script>
     ```

5. **Test Changes Locally**:
   Always run `npm run dev` to test changes before building and deploying.

## Troubleshooting
Common issues and solutions:
- **npm install fails**: Ensure Node.js is updated, and try `npm cache clean --force` followed by `npm install`.
- **Development server doesn’t start**: Check for port conflicts (`lsof -i :3000` on Linux/Mac) and try a different port in `vite.config.js`:
  ```js
  server: { port: 3001 }
  ```
- **GitHub Pages shows 404**: Verify the `gh-pages` branch exists and is set as the source in GitHub Pages settings.
- **Custom domain not working**: Check DNS settings with `dnschecker.org` and ensure the `CNAME` file is in the `gh-pages` branch.
- **Build errors**: Check the terminal output for specific errors, often related to missing dependencies or syntax issues in JSX/CSS.

For additional help, check the [Vite documentation](https://vitejs.dev/) or [React documentation](https://react.dev/).

## Contributing
Contributions are welcome to improve the website! To contribute:
1. Fork the repository on GitHub.
2. Clone your fork:
   ```bash
   git clone https://github.com/your-username/hamzadenizyilmaz-com.git
   ```
3. Create a feature branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. Make changes and commit:
   ```bash
   git commit -m "Add your feature description"
   ```
5. Push to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```
6. Open a pull request on the original repository with a clear description of your changes.

Please follow the code style used in the project (e.g., ESLint/Prettier rules) and test changes locally before submitting.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact
For questions, feedback, or collaboration:
- **Email**: info@hamzadenizyilmaz.com
- **Website**: [hamzadenizyilmaz.com](https://hamzadenizyilmaz.com)

Thank you for exploring my portfolio repository! I hope this guide helps you set up and customize your own website. 🌟
