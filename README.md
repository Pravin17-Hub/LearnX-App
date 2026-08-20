# LearnX Android Mobile Application

This is the dedicated native Android application container for **LearnX**, built with Capacitor. It is completely isolated from your website codebase to ensure the live web app remains unaffected.

---

## 🚀 How to Build the Installable `.apk`

### Method 1: Using Android Studio (Fastest Local Build)
1. Open **Android Studio**.
2. Click **Open** and select the folder:
   `c:\Users\Dell\Desktop\LearnX-App\android`
3. Wait for Gradle sync to complete.
4. Click on the top menu: **Build** > **Build Bundle(s) / APK(s)** > **Build APK(s)**.
5. Once finished, click **locate** in the popup to find `app-debug.apk` and transfer it to your phone to install!

---

### Method 2: 1-Click Cloud APK Build (GitHub Actions)
1. Initialize git in this folder and push to a new GitHub repository (e.g., `LearnX-App`):
   ```bash
   git init
   git add .
   git commit -m "Initial Android Capacitor Project"
   git branch -M main
   git remote add origin <YOUR_GITHUB_REPO_URL>
   git push -u origin main
   ```
2. Go to the **Actions** tab on your GitHub repository.
3. The **Build Android APK** workflow will automatically run and provide a downloadable **`app-debug.apk`** artifact.

---

## ⚙️ Connecting to your Live Deployed Website
In `capacitor.config.json`, the `server.url` field controls the backend/frontend host:
```json
{
  "appId": "com.learnx.app",
  "appName": "LearnX",
  "server": {
    "url": "https://your-live-learnx-website.com",
    "cleartext": true
  }
}
```
Whenever you update `capacitor.config.json`, run:
```bash
npx cap sync android
```
