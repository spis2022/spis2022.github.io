# OAuth login

To use the following code, you'll need to configure APP_SECRET_KEY, GITHUB_CLIENT_ID and GITHUB_CLIENT_SECRET as shown below.

Example: [https://replit.com/@phtcon/spis2022-0824-try-login-1#main.py](https://replit.com/@phtcon/spis2022-0824-try-login-1#main.py)

# Configuring APP_SECRET_KEY

The value of APP_SECRET_KEY is used to cryptographically sign your sessions.   It can be any string of letters and numbers such as these examples:
* `szifjsSkjhkShjjFdofzsjlvi8ihweifaw3lfhia8`
* `zvjKJHKJsiljzlsdivzlsu2q2o9zojlvdloiqfloivdz`
* `SI8ZVSLsi8hlilvselviSIVSLV`

To set it in a a repl, follow these instructions (as illustrated in the animation below):

![spis-set-app-secret-key](https://user-images.githubusercontent.com/1119017/186516526-dbd19008-5c9f-44c1-aa1b-0bd0e4169298.gif)

# Configuring GITHUB_CLIENT_ID and GITHUB_CLIENT_SECRET

These are configured in the same way as APP_SECRET_KEY, but the values must be obtained from the GitHub Settings for your account.

Here are the instructions and an animation to illustrate the idea.  You will need the URL of your website to proceed (e.g. `https://spis2022-0824-try-login-1.phtcon.repl.co`), i.e. the URL that you type in to bring up your web app in a regular browser (not the URL of your repl interface where you type in the Python code.)

1. Login to GitHub at [https://github.com](https://github.com) and go to Settings
2. Go to Developer Settings (left navigation, near the bottom)
3. Select OAuth Apps
4. Click the New OAuth App button (upper right).
5. Fill in the Application Name with something you'll recognize. This could be the same as your application URL.
6. Fill in the Home Page with your application URL.
7. Fill in the Callback URL with your application URL with `/callback` attached to the end of it.
8. Click Register Application

You will get a value for the GITHUB_CLIENT_ID.  Copy/paste this in for the secret in Repl.

You will need to click to get a value for the GITHUB_CLIENT_SECRET.  Copy/paste this into the secret in Repl also.

At that point, your app should start for login and logout.

![spis-github-client-id-secret](https://user-images.githubusercontent.com/1119017/186519147-360b9672-2e1e-42be-b3a2-d872d9c46554.gif)
