
## Test your code

To test your application in Visual Studio, press **F5** to run your project. The **MainWindow** for your application is displayed:

![Test your application](./media/active-directory-develop-guidedsetup-windesktop-test/samplescreenshot.png)

When you're ready to run your test, use a Microsoft Azure Active Directory account (work or school account) or a Microsoft account (live.com, outlook.com) to sign in. The first time that you run the application, you're prompted to sign in:

![Sign in to the application](./media/active-directory-develop-guidedsetup-windesktop-test/signinscreenshot.png)

### Provide consent for application access
The first time that you sign in to your application, you're prompted to provide your consent to allow the application to access your profile and to sign you in: 

![Provide your consent for application access](./media/active-directory-develop-guidedsetup-windesktop-test/consentscreen.png)

### View application results
After you sign in, you should see the user profile information returned by the call to the Microsoft Graph API. The results are displayed in the **API Call Results** box. Basic information about the token that was acquired via the call to **AcquireTokenAsync** or **AcquireTokenSilentAsync** should be visible in the **Token Info** box. The results contain the following properties:

|Property  |Format  |Description |
|---------|---------|---------|
|**Name** |User's full name |The user’s first and last name.|
|**Username** |<span>user@domain.com</span> |The username that is used to identify the user.|
|**Token Expires** |DateTime |The time at which the token expires. MSAL extends the expiration date by renewing the token as necessary.|
|**Access Token** |String |The token string that is sent to HTTP requests that require an **Authorization** header.|

<!--start-collapse-->
### More information about scopes and delegated permissions

The Microsoft Graph API requires the **user.read** scope to read a user's profile. This scope is automatically added by default in every application that's registered on the registration portal. Other APIs for Microsoft Graph, as well as custom APIs for your back-end server, might require additional scopes. The Microsoft Graph API requires the **Calendars.Read** scope to list the user’s calendars.

To access the user’s calendars in the context of an application, add the **Calendars.Read** delegated permission to the application registration information. Then, add the **Calendars.Read** scope to the **acquireTokenSilent** call. 

>[!NOTE]
>The user might be prompted for additional consents as you increase the number of scopes.

<!--end-collapse-->

[!INCLUDE  [Help and support](./active-directory-develop-help-support-include.md)]
