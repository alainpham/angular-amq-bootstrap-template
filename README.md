# Angular with AMQ-7 Bootstrap Plotly Template

An Angular 5 project preconfigured with Bootstrap, rhea for messaging with AMQ 7 Broker, plotly.js for charts and plots.

Clone this repo and start from here or follow the steps below to get up and running.

![Screenshot](src/screen.png)

## Prerequisites

* Have npm installed (node)
* Install [angular-cli](https://angular.io/guide/quickstart) : `npm install -g @angular/cli`

* Have AMQ 7 installed and running
	* [Download AMQ version 7.0.0+ here](https://developers.redhat.com/products/amq/download/)
	* unzip package `unzip jboss-amq-7.0.0.redhat-1-bin.zip`
	* create a test instance

			cd jboss-amq-7.0.0.redhat-1/bin
			./artemis create  --user admin --password admin --allow-anonymous Y ./../instances/eventbrk
			cd ./../instances/eventbrk/bin
			./artemis run

## Steps taken to generate this template

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

Create a dummy component and start playing with messages and plots.
