# Phaser 4 - Basic Node JS Template

![License](https://img.shields.io/badge/license-MIT-green)

Forked from the excellent project by [Scott Westover / Dev Share Academy.](https://github.com/devshareacademy/phaser-4-basic-js-template)

A barebones, command line-oriented template for [Phaser 4](https://github.com/photonstorm/phaser) using JavaScript & Node.

**Phaser Version:** `4.1.0`

## Requirements

This template is intended to work without additional baggage of an NPM project. No more error messages about
out of date packages, and installing the whole internet. All you really need is:

- A modern web browser
- A local web server

To build the games, run command line tools and web servers, the below are required:

- Command line
- Editor
- [Node.JS](https://nodejs.org/en/download)

For node follow these command line instructions to install the NVM tool, then use that to install node:

```shell
# Checkout this template from GitHub
git clone git@github.com:sarah-j-smith/phaser-4-basic-js-template.git my-cool-game

# Download and install nvm, if you don't have it
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.8/install.sh | bash

# If you installed nvm start a new shell, or do this instead of restarting the shell
\. "$HOME/.nvm/nvm.sh"

# change into the checked out template
cd my-cool-game 

# Download and install Node.js - this reads the nvmrc file to get the right version
nvm use

# Verify the Node.js version:
node -v # Should print "v24.21.0".
```

## Running Locally

```bash
# This should install a local version of the node package live-server in npm's storage (not in the game)
npx live-server
```

## Writing Code

This template is set up for a modern JavaScript development workflow without any build tools. Simply start your local web server and begin editing the files in the `src` folder. Your changes will be reflected when you refresh your browser.

The main entry point for the application is `src/main.js`.

## Deploying Code

This template includes a bundle script to gather all the necessary files for deployment into a `dist` folder.

To create a distributable bundle, run the following command from the root of the project:

```sh
bash scripts/bundle.sh
```

This will create a `dist` folder containing your game. The contents of this folder can then be uploaded to any static web hosting service. The script will exclude the `src/types` directory from the final bundle.

Since this template required Node.JS the script will use that to minify the project.

### Static Assets

Any static assets like images or audio files should be placed in the `assets` folder. They can then be loaded into your game.

## Updating Phaser

To update the Phaser library in this project, there are three main components that need to be synchronized:

1.  **Documentation:** The Phaser version mentioned at the top of this `README.md`.
2.  **Library Files:** `assets/js/phaser.js` and `assets/js/phaser.min.js`.
3.  **Type Definitions:** `src/types/phaser.d.ts`.

### Manual Update

If you wish to update these files manually:

1.  **Download JavaScript Files:** Fetch the desired version from the jsDelivr CDN:
    - `https://cdn.jsdelivr.net/npm/phaser@VERSION/dist/phaser.js`
    - `https://cdn.jsdelivr.net/npm/phaser@VERSION/dist/phaser.min.js`
      _(Replace `VERSION` with the target version, e.g., `4.1.0`)_
2.  **Download Type Definitions:** Fetch the `phaser.d.ts` file from the Phaser GitHub repository:
    - `https://raw.githubusercontent.com/phaserjs/phaser/refs/tags/vVERSION/types/phaser.d.ts`
3.  **Update README:** Manually update the version number in the `**Phaser Version:**` line at the top of this file.

### Using the Update Script

A convenience script is provided in the `scripts` folder to automate this process.

**To list available Phaser versions (requires npm):**

```bash
./scripts/update-phaser.sh --list
```

**To update to a specific version:**

```bash
./scripts/update-phaser.sh 4.1.0
```

The script will automatically download the required files to their correct locations and update this README.
