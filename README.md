# Angular phonecat upgrade steps


## Overview

https://angular.io/docs/ts/latest/guide/upgrade.html#!#phonecat-upgrade-tutorial


## Steps
- [x] 1. Switching to TypeScript
- [x] 2. Installing Angular
- [x] 3. Bootstrapping a hybrid PhoneCat
- [ ] 4. Upgrading the Phone service
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
"Now we can load Angular via SystemJS. We'll add the Angular polyfills and the SystemJS config to the end"

Ending spot:
"This means we are now running both AngularJS and Angular at the same time. That's pretty exciting!"

new steps: 
1. add systemjs.config.js, just copy one from 
    https://git.devop.vertafore.com/zhangmi/vap-angular-seed/blob/master/systemjs.config.js
2. the new file systemjs.config.js doesn't work out of box, made some change    



## Trouble shooting

```
when running npm run tsc, if error ts2304 (cannot fine name 'Set', ...) shows up, run this command:
npm install @types/jasmine @types/angular  @types/angular-animate @types/angular-cookies @types/angular-mocks @types/angular-resource @types/angular-route @types/angular-sanitize --save-dev
```




