# Webchat Anonymous Logout
**A single HTML page to logout anonymous users in Helpshift Webchat.**

By default, Helpshift doesn't log out anonymous users and CORS prevents deleting cookies from other domains. The JS on this page creates a cookie containing a random GUID that is used as the userID in Helpshift. The cookie expires after the Helpshift conversation ends or after 20 minutes. Right now the page is set to automatically refresh after 30 minutes. In normal use cases this will remove the previous conversation from view after the user refreshes the page or leaves the browser. 

## Testing Setup 
### Add your Helpshift Information
1) Add your PLATFORM_ID and DOMAIN to the Widget Code (Lines 24 and 25)

### Running Locally
You will need to use a webserver to run Helpshift webchat. You can run one locally using Python
1) From the command line, navigate to the folder holdering your HTML 
2) Enter the following syntax exactly: 
```
python -m http.server
```

## Before Using this in Production
1) Implement a backend GUID generator - Math.random is not considered a quality random number generator
2) Implement [Helpshift User Identity Verification](ttps://developers.helpshift.com/web-chat/users/#configuring-identity-verification)
