# AngularAmqBootstrapTemplate

An Angular 5 project preconfigured with Bootstrap, rhea for messaging with AMQ 7 Broker, plotly.js for charts and plots.

Clone this repo to start a project

![Screenshot](src/screen.png)

```
ng new angular-amq-bootstrap-template
npm install rhea --save
npm install @ng-bootstrap/ng-bootstrap --save 
npm install bootstrap --save
npm install plotly.js --save
```

Edit src/tsconfig.app.json. Add node to types.

```
{
  "extends": "../tsconfig.json",
  "compilerOptions": {
    "outDir": "../out-tsc/app",
    "baseUrl": "./",
    "module": "es2015",
    "types": ["node"]
  },
  "exclude": [
    "test.ts",
    "**/*.spec.ts"
  ]
}
```

edit .angular-cli.json

```
      "styles": [
        "../node_modules/bootstrap/dist/css/bootstrap.min.css","styles.css"
      ],

      ...

      "scripts": ["../node_modules/plotly.js/dist/plotly.min.js"],
```

edit src/typings.d.ts

```
declare var Plotly: any;
```

edit src/app/app.module.ts
```
import { NgbModule } from '@ng-bootstrap/ng-bootstrap';
import { FormsModule } from '@angular/forms';
...
  imports: [
    BrowserModule, FormsModule, NgbModule.forRoot()
  ],
```