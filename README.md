# Angular Material MDC Migration
After migrating to the latest Material Design Components (MDC), a lot of projects are facing issues with styles, and my project is one of them. Therefore, we decided to write about how we fixed it.

We understand that the core of the problem is that we created components on top of Material Components, Modified it for our use cases.

# Steps to MDC Migration

1. Upgrade Angular, Material and run mdc-migration script provided by material team.
You can copy this code and create a batch file and run it or just run each step one by one.
```cmd
@ECHO OFF
call npm i typescript@4.8.x --force
echo Updating Zone JS, Flexlayout, eslint and other related versions which matches new Angular version...
call npm i zone.js @angular/flex-layout@15.0.0-beta.42 @angular-eslint/builder@15.x @angular-eslint/eslint-plugin@15.x @angular-eslint/eslint-plugin-template@15.x @angular-eslint/schematics@15.x @angular-eslint/template-parser@15.x  --force
call npx ng update @angular/core@15 @angular/cli@15 --allow-dirty --force
call npx ng update @angular/material@15 --allow-dirty --force
call npx ng generate @angular/material:mdc-migration
PAUSE
```

2. Update your theme
     ```css
     @use '@angular/material' as mat;
     $ec--mat-typography: mat.define-typography-config(
          $font-family: $aal-font-family,
          $headline-4: mat.define-typography-level($aal-font-h1...),
          $headline-3: mat.define-typography-level($aal-font-h2...),
           ...more settings
     );
     / *This is new way of defining a theme from Angular 15 */
    $ec--mat-light-theme: mat.define-light-theme((
      color: (
          primary: $aal--mat-primary-color,
          accent: $aal--mat-accent-color,
          warn: $aal--mat-warn-color
      ),
      typography: $aal--mat-typography,
      density: -1, // you can play around densities, which suits your application
      ));

      @include mat.typography-hierarchy($ec--mat-typography);
      @include mat.core();
      /**
        Important to include all component themes in body
       */
      body{
          @include mat.all-component-themes($aal--mat-light-theme);
          @include mat.button-density(-2); // these densities makes more sense for my project, feel free to play around
          @include mat.icon-button-density(-2); // these densities makes more sense for my project, feel free to play around
        }
    ```
  
3. Search across your application and replace the following classes, if you used it. 

Comprehensive list of classes which are not automatically  migrated by "ng generate @angular/material:mdc-migration"

| Component | Old Class | New Class |
| --- | --- | ---|
| mat-tab | mat-tab-label-active | mdc-tab--active|
||mat-tab-label-content	| mdc-tab__content |
||mat-tab-label-container	|mat-mdc-tab-label-container|
|| mat-tab-list |	mat-mdc-tab-list|
||mat-tab-body-wrapper |	mat-mdc-tab-body-wrapper|
||mat-tab-label|	mat-mdc-tab|
||mat-tab-header-pagination-controls-enabled |	mat-mdc-tab-header-pagination-controls-enabled|
||mat-tab-header-pagination	|mat-mdc-tab-header-pagination|
||mat-tab-labels	| mat-mdc-tab-labels|
|mat-chip|mat-chip-list	| mat-mdc-chip-list|
||mat-chip-list-wrapper |	mat-chip-list-wrapper|
|mat-checkbox|mat-checkbox-frame	| mdc-checkbox__checkmark|
||mat-checkbox-label|	mdc-label|
||mat-checkbox-checked	| mat-mdc-checkbox-checked|
||mat-checkbox-label|mdc-label|
||mat-checkbox-layout|-|
|mat-button|mat-button-focus-overlay|mat-mdc-focus-indicator|
|mat-radio|mat-radio-outer-circle	| mdc-radio__outer-circle|
||mat-radio-inner-circle	| mdc-radio__inner-circle|
||mat-radio-checked|	mat-mdc-radio-checked|
||mat-radio-label-content|	mdc-label|
||mat-radio-label|mdc -label|
|mat-progress-bar|mat-progress-bar-buffer |	mdc-linear-progress__buffer|
|mat-form-field|mat-form-field-flex | mat-mdc-form-field-flex|
||mat-form-field-wrapper	| mat-mdc-text-field-wrapper|
||mat-form-field-underline|	mdc-line-ripple|
||mat-form-field-subscript-wrapper	| mat-mdc-form-field-subscript-wrapper|
||mat-form-field-prefix	| mat-mdc-form-field-text-prefix|
||mat-form-field-suffix	| mat-mdc-form-field-text-suffix|
||mat-form-field-infix	| mat-mdc-form-text-infix|
||mat-form-field-label	| mat-mdc-floating-label|
|mat-dialog|mat-dialog-container	| mdc-dialog__container|
||mat-dialog-content	| mat-mdc-dialog-content|
|No Change|||
||mat-button-toggle||
||mat-button-toggle-checked||
||mat-button-toggle-disabled||
||mat-button-toggle-focus-overlay||


> Note: Please feel free to Comment in case if you find any class replacements, which might help other projects.
