# Angular Material Mdc Migration
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


