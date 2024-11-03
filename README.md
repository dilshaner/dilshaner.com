# Setting Up Your Personal Portfolio and Blog with Hugo on Netlify

Welcome to **Dilshaner.com**—a personal portfolio and blog site built using [Hugo](https://gohugo.io) with the **hugo-profile** theme. This guide will walk you through the entire process, from initializing the repository to deploying your site on Netlify with a custom domain.

## Overview

This website showcases a portfolio with sections for **About**, **Experience**, **Projects**, **Education**, and more. The configuration is optimized for professional and personal use, and the site is easily customizable and scalable.

## Project Structure and Setup

### Requirements

1. **Hugo**: Install Hugo by following the instructions [here](https://gohugo.io/getting-started/installing/).
2. **Git**: Ensure you have Git installed on your system. Follow the installation guide [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
3. **Netlify Account**: Sign up for a free account at [Netlify](https://www.netlify.com/).

### Setup Instructions

1. **Clone the Repository**

   Start by cloning this repository to your local machine:

   ```bash
   git clone https://github.com/dilshaner/dilshaner.com.git
   cd dilshaner.com
   ```

2. **Install the Hugo Profile Theme**

   The project uses the `hugo-profile` theme. Install it by running:

   ```bash
   git clone https://github.com/gurusabarish/hugo-profile themes/hugo-profile
   ```

3. **Configure Your Site**

   Open the `config.yaml` file in your favorite text editor and customize the settings according to your preferences. Ensure to update the `baseURL`, `title`, and any other parameters specific to your content.

4. **Add Your Content**

   Create new content pages or posts in the `content` directory. You can use the following command to create a new post:

   ```bash
   hugo new posts/my-first-post.md
   ```

   Edit the newly created markdown file and fill it with your content.

5. **Build Your Site Locally**

   You can preview your site locally by running:

   ```bash
   hugo server
   ```

   Open your browser and go to `http://localhost:1313` to see your site.

6. **Prepare for Deployment**

   Before deploying to Netlify, ensure your site builds correctly by running:

   ```bash
   hugo
   ```

   This command generates your static site files in the `public` directory.

### Deploying to Netlify

1. **Create a New Site on Netlify**

   - Log in to your Netlify account.
   - Click on **"New site from Git"**.

2. **Connect Your Repository**

   - Select your Git provider (e.g., GitHub).
   - Authorize Netlify to access your repository.
   - Choose the repository you just cloned.

3. **Set Build Options**

   In the build settings, specify the following:

   - **Branch to deploy**: `main` (or the branch you're working on)
   - **Build command**: `hugo`
   - **Publish directory**: `public`

4. **Deploy Your Site**

   Click on **"Deploy site"**. Netlify will build and deploy your site. Once the deployment is complete, you will be provided with a temporary Netlify subdomain.

### Adding a Custom Domain

1. **Configure Your Domain**

   - In your Netlify dashboard, go to the **Domain settings** for your site.
   - Click on **"Add custom domain"**.
   - Enter your custom domain name (e.g., `dilshaner.com`) and click **"Verify"**.

2. **Update DNS Settings**

   You will need to update your DNS settings with your domain registrar (like GoDaddy, Namecheap, etc.):

   - Set your domain's **CNAME** record to point to `your-site-name.netlify.app` (the temporary subdomain provided by Netlify).
   - Alternatively, if you're using an apex domain (e.g., `dilshaner.com`), you might need to set an **A** record pointing to Netlify's load balancer IP addresses.

3. **Verify Custom Domain**

   Once the DNS settings propagate (which can take a few minutes to 48 hours), you should be able to access your site using your custom domain. Return to your Netlify dashboard to confirm the custom domain setup.
