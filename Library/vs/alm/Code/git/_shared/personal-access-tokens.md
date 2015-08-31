ms.ContentId: F3B46B13-319C-4E3B-A8FB-4B6EA4964E2A

0.  Sign in to your Visual Studio Online account (```http://[youraccount].visualstudio.com```).

0.  Go to your team project's home page and open your profile.

   ![Team project home page, my profile](/Library/vs/alm/Code/git/_shared/_img/my-profile.png)

0. Create a new personal access token for this account.

   ![Add a personal access token on the security page ](/Library/vs/alm/Code/git/_shared/_img/add-personal-access-token.png)

0.  Enter the details for this token.

   ![Enter token details](/Library/vs/alm/Code/git/_shared/_img/setup-personal-access-token.png)

0.  Select the [scopes](https://www.visualstudio.com/integrate/get-started/auth/oauth#scopes) that this token authorizes.
   
   ![Select scopes for this token](/Library/vs/alm/Code/git/_shared/_img/select-personal-access-token-scopes.png)

0. After you finish creating the token, make sure to copy the token. 
You'll use this token as your password for your Git tools or application.

   ![Use token as password for your git tools or application](/Library/vs/alm/Code/git/_shared/_img/create-personal-access-token.png)
   
   **Note: Remember that these tokens are your identity. When used, the token is acting as you. 
    Keep your tokens secret and treat them like your password. To help keep your 
    token more secure, consider using the 
    [Windows Credential Store for Git](http://gitcredentialstore.codeplex.com/) 
    so that you don't have to enter your credentials every time you push.**
   
   For example, if you use the Git command prompt to run a Git command, you'll be prompted for a username and password.

   ```
   git clone https://[account].visualstudio.com/DefaultCollection/_git/[team project]
   ```

   Enter a username that does not contain an @ character (for example, Jamal, not fabrikamfiber4@hotmail.com). 
   Use the token that you created as your password.

   ```
   Username for 'https://fabrikam-inc.visualstudio.com': Jamal
   Password for 'https://fabrikam-inc.visualstudio.com': [COPY THE TOKEN HERE]
   ```

0.  When you don't need your token anymore, just revoke the token to remove its access from this account.
