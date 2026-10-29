Deployment Runbook

### Phase 1: Local Setup & Version Control
1. In your project directory, verify your build output (e.g., `index.html` and any assets).
2. Initialize Git and commit all project files:
   ```bash
   git init
   git add .
   git commit -m "feat: initial release of Grady's Garage landing page"
   ```
3. Create a new private repository on GitHub (e.g., `gradys-garage-web`).
4. Link your local repo and push to the `main` branch:
   ```bash
   git remote add origin https://github.com/<your-username>/gradys-garage-web.git
   git branch -M main
   git push -u origin main
   ```

### Phase 2: Deploy to Cloudflare Pages
1. Log in to the [Cloudflare Dashboard](https://dash.cloudflare.com/).
2. In the sidebar, navigate to **Compute (Workers & Pages)** > **Create application** > **Pages** > **Connect to Git**.
3. Select your GitHub account and authorize access to `gradys-garage-web`.
4. Configure the build parameters:
   * **Project name:** `gradys-garage`
   * **Production branch:** `main`
   * **Framework preset:** `None` (for plain HTML/Tailwind) or select your framework (Astro, Vite, etc.).
   * **Build command:** Leave blank for static HTML, or provide the build script (e.g., `npm run build`).
   * **Build output directory:** `/` for static root, or `dist`/`build`.
5. Click **Save and Deploy**. Cloudflare will deploy the project and supply a temporary preview domain (e.g., `gradys-garage.pages.dev`).

### Phase 3: Connect GoDaddy DNS to Cloudflare Pages
1. From your Cloudflare Pages dashboard, go to the **Custom domains** tab and click **Set up a custom domain**.
2. Enter `gradysgarage.com` and select **Continue**.
3. Cloudflare will generate the necessary DNS records.
4. Open a new browser tab, log in to **GoDaddy**, and open **Domain Portfolio** > **gradysgarage.com** > **DNS Management**.
5. Configure the DNS entries:
   * **CNAME Record:**
     * **Name:** `www`
     * **Value:** `gradys-garage.pages.dev`
     * **TTL:** 1/2 Hour (or default)
   * **Apex (Root) Record:**
     * Point the root domain (`@`) to the designated Cloudflare IP address or apex target provided in the Cloudflare dashboard.
6. Remove any default GoDaddy parking records (such as standard GoDaddy parking `A` records pointing to parked IPs).
7. Return to Cloudflare Pages and click **Check DNS**. 
8. Cloudflare will automatically provision a free universal SSL/TLS certificate once DNS propagation begins (typically 5 to 30 minutes).