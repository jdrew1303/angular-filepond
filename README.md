# Angular FilePond

Angular FilePond is a handy adapter component for [FilePond](https://github.com/pqina/filepond), a JavaScript library that can upload anything you throw at it, optimizes images for faster uploads, and offers a great, accessible, silky smooth user experience.

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/pqina/angular-filepond/blob/master/LICENSE)
[![npm version](https://badge.fury.io/js/angular-filepond.svg)](https://www.npmjs.com/package/angular-filepond)
[![Donate with PayPal](https://img.shields.io/badge/donate-PayPal.me-pink.svg)](https://www.paypal.me/rikschennink/10)

<img src="https://github.com/pqina/filepond-github-assets/blob/master/filepond-animation-01.gif?raw=true" width="370" alt=""/>

Installation:

```bash
npm install angular-filepond --save
```

Usage:

```js
import { Component, ViewChild } from '@angular/core';

// Register file type validation plugin
import { registerPlugin } from 'angular-filepond';
import FilePondPluginFileValidateType from 'filepond-plugin-file-validate-type/dist/filepond-plugin-file-validate-type.esm.js';
registerPlugin(FilePondPluginFileValidateType);

@Component({
  selector: 'app-root',
  template:  `
    <div class="root">
        <FilePond #myPond 
            name="my-name" 
            className="my-class" 
            labelIdle="Drop files here..."
            allowMultiple="true"
            acceptedFileTypes="image/jpeg, image/png"
            [files]="myFiles" 
            (oninit)="handleFilePondInit()">
        </FilePond>
    </div>
  `
})

export class AppComponent {

  myFiles = ['index.html'];

  // Allows us to get a reference to the FilePond instance
  @ViewChild('myPond') myPond: any;

  handleFilePondInit = () => {

    console.log('FilePond has initialised');

    // FilePond instance methods are available on `this.myPond`

  }
}
```

[Read the docs for more information](https://pqina.nl/filepond/docs/patterns/frameworks/angular/)
