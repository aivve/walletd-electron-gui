## WalletdShell - GUI wallet for Karbo walletd service.


### Features:

This wallet contains the basic functions required to manage your Karbo assets:

* Wallet creation:
  * Create new wallet
  * Import/recover from private keys OR mnemonic seed
* Basic wallet operation/transactions:
  * Open an existing wallet
  * Display wallet addresses & balances
  * Create new address
  * Delete address
  * Display & Backup private keys/seed (for each address)
  * Sending/transferring. Integrated Address or Payment ID are supported. Also provides address lookup from your addressbook
  * Transactions history listing/sorting/searching/detail
  * Incoming transaction notification
  * Export incoming, outgoing, or all transactions to csv file
  * Rescan wallet from specific block height
  * Perform wallet optimization
  * Utilities: generate payment id and integrated address
* Address book:
  * Add/Edit/Delete address entry
  * Listing/sorting/searching existing entries
  * Allow to store same wallet address with different payment id
  * Autosave address after sending to new/unknown recipient
  * Allow to optionally create password protected address book
* Misc:
  * Option to use system tray (on closing/minimizing wallet)
  * Provides list of public nodes
  * Allow to add custom node address
  * Theme: Dark & Light Mode
  * [Keyboard shortcuts](docs/shortcut.md)

NOTE: Because browser can not handle large number of transactions only last are displayed.

### Download &amp; Run WalletdShell

#### Windows:
1. Download the latest installer from this repo
2. Run the installer (`walletdshell-<version>-win-setup.exe`) and follow the installation wizard.
3. Launch WalletdShell via start menu or desktop shortcut.

#### GNU/Linux (AppImage):
1. Download latest AppImage from this repo
2. Make it executable, either via GUI file manager or command line, e.g. `chmod +x walletdshell-<version>-linux.AppImage`
3. Run/execute the file, double click in file manager, or run via shell/command line (See: https://docs.appimage.org/user-guide/run-appimages.html)

#### macOS
1. Download latest archive from this repo
2. Extract downloaded zip archived
3. Run the executable binary (`WalletdShell.app/Contents/MacOs/WalletdShell`)

### Using WalletdShell
Please visit our wiki page: [WalletdShell User Guide](../../wiki).

### Building/Packaging WalletShell
You need to have `Node.js` and `npm` installed, go to https://nodejs.org and find out how to get it installed on your platform.

Once you have Node+npm installed:
```
# assuming you're building it on GNU/Linux
# first, download walletd binary for each platform
# from Karbo 2 official repo
# https://github.com/Karbovanets/karbo/releases
# extract the walletd executable somewhere

# clone the repo
$ git clone https://github.com/aivve/walletd-electron-gui
$ cd walletd-electron-gui

# install dependencies
$ npm install

# create build+dist directory
$ mkdir -p ./build && mkdir -p ./dist

# copy/symlink icons from assets, required for packaging
$ cp ./src/assets/icon.* ./build/

# build GNU/Linux package
$ mkdir -p ./bin/lin
$ cp /path/to/linux-version-of/walletd ./bin/lin/
$ npm run dist-lin

# build Windows package (you need to have wine 2.0+ installed)
$ mkdir -p ./bin/win
$ cp /path/to/win-version-of/walletd.exe ./bin/win/
$ npm run dist-win

# build OSX package
$ mkdir -p ./bin/osx
$ cp /path/to/osx-version-of/walletd ./bin/osx/
$ npm run dist-mac
```

Resulting packages or installer can be found inside `dist/` directory.

### Porting for another coin
Please see [this guide](docs/porting.md) if you want to adapt WalletdShell to be use for your own TurtleCoin fork.


