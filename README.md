# Anypoint-CLI Installation and Usage Details

**Note**: In Windows, it's recommended to use the command prompt only (Not PowerShell/Git Bash or any other CLI).

**Prerequisites**:

- Node.js installation (latest/LTS Version recommended)
- Git

**Installation Steps**:

1. Install the AnyPoint CLI:
    ```
    npm install -g anypoint-cli@latest
    ```

2. Create the credentials file:
   ```
   C:/Users/<user-name>/.anypoint/credentials
   ```

3. Configure the credentials file according to your need:
   ```json
   {
    "default": {
     "username": "salman_test4" <-- THIS IS THE BARE MINIMUM CONFIG YOU NEED
    },
    "otherProfile": {
     "username": "",
     "password": "",
     "organization": "",
     "environment": "",
     "host": ""
    },
    "connAppProfile": {
     "client_id": "",
     "client_secret": "",
     "organization": "",
     "environment": "",
     "host": ""
    }
   }
   ```
   - Save it.

4. Open CMD (for Windows) from any directory and run the following command to launch the Anypoint CLI:
   ```
   $ anypoint-cli
   ```
   If the 'password' key is not configured in the credentials file, it will prompt for the password.

5. Once authenticated, you can use the 'help' command to see all the available commands, their flags, options, etc. Alternatively, you can always refer to the Mule official docs for command-related help.

   For example, here's a simple command to restart a CloudHub application:
   - `runtime-mgr cloudhub-application restart <app-name>`
   - `runtime-mgr cloudhub-application restart "get-ip-headers"`

**Note**: You can set your authentication credentials using commands as well. Follow this link for the same - [Authentication with AnyPoint CLI](https://docs.mulesoft.com/anypoint-cli/4.x/auth#credentials-file)

**Note**: Set the ANYPOINT_PROFILE environment variable to tell the CLI agent which authentication profile (eg.: otherProfile, connAppProfile) to use in the credentials file. Without the ANYPOINT_PROFILE environment variable set, it uses the default one.

**Recommended Authentication Mechanism**: Connected App Creds (Client ID and client secret)
