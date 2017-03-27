# Angular phonecat upgrade steps


## Overview

https://angular.io/docs/ts/latest/guide/upgrade.html#!#phonecat-upgrade-tutorial


## Steps
- [x] 1.1 Switching to TypeScript

when running "npm run tsc:w", if you don't have any ts file yet, you would end up TS18003 error. Rename at least one js file to ts before running that command. 
Rename all js files, npm start works fine.

Next step: https://angular.io/docs/ts/latest/guide/upgrade.html#!#installing-angular
- [ ] 1.2 Installing angular

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

new steps: 
1. add systemjs.config.js, just copy one from 
    https://git.devop.vertafore.com/zhangmi/vap-angular-seed/blob/master/systemjs.config.js

Ending spot:
"Bootstrapping a hybrid PhoneCat"



