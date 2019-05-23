# iXperience - Full Stack

Welcome to iXperience Full Stack 2019!

[[toc]]

## Command Line / Terminal

### Mac

Change directory to some folder
```bash
cd /some/folder
```

Move back to a parent folder
```bash
cd ..
```

Create a folder called x
```bash
mkdir x
```

List the current directory
```bash
ls
```

Delete a file
```bash
rm ./file
```

Print working directory
```bash
pwd
```

### Windows

Change directory to some folder
```bash
cd /some/folder
```

Move back to a parent folder
```bash
cd ..
```

Create a folder called x
```bash
mkdir x
```

List the current directory
```bash
dir
``` 

Delete folder x
```bash
del x
```

Move or rename folder/file x to y
```bash
move x y
```

## Yarn
__Fast, reliable and secure dependency management tool__

Node.js includes NPM. You can choose to use NPM or Yarn.

Install
```bash
npm install -g yarn
```

Starting a new project
```bash
yarn init
```

Adding a dependency
```bash
yarn add [package]
```

Installing all of the dependencies of a project
```bash
yarn install
```

or 

```bash
yarn
```

Running package.json scripts
```bash
yarn [script]
```

__example__
```bash
yarn start
```

## Git

Copy a repo to your local machine
```git
git clone <url>
```

Find out the status of all your files
```git
git status
```

Bring the code down from your repository
```git
git pull <remote> <branch>

git pull origin master
```

Add all of your changes to be committed
```git
git add -a .
```

Commit your changes to the version history
```git
git commit -m "My cool new version"
```

Push your changes up to the remote
```git
git push <remote> <branch>

git push origin master
```

## Ionic

### Installation

Enter the following command in terminal (make sure you have the lastest version of node.js installed)
```bash
npm install -g ionic
```

::: tip
The -g means it is a global install. For Window’s it's recommended to open an Admin command prompt. For Mac/Linux, run the command with sudo.
:::

## Ionic CLI

### Version

First check the version of Ionic you have just installed
```bash
ionic --version
```

### Creating project

Enter the following command in terminal
```bash
ionic start name-of-your-app
```

::: tip
Assuming your working directory (current directory your terminal is pointing to) is `/Users/me/Documents/ix/full-stack`, the above command would create a new project folder as follows: `/Users/me/Documents/ix/full-stack/name-of-your-app`.
:::

### Run app

Run locally (localhost:8100)
```bash
cd name-of-your-app
ionic serve
```

The browser should open automatically to localhost:8100. If it doesn't, then manually open up your browser and navigate to localhost:8100.


## Open in VSCode

### Open in VSCode

Open up another terminal and `cd` into the project. Type the following command to open the project in Visual Studio Code.
```bash
cd name-of-your-app
code .
```

::: warning
In the previous step we ran `ionic serve` in our terminal. This terminal window is not listening for anymore commands as it is busy serving our Ionic project with a built-in server (more on that later). Therefore, you need to open up a new terminal window (NOTE: you can have many tabs in Terminal on Mac).
:::

::: tip
Alternatively, open up Visual Studio Code manually and open the folder through the app by going to `File > Open...` and selecting your new Ionic project.
:::

## Project Anatomy

### Package.json

