# PulseMetrics | Google Analytics 4 (GA4) Practical Project

A responsive, single-page web application built to analyze key features of Google Analytics 4 (GA4) by tracking real-time user behavior, traffic sources, engagement patterns, and conversion funnels over HTTPS.

---

## 🚀 Step 1: Get Your Google Analytics Measurement ID

1. Go to [analytics.google.com](https://analytics.google.com/) and sign in with your Google account.
2. If creating an account for the first time:
   - Click **Admin** (gear icon in lower-left).
   - Click **+ Create Account** or **+ Create Property**.
   - Property Name: `PulseMetrics Demo`
   - Select your reporting time zone and currency, then click **Next**.
   - Choose your industry category and business size, then click **Create**.
3. Set up Data Stream:
   - Choose platform: **Web**.
   - Website URL: Enter your GitHub Pages URL (e.g. `https://mannunadkat.github.io/sma_p8`) or a temporary placeholder.
   - Stream name: `PulseMetrics Web Stream`.
   - Click **Create stream**.
4. Copy your **Measurement ID** (Format: `G-XXXXXXXXXX`).

---

## 🛠️ Step 2: Configure the Measurement ID

You have two simple options:

### Option A: Edit Directly in `index.html` (Recommended)
Open `index.html` and locate line 14:
```javascript
const GA_ID = urlParams.get('ga') || storedId || 'G-XXXXXXXXXX';
```
Replace `'G-XXXXXXXXXX'` with your real ID (e.g., `'G-AB12CD34EF'`).

### Option B: Set Dynamically on the Webpage
You can also open the live webpage, type your `G-XXXXXXXXXX` in the top notification bar, and click **Apply GA ID**. It saves automatically in browser storage!

---

## 🌐 Step 3: Host on GitHub Pages (Instant Free HTTPS Link)

To get a live HTTPS URL via GitHub Pages:

1. **Commit your files locally**:
   ```bash
   git add .
   git commit -m "Initial commit of Google Analytics testbed website"
   ```

2. **Create a new GitHub repository**:
   - Go to [github.com/new](https://github.com/new).
   - Repository Name: `sma_p8` (or any preferred name).
   - Set visibility to **Public**.
   - Leave "Add a README" unchecked, then click **Create repository**.

3. **Push to GitHub**:
   ```bash
   git branch -M main
   git remote add origin https://github.com/mannunadkat/sma_p8.git
   git push -u origin main
   ```

4. **Enable GitHub Pages**:
   - In your GitHub repository, go to **Settings** &rarr; **Pages** (under "Code and automation").
   - Under **Build and deployment** &gt; **Branch**:
     - Select branch: `main`
     - Select folder: `/(root)`
     - Click **Save**.
   - Wait 1–2 minutes. GitHub will provide your live secure link:
     ```
     https://mannunadkat.github.io/sma_p8/
     ```

---

## 📊 Step 4: Generating Analytical Insights

Once live, visit the website and interact with the elements. Then open your GA4 Dashboard:

### 1. User Behavior Insights
- **Where to look**: `Reports` &rarr; `Realtime` & `Reports` &rarr; `Engagement` &rarr; `Pages and screens`.
- **Observations to note**:
  - Active users right now and device categories (desktop vs. mobile).
  - Page views (`page_view`), session starts (`session_start`), and user scrolls (`scroll`).

### 2. Traffic Sources
- **Where to look**: `Reports` &rarr; `Acquisition` &rarr; `Traffic acquisition`.
- **How to test**:
  - Visit the URL directly (Direct).
  - Test UTM campaign tags by appending query parameters:
    ```
    https://mannunadkat.github.io/sma_p8/?utm_source=linkedin&utm_medium=social&utm_campaign=lab_experiment
    ```
  - Observe how GA4 categorizes session sources into Organic, Direct, and Social.

### 3. Engagement Patterns
- **Where to look**: `Reports` &rarr; `Engagement` &rarr; `Events`.
- **Tracked Interactions on this site**:
  - `faq_interaction`: Accordion toggles measuring content consumption.
  - `video_engagement`: Simulation of media interaction.
  - `file_download`: Triggered by clicking "Download Study Guide".

### 4. Conversions & Funnels
- **Where to look**: `Reports` &rarr; `Realtime` &rarr; `Event Count by Event Name` and `Reports` &rarr; `Engagement` &rarr; `Conversions`.
- **Key Conversion Events**:
  - `generate_lead`: Submitting the inquiry form with role categorization.
  - `select_item` & `begin_checkout`: Selecting a pricing tier ($0, $29, $99).
  - `sign_up_intent`: Clicking the primary Call to Action (CTA).
- In GA4 Admin &rarr; **Events**, toggle **Mark as conversion** for `generate_lead` and `begin_checkout` to track conversion rates.
