# Angular phonecat upgrade steps


## Overview

https://angular.io/docs/ts/latest/guide/upgrade.html#!#phonecat-upgrade-tutorial

## Run the project on your box
1. npm run tsc  // don't skip this step
2. npm start    // this task contains package install 
3. load in browser: localhost:8000

## Steps
- [x] 1. Switching to TypeScript
- [x] 2. Installing Angular
- [x] 3. Bootstrapping a hybrid PhoneCat
- [x] 4. Upgrading the Phone service
- [ ] 5. Upgrading Components
- [ ] 6. AoT compile the hybrid app
- [ ] 7. Adding the Angular Router and Bootstrap
- [ ] 8. Say Goodbye to AngularJS

```
when running "npm run tsc:w", if you don't have any ts file yet, you would end up TS18003 error. Rename at least one js file to ts before running that command. 
Rename all js files, npm start works fine.
```

```
    first, do this: 
    npm i -g tsd 
    tsd install angular angular-route angular-resource angular-mocks jasmine
    these are helper for vscode to understand angular typescript
```
 
issue 1: 
after moving index.html file from /app to the root, phone detail route is resolved as 
http://localhost:8000/app/#!/phones/motorola-xoom-with-wi-fi
it should be 
http://localhost:8000/#!/phones/motorola-xoom-with-wi-fi
I just changed href content in phone-list.template.html to make it work again.

Starting spot: 
"Upgrading Components"

This time we only convert one component component phone-list to angular 2. 

Ending spot:
"Now set the remaining phone-detail.component.ts as follows:"

Notes: 
got an error when loading the site: 
js code: Object.defineProperty(exports, "__esModule", { value: true });
error: exports is not defined.
Refer to Trouble shooting session


## Trouble shooting

when running npm run tsc, if error ts2304 (cannot fine name 'Set', ...) shows up, run this command:
```
npm install @types/jasmine @types/angular  @types/angular-animate @types/angular-cookies @types/angular-mocks @types/angular-resource @types/angular-route @types/angular-sanitize --save-dev
```

issue: related to Object.defineProperty(exports, "__esModule", { value: true });
```
typescript 2.2.1 compiles this line with weird result. 
import { Phone, PhoneData } from '../core/phone/phone.service';
downgrade it to 2.0.10 would solve the problem for now. We will find out if we can change tsc compile setting using the latest compiler to solve this issue.
```

templateUrl relative path:
Upgrade tutorial didn't mention about how to setup the templateUrl path in the right way. Refer to phone-list.component.ts file and "moduleId: module.id," would fix this problem.


