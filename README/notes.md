# Installation Setup:

```shell
ng add @angular/material
 - Angular Material
 - Component Dev Kit (CDK)
 - Angular Animation
```

Set up global Angular material typography styles? (Y/N) yes

typography - this gives us access to a lot of class reponsible for spacing, shadows and animations

## steps:

1. go to index.html and remove mat-typography class because angular material does not apply any global CSS, but these will be applied within the components and child elements of a parent. let's remove this class, since we dont looking into this featues.
   and we can see roboto google font added in the index.html
2. go to styles.scss and we can see height 100% applied for html, body and font-family as roboto.
3. go to angular.json and we can see that prebuild theme is configured here under styles array ("@angular/material/prebuilt-themes/indigo-pink.css",), my personal preference is to remove it from here and explicitly import it in our styles.scss file instead.. remove fron build object as well as test object.
   and go to styles.scss and import it like (@import "@angular/material/prebuilt-themes/indigo-pink.css") instead. we don't need to refer node_modules folder as we did in the angular.json file. now we can just get it straight out of the angular material barrel.
4. go to app.module.ts/app.config.ts and we can see BrowserAnimationsModule/provideAnimations has been imported into our application which enables angular's animation system.
5. And lastly but not least, go to package.json, we can see updated dependencies to this file - "@angular/cdk": "^17.0.4", "@angular/material": "^17.0.4".

office document page - https://material.angular.io/

- get started and go to components and we can see the all the components

## demo:

go to button component and then go to examples tab
copy the html <button mat-button>Basic</button> and past it to our project.
it will not work. so, go to api tab and copy the api reference (import {MatButtonModule} from '@angular/material/button';) and import it our module/component

## icons:

https://developers.google.com/fonts/docs/material_icons - this is official page for mat icons

--dry-run - This option is used to simulate the generation process without actually creating files on disk. It allows you to preview what files would be generated and their structure before committing to the generation.
--dry-run as -d (aliases) - it means no changes were made, just we can see how the file path will look like.. what are the changes will make in the cli display.

ng g m shared\material --dry-run --flat

ng g m shared\material --flat - run this command

1. CommonModule, remove the common module since that won't be needed in material module

2. add FormsModule in material module

3. let's go ahead and import all the available modules into our Material Module and complete list can be composed by looking at the angular component repo at github. But instead of doing thatm you could just go ahead and trust me that the following exports is the complete list and you can find this file either at my Github repo for this course (https://github.com/ajtowf/styling-applications-with-angular-material/blob/main/src/app/shared/material.module.ts) or
   among the exercise files here at Pluralsight.
