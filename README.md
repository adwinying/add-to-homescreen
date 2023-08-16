# Add to Homescreen 📱
Adding to Home Screen allows mobile websites / PWA's to have nearly full app functionality without registering in the Apple/Google App Stores. 
</br>
The UI Library guides a user to add the website to their home screen on IOS and Android.
</br>
Instructions have been user-optimized and should yield ~85% home screen install rate on IOS and Android.

[Demo implementation (open on your phone) - Aardvark App](https://philfung.github.io).

![demo-ios](https://github.com/philfung/add-to-homescreen/assets/1054593/310488ab-735d-434e-b3bb-f89dde993fa7)


## Installation
Install the package using npm:

```
npm install add-to-homescreen
```

Now test locally:
```
npm run build
npm start
```

## Usage
Follow above installation instructions above to compile JS and CSS.  Then, add to your website:

1. Copy the entire ["dist" folder](https://github.com/philfung/add-to-homescreen/tree/main/dist) over to your codebase or CDN. 
   This folder includes all js,css, and image assets required.

2. Make sure your site has the minimum requirements for installing a web app on homescreen for IOS and Android.
    1. in your root directory, include a square app icon of at least 40 x 40 px specifically named ["apple-touch-icon.png"](https://github.com/philfung/add-to-homescreen/blob/main/apple-touch-icon.png)    
    2. in your root directory, include a web manifest file ["manifest.json"](https://github.com/philfung/add-to-homescreen/blob/main/manifest.json). Reference the manifest in your index HTML file. 
        ```
        = index.html =
        <head>
        ...
        <link rel="manifest" href="manifest.json">
        ..
        </head>
        ```
3. Include the library JavaScript and CSS files in your index HTML file:

    ```
    = index.html =
    <head>
    ...
    <link rel="stylesheet" href="https://your-cdn.com/../dist/add-to-homescreen.min.css">
    <script src="https://your-cdn.com/../dist/add-to-homescreen.min.js"></script>
    ...
    </head>
    ```

4. Call the library on your website.

    ```
    = index.html =
    <script>
    document.addEventListener('DOMContentLoaded', function () {

        window.AddToHomeScreenInstance = new window.AddToHomeScreen(
            {
                appName: 'Aardvark',                                   // Name of the app
                appIcon: 'apple-touch-icon.png',                       // App icon link (square, at least 40 x 40 pixels)
                assetUrl: 'https://your-cdn.com/../dist/assets/img/',  // Link to directory of library image assets 
                showErrorMessageForUnsupportedBrowsers: true,          // Should we prompt users on non-compliant browsers (like IOS Opera) to switch for 'Add to Homescreen' (like IOS Safari)? Default: true.
                allowUserToCloseModal: false                           // Allow user to close the 'Add to Homescreen' message? Not allowing will increase installs. Default: false.
            }
        );
            
        ret = window.AddToHomeScreenInstance.show();                   // show "add-to-homescreen" instructions to user, or do nothing if already added to homescreen
    });
    </script>
    ```
Here's an [example implementation](https://github.com/philfung/add-to-homescreen/blob/main/index.html). 
# Dependencies

No dependencies. This is written in raw ES6 javascript and all css is namespaced to minimize codebase conflict and bloat.

# License
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# Edge Case Support
Users not on add to homescreen supported mobile browsers or on desktop will be shown a message to redirect to a supported browser.

Desktop users:
<img width="384" alt="error-modal-desktop" src="https://github.com/philfung/add-to-homescreen/assets/1054593/83c07702-15b6-4bd3-a362-1b846ab381a7">

iPhone users:

Android users:


# TODOs
- [ ] Add support for Chrome App on IOS
- [ ] Update Android Chrome instructions for new Chrome release (include "Install App" messaging)
- [ ] README: Add video thumbnails
- [ ] README: Fill in missing url links




