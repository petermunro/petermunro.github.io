# Getting Started


> Ensure that you have node.js and npm: run: `node -v`
> and `npm -v`. These should be at least node 6.9.x
> and npm 3.x.x.

1. Check that Angular CLI is installed:

       $  ng -v

   This should display a version message.

2. Use Angular CLI to create a new project:

       $ ng new my-app

   This takes some time.

3. Once it is complete, run your app:

       $ cd my-app
       $ ng serve --open


## Modify your App

1. Edit `src/app/app.component.ts` and add a field after `title`:

        ...
        export class AppComponent {
          title = 'My First Angular App';
          name = 'John Doe';
        }

2. This component uses an external template to display its data. Where is this template located?

3. Edit the template to display your field using "interpolation":

        ...
        </h1>
        <p>
          An application by {{name}}.
        </p>
        ...

4. Check your web browser to ensure that the changes have been made.


## Exploring the Project Tree

The project tree looks something like this:

```
.
├── README.md
├── dist/
├── e2e/
├── karma.conf.js
├── package.json
├── protractor.conf.js
├── src/
│   ├── app/
│   │   ├── app.component.css
│   │   ├── app.component.html
│   │   ├── app.component.spec.ts
│   │   ├── app.component.ts
│   │   └── app.module.ts
│   ├── assets/
│   ├── environments/
│   ├── favicon.ico
│   ├── index.html
│   ├── main.ts
│   ├── polyfills.ts
│   ├── styles.css
│   ├── test.ts
│   ├── tsconfig.app.json
│   ├── tsconfig.spec.json
│   └── typings.d.ts
├── tsconfig.json
├── tslint.json
└── yarn.lock
```

The top level contains configuration files, while sources are of course in the `src` folder.

Answer the following:

1. What's the name of the element in the `<body>` of `src/index.html`?
2. In `src/main.ts`, what's the name of the parameter passed to `platformBrowserDynamic().bootstrapModule()`?
3. In which file would you place global styles?
   - Which `.json` file configures the name of this CSS file?


## Exploring Angular CLI

Using the [Angular CLI wiki](https://github.com/angular/angular-cli/wiki), answer the following:

1. How would you create a production build for your app?
2. How would you have `ng serve` run on a different port?
3. What's the difference between `ng test` and `ng e2e`?
