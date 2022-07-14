# Minimal-Proton

This repository contains a custom chromeCSS theme for firefox.

Originally forked from [Neikon/AutoColor-Minimal-Proton.](https://github.com/Neikon/AutoColor-Minimal-Proton) 

I just forked and modified some lines to remove the autocolor capability and turned it into a dark mode theme and then added a custom local newtab page.



# Applying Minimal Proton theme
1. Clone the repository
2. Go to `about:config` and turn `toolkit.legacyUserProfileCustomizations.stylesheets` value to `true`.
3. Locate your firefox profile by navigating to `about:support` click the `Open Folder` button beside `Profile Folder` 
5. Extract the chrome folder. The directory should look like this `{profname}\chrome`
6. You're good! Restart the firefox in order to see changes.

# Applying the custom newtab theme
 1. Create file: `C:\Program Files\Mozilla Firefox\defaults\pref\enable-autoconfig.js`
Paste on the file
```
// enable autoconfig
    pref("general.config.sandbox_enabled", false);

pref("general.config.filename", "autoconfig.cfg");
    pref("general.config.obscure_value", 0);
 ```

2) Create file: `C:\Program Files\Mozilla Firefox\autoconfig.cfg`

Paste on the file
```
// set new tab page
var {classes:Cc,interfaces:Ci,utils:Cu} = Components;
aboutNewTabService = Cc["@mozilla.org/browser/aboutnewtab-service;1"].getService(Ci.nsIAboutNewTabService);
aboutNewTabService.newTabURL = "file:///C:/{path_to_file}";
```
3) edit the line newTabURL="" to point to your startpage index.html file. The file:/// is necessary.
4) Remove any extensions that would affect the New Tab Page.
5) Restart Firefox and test.

# Screenshots: 
![image](https://user-images.githubusercontent.com/65537922/179061497-160bfc2f-f917-477d-a82a-9277ea32a338.png)
![image](https://user-images.githubusercontent.com/65537922/179061604-c1b2fa86-4c62-4206-98b5-daf57b66c078.png)

