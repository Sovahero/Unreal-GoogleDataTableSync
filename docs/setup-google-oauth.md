# Authentication

## Purpose
The editor needs permission to access the same private spreadsheets your Google account can access.

## Recommended approach
Use your own Google access for your team (recommended over Demo). This avoids shared usage limits and gives you control.

Find out more on [OAuth Clients](https://support.google.com/cloud/answer/15549257)

## First‑time entry
- The first time you click `Configure`, you can paste the `Client ID` and `Client Secret`.
- Later, you can update them in `Project Settings → Plugins → Google DataTable Sync`.

<img width="691" height="632" alt="UeGoogleAuthConfig" src="https://github.com/user-attachments/assets/9732b410-26b8-4306-8bf9-ac37e31bc087" />

When the browser confirms success, you can close the tab:

<img width="1015" height="271" alt="AuthSuccessful" src="https://github.com/user-attachments/assets/584b7bf3-8328-4015-925b-1674f7721ee2" />

## Where it is remembered
Your sign‑in is remembered per user for the current project (per‑user settings, not committed to source control).

## Switching account or resetting
Update credentials in Project Settings to switch; the plugin will prompt you to sign in again if the Client ID changes.

---

## Creating your own Google Client ID / Secret (step-by‑step)

This detailed guide shows every click needed to generate your own credentials.

### Step 1: Create a Google Cloud Project

First, we'll create a new project in the Google Cloud Console to house our API settings.

1.  Go to the [Google Cloud Console](https://console.cloud.google.com/).
2.  If you have existing projects, click the project selection dropdown at the top of the page, then click **New project**.

    <img width="1149" height="795" alt="1-NewProject" src="https://github.com/user-attachments/assets/36bef09a-7e12-4e09-a3f5-5eb1032bf802" />

3.  Give your project a name (e.g., "My Game Data") and click **Create**.
  
    <img width="762" height="594" alt="2-NewProject2" src="https://github.com/user-attachments/assets/9a261ca9-a627-4ebc-8a08-d0ea368c1a70" />

### Step 2: Enable the Google Sheets API

Now, we need to activate the specific API that allows our plugin to interact with Google Sheets.

1.  Open the navigation menu (☰) and go to **APIs & Services → Library**.
   
    <img width="749" height="893" alt="3-APIsAndServices" src="https://github.com/user-attachments/assets/e0f74e54-f180-4277-9c31-51d878fc8eca" />

2.  In the search bar, type `Google Sheet` and select the **Google Sheets API** from the results.

    <img width="1891" height="601" alt="4-FindApi" src="https://github.com/user-attachments/assets/1c5bd947-8cbd-4179-8583-6fb4b3167ee0" />

3.  Click the **Enable** button to activate the API for your project.

    <img width="1342" height="777" alt="5-EnableApi" src="https://github.com/user-attachments/assets/5df59ca8-7c87-4362-b730-f3c588b6e00c" />

### Step 3: Configure the OAuth Consent Screen

This screen is what users will see when the plugin asks for permission to access their Google account for the first time.

1.  After enabling the API, navigate to the **OAuth consent screen** tab on the left-hand menu.

    <img width="967" height="549" alt="6-GoToAuthConsent" src="https://github.com/user-attachments/assets/3c3983df-b781-4a04-a3e7-6825854fba33" />

2.  If this is your first time, you may need to click **Get started**.

    <img width="1573" height="825" alt="7-StartAuth" src="https://github.com/user-attachments/assets/23ddc37e-2b92-4220-a932-f1547debecae" />

3.  Fill out the required App Information (App name, User support email, Developer contact). You can leave the rest blank. Click **Save and Continue** through the "Scopes" and "Optional Info" sections.
4.  Choose **External** for the User Type and click **Create**.
5.  On the **Test users** step, add the Google accounts of everyone on your team who will use this plugin. Only these users will be able to sign in while the app is in "Testing" mode.
6.  Once you reach the end of the setup, click the **Create** button on the summary page.

    <img width="818" height="629" alt="8-CreateProject" src="https://github.com/user-attachments/assets/4335c2eb-2735-413e-8442-5109e8a945c7" />

### Step 4: Create the Client ID and Secret

This is the final step, where we generate the actual keys to paste into Unreal Engine.

1.  From the OAuth Overview page, click **Create OAuth client**.

    <img width="1991" height="542" alt="9-NewClient" src="https://github.com/user-attachments/assets/2d2065ee-19ae-48e5-a1f0-af5e3e352ee1" />

2.  In the 'Application type' dropdown, select **Desktop app**. This is a mandatory step for the plugin to work correctly.
3.  Give it a recognizable name (e.g., "Unreal Plugin Desktop Client").
4.  Click **Create**.

    <img width="1200" height="659" alt="10-CreateClient" src="https://github.com/user-attachments/assets/404ba36b-a90c-48a5-b3c2-f52bef194706" />

5.  Your credentials are now created. The list of clients will appear. To view the secret, click the **edit icon (pencil)** on the right.

    <img width="2196" height="401" alt="11-ShowClienfInfo" src="https://github.com/user-attachments/assets/1b4459ac-49b9-4ee7-86f0-6dd16094cd1b" />

6.  You can now see your **Client ID** and **Client secret**. Use the copy icons next to each one. These are the values you will paste into Unreal Engine.

    <img width="1927" height="824" alt="12-CopyClinetInfo" src="https://github.com/user-attachments/assets/9c6b4e52-479a-44ed-a79b-64c1be360714" />

### Step 5: Enter Credentials in Unreal Engine

With the keys copied, return to Unreal Engine.

1.  Open `Project Settings → Plugins → Google DataTable Sync`.
2.  Unchek **UseDemoCredentials**.
2.  Paste the **Client ID** and **Client Secret** into their respective fields.
3.  Ensure the "Redirect Uri" is set to `http://localhost:8080` (this is the default).
4.  Open any DataTable and click `Export` or `Import`. The plugin will now use your new credentials to prompt for a one-time sign-in in your browser.

### Step 6 (Optional): Go to Production

By default, your app is in "Testing" mode, and only the test users you specified can sign in. To allow any user with a Google Account to use your credentials, you can publish the app.

1.  In the Google Cloud Console, navigate back to the **OAuth consent screen** and go to the **Audience** tab.
2.  Click **Publish app**.

    <img width="1084" height="998" alt="13-PublishApp" src="https://github.com/user-attachments/assets/63b52205-bf1f-45c0-a668-21b12b45222a" />

3.  Confirm the action.

    <img width="829" height="371" alt="14-SuccessPublishApp" src="https://github.com/user-attachments/assets/f9586cfa-6f20-451d-9da0-965a5e8031a2" />

!!! tip "You're done!"
    Your project is now fully configured with its own secure credentials. You won't need to do this process again for this project.
