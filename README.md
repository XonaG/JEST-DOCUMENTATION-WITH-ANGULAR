![JEST](https://www.xfive.co/wp-content/uploads/2017/03/jest2-1675x1116.jpg)
# JEST DOCUMENTATION WITH ANGULAR 📘

## 📏 What is JEST?

Jest is a delightful JavaScript Testing Framework with a focus on simplicity.

It works with projects using: Babel, TypeScript, Node, React, Angular, Vue and more!

* Jest is a testing platform, widely adapted by many large companies and swiftly adopted by the React community.
* Sits on top of Jasmine, so the API is nearly identical.
* Has all of it’s API documented, along with guides, examples and helpful community on forums like Reactiflux and Stack Overflow.
* Focuses on Developer Experience (speed and ease of use is the first priority.)
* Provides meaningful error messages.
* Runs on Continuous Integration servers without extra tooling (abstracting the DOM with jsdom library.)
* Provides code coverage out of the box.
* Integrates with Babel and TypeScript seamlessly.

And what’s most important is that it provides a smart, immersive watch mode. The watch mode runs only tests affected by git file changes – it also runs failed tests first and is able to bail on first error so the feedback loop is ~10x faster than with Karma, depending on test suite size.

## ⭐ START JEST IN AN ANGULAR PROJECT

### 📌 JEST INSTALLATION IN AN ANGULAR PROJECT

In order to start using Jest in our Angular project, just execute the command: 

```cmd
ng add @briebug/jest-schematic
```

## ⚠️ Important data

* By using this command the Karma configuration and test.ts files will disappear from the project and a new file with the JEST configuration will be created.

* The configuration of jest-preset-angular looks for all files that end in .spec.ts and run them as test files. So we’ll start by setting up our test file, hello-ewe.component.spec.ts

## 👍 ADDITIONAL CONFIGURATION

It is recommended to add the following scripts to the package.json file

```json
{
  "scripts": {
    "test": "jest",
    "test:watch": "jest --watch",
    "test:coverage": "jest --coverage"
  }
}
```

## 🔥 First interaction with JEST

First we have to run the command:

```cmd
npm run test:wacth
```

This will activate all existing automated tests with the .spec.js extension.

When the execution is finished and we see the result of the tests, we can press the W key, and a menu with the following options will appear:

![Menu](./src/assets/img/menu.png)

You select the option you need

## 💗 Benefits of using Jest

* It has a cleaner and better ordered interface with greater detail to test errors.
* One can consider Jest to be an exceptionally well documented and quick performing testing framework.
* A powerful developer tooling is provided by Jest with reduced error-prone code.
* It is also possible for this framework to execute visual regression tests. It captures screenshots for doing this. During the development of an application by using React JS, this particular feature is quite useful for preventing UI bugs. This is done by recording the rendered component’s screenshot and comparing it afterward with components that have been rendered in the future. It is possible to update the screenshots with the addition of new features.
* Run your Angular tests without a browser.
* Run test suite several times faster.
* Rerun instantly only tests related to latest code change.

## 🏮 The Cons

* Not much tooling or libraries are supported by Jest as compared to Jasmine and other frameworks.
* Individuals who are not comfy with this framework have asserted that it is difficult to learn Jest.
* For bigger snapshot files, snapshot testing is not possible with Jest.

## 🧪 Examples of execution with JEST

You will be able to run the sample tests that come in this template and you can get an idea of how you can work with JEST and some of its methods.

If you wish to study JEST in more depth visit [https://www.xfive.co/blog/testing-angular-faster-jest/](https://www.xfive.co/blog/testing-angular-faster-jest/)


Before we start unit testing with jest we need to configure our spec.js test file by adding the following lines of code: 

```javascript
import "zone.js/dist/zone";
import 'zone.js/dist/zone-testing';
import { BrowserDynamicTestingModule, platformBrowserDynamicTesting } from '@angular/platform-browser-dynamic/testing';

TestBed.initTestEnvironment(
  BrowserDynamicTestingModule, platformBrowserDynamicTesting())
```

The imports used in this example are simply used for demonstrative use since you may require a larger number of imports according to your needs.

The following code shows the necessary configuration for our unit test

```javascript
beforeEach(async () => {
    await TestBed.configureTestingModule({
      declarations: [
        AppComponent
      ],
    }).compileComponents();
  });
```
### Examples of tests

In the following test case we ensure that the application has been created correctly.

```javascript
it('should create the app', () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app).toBeTruthy();
  });
```

In the following test case we verify that the title of our page is jest.

```javascript
it(`should have as title 'jest'`, () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app.title).toEqual('jest');
  });
```

In the following test case we verify that the text content of a div is equal to jest app is running!

```javascript
it('should render title', () => {
    const fixture = TestBed.createComponent(AppComponent);
    fixture.detectChanges();
    const compiled = fixture.nativeElement;
    expect(compiled.querySelector('.content span').textContent).toContain('jest app is running!');
  });
```

The final code for our unit test would be as follows:

```javascript
import "zone.js/dist/zone";
import 'zone.js/dist/zone-testing';
import { TestBed } from '@angular/core/testing';
import { BrowserDynamicTestingModule, platformBrowserDynamicTesting } from '@angular/platform-browser-dynamic/testing';
import { AppComponent } from './app.component';

TestBed.initTestEnvironment(
  BrowserDynamicTestingModule, platformBrowserDynamicTesting());

describe('AppComponent', () => {
  beforeEach(async () => {
    await TestBed.configureTestingModule({
      declarations: [
        AppComponent
      ],
    }).compileComponents();
  });

  it('should create the app', () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app).toBeTruthy();
  });

  it(`should have as title 'jest'`, () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app.title).toEqual('jest');
  });

  it('should render title', () => {
    const fixture = TestBed.createComponent(AppComponent);
    fixture.detectChanges();
    const compiled = fixture.nativeElement;
    expect(compiled.querySelector('.content span').textContent).toContain('jest app is running!');
  });
});

```

## 👾 Summary

I was really surprised that it is possible to integrate a third-party testing tool that does not run in the browser, such as Jest, into Angular. A couple of days ago I still thought it would be impossible to do it in a reasonable amount of time and simply not worth the effort, but it turned out to be worth it.

So if you care about your testing experience, do yourself a favor and run Angular tests with Jest. You’ll love it.