# Content Builder made easy

This is a (nearly) drag and drop setup for a Steam's content builder

Included is a pre-made build script and depot description, a gitignore file so this can be dropped in your game repository without worry, as well as a few .bat files to get you started (if you're on windows).

## Installation

Download the repository and drop the `content-builder` folder wherever you'd like it to be. The .gitignore file will ensure that even if this is placed within your game's git repository, no unneeded files (including your builds) will clog up commits.

## Setup

There are a few lines of text you'll need to change in order for this to work for your project, so I'll list those out here:
 - `login.bat`: You'll need to change `<username>` to the steam username that will be used to login to steam.
 - `quickbuild.bat`: Again, `<username>` here will need to be changed to the steam username to be used for login.
 - `scripts\depot_build_content.vdf`: You'll need to set the `<depot id>` to the ID of the depot you'll be building to, as found in Steamworks.
 - `scripts\quickbuild.vdf`: Here `<app id>` and `<depot id>` will need to be set to their corresponding ID's as shown in Steamworks. `<branch name>` should be set to the name of the beta branch you'd like to have the build automatically pushed to.
    - Note: `<branch name>` cannot be set to "default", as Steam does not allow automatic pushes of builds to the defualt branch, so you must have a seperate branch to push to. Alternatively, if you do not want the build to automatically go live to any branch, the `"Set Live"` line can be omitted.

After those edits have been made, `login.bat` will also need to be run at least once on any computer that needs to use `quickbuild.bat`. This will ensure that the login credentials for steamcmd are properly cached.

## Use

After you've finished making the necessary edits to the script files, simply place your build contents in the `_build` folder, and run `quickbuild.bat`. Your game will be built and uploaded to Steam!