Anatomy of package.json
```json{6,15,32}
{
  "name": "fs-resume",
  "version": "0.0.1",
  "author": "Ionic Framework",
  "homepage": "https://ionicframework.com/",
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "test": "ng test",
    "lint": "ng lint",
    "e2e": "ng e2e"
  },
  "private": true,
  "dependencies": {
    "@angular/common": "^7.2.2",
    "@angular/core": "^7.2.2",
    "@angular/forms": "^7.2.2",
    "@angular/http": "^7.2.2",
    "@angular/platform-browser": "^7.2.2",
    "@angular/platform-browser-dynamic": "^7.2.2",
    "@angular/router": "^7.2.2",
    "@ionic-native/core": "^5.0.0",
    "@ionic-native/splash-screen": "^5.0.0",
    "@ionic-native/status-bar": "^5.0.0",
    "@ionic/angular": "^4.1.0",
    "core-js": "^2.5.4",
    "rxjs": "~6.5.1",
    "tslib": "^1.9.0",
    "zone.js": "~0.8.29"
  },
  "devDependencies": {
    "@angular-devkit/architect": "~0.13.8",
    "@angular-devkit/build-angular": "~0.13.8",
    "@angular-devkit/core": "~7.3.8",
    "@angular-devkit/schematics": "~7.3.8",
    "@angular/cli": "~7.3.8",
    "@angular/compiler": "~7.2.2",
    "@angular/compiler-cli": "~7.2.2",
    "@angular/language-service": "~7.2.2",
    "@ionic/angular-toolkit": "~1.5.1",
    "@types/node": "~12.0.0",
    "@types/jasmine": "~2.8.8",
    "@types/jasminewd2": "~2.0.3",
    "codelyzer": "~4.5.0",
    "jasmine-core": "~2.99.1",
    "jasmine-spec-reporter": "~4.2.1",
    "karma": "~4.1.0",
    "karma-chrome-launcher": "~2.2.0",
    "karma-coverage-istanbul-reporter": "~2.0.1",
    "karma-jasmine": "~1.1.2",
    "karma-jasmine-html-reporter": "^0.2.2",
    "protractor": "~5.4.0",
    "ts-node": "~8.1.0",
    "tslint": "~5.16.0",
    "typescript": "~3.1.6"
  },
  "description": "An Ionic project"
}
```

::: tip scripts
The scripts section of the file allows us to add custom commands. For example, we can run `npm run start`, which will then trigger the above `ng serve` command. This is handy for re-usable commands shared across the project.
:::

::: tip dependencies and devDependencies
The above dependencies are installed by running `npm install`. Ionic does this for us automatically. You can find these dependencies inside the `node_modules` folder inside the project.
:::

### Index.html

Anatomy of index.html - SPA: app-root component embeded into html body tag
```html{16}
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title>Ionic App</title>
  <base href="/" />
  <meta name="viewport" content="viewport-fit=cover, width=device-width, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <meta name="format-detection" content="telephone=no" />
  <meta name="msapplication-tap-highlight" content="no" />
  <link rel="icon" type="image/png" href="assets/icon/favicon.png" />
  <!-- add to homescreen for ios -->
  <meta name="apple-mobile-web-app-capable" content="yes" />
  <meta name="apple-mobile-web-app-status-bar-style" content="black" />
</head>
<body>
  <app-root></app-root>
</body>
</html>
```

### app.module.ts

Main enrty point of the app - All components, services and modules must be declaired here
```ts
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { RouteReuseStrategy } from '@angular/router';

import { IonicModule, IonicRouteStrategy } from '@ionic/angular';
import { SplashScreen } from '@ionic-native/splash-screen/ngx';
import { StatusBar } from '@ionic-native/status-bar/ngx';

import { AppComponent } from './app.component';
import { AppRoutingModule } from './app-routing.module';

@NgModule({
  declarations: [AppComponent],
  entryComponents: [],
  imports: [BrowserModule, IonicModule.forRoot(), AppRoutingModule],
  providers: [
    StatusBar,
    SplashScreen,
    { provide: RouteReuseStrategy, useClass: IonicRouteStrategy }
  ],
  bootstrap: [AppComponent]
})
export class AppModule {}

```

### app.component

Main app component: 
app.component.ts
```ts
import { Component } from '@angular/core';

import { Platform } from '@ionic/angular';
import { SplashScreen } from '@ionic-native/splash-screen/ngx';
import { StatusBar } from '@ionic-native/status-bar/ngx';

@Component({
  selector: 'app-root',
  templateUrl: 'app.component.html'
})
export class AppComponent {
  constructor(
    private platform: Platform,
    private splashScreen: SplashScreen,
    private statusBar: StatusBar
  ) {
    this.initializeApp();
  }

  initializeApp() {
    this.platform.ready().then(() => {
      this.statusBar.styleDefault();
      this.splashScreen.hide();
    });
  }
}

```