[![N|Solid](https://camo.githubusercontent.com/57576c48daefc4d5763df531fea755f6df3d359420ddabf76dc52f19c56bd112/68747470733a2f2f6672616d65776f726b372e696f2f692f6c6f676f2e737667)](https://framework7.io/docs/migration-from-v6-to-v7)

# Framework7 upgrade V6 to V7


Follow these steps:

`1.`Run this command to update your framework7 version to latest version
```sh
npm install framework7@7.0.9
```
`2.`Run this command to update your Dom7 version to latest version
```sh
npm install dom7@4.0.4
```
`3.`the way you import framework7 resources and components is changed based on `package.json` file under section `exports`. So, you need to remove this line
```sh
import 'framework7/framework7-bundle.css';
```
and replace it with this line
```sh
import 'framework7/css/bundle';
```
`4.`Also, the way you import Dom7 is changed. It become inside framework7. So you need to remove this line
```sh
import $ from 'dom7';
```
and replace it with this line
```sh
import { Dom7 } from 'framework7';
```
or with this line, based on what you import from framework7
```sh
import Framework7, { Dom7, getDevice } from 'framework7';
```

`5.` if you make global event like: `$(document).on(event, selector, function(){})`. You must first to load Dom7 from Framework7 then store it inside $ variable like these lines
```sh
import { Dom7 } from 'framework7';
var $ = Dom7;
//then you can use your global events
$(document).on(event, selector, function(){})
```
