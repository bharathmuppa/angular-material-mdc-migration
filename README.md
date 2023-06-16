# Angular Material Mdc Migration
Comprehensive list of classes which are not migrated by "ng generate @angular/material:mdc-migration"

# Mat Tab:
- mat-tab-label-active to mdc-tab--active
- mat-tab-label-content to mdc-tab__content
- mat-tab-label-container to mat-mdc-tab-label-container
- mat-tab-list to mat-mdc-tab-list
- mat-tab-body-wrapper to mat-mdc-tab-body-wrapper
- mat-tab-label to mat-mdc-tab
- mat-tab-header-pagination-controls-enabled to mat-mdc-tab-header-pagination-controls-enabled
- mat-tab-header-pagination to mat-mdc-tab-header-pagination
- mat-tab-labels to mat-mdc-tab-labels

# Chip:
- mat-chip-list to mat-mdc-chip-list
- mat-chip-list-wrapper to mat-chip-list-wrapper

# Checkbox:
- mat-checkbox-frame to mdc-checkbox__checkmark
- mat-checkbox-label to mdc-label
- mat-checkbox-checked to mat-mdc-checkbox-checked

# Button Text:
- mat-button-focus-overlay to mat-mdc-focus-indicator

# Radio Button:
- mat-radio-outer-circle to mdc-radio__outer-circle
- mat-radio-inner-circle to mdc-radio__inner-circle
- mat-radio-checked to mat-mdc-radio-checked
- mat-radio-label-content to mdc-label
- mat-radio-label to mdc -label


# Progress Bar:
- mat-progress-bar-buffer to mdc-linear-progress__buffer

# Form Fields:
- mat-form-field-flex to mat-mdc-form-field-flex
- mat-form-field-wrapper to mat-mdc-text-field-wrapper
- mat-form-field-underline to mdc-line-ripple
- mat-form-field-subscript-wrapper to mat-mdc-form-field-subscript-wrapper
- mat-form-field-prefix to mat-mdc-form-field-text-prefix
- mat-form-field-suffix to mat-mdc-form-field-text-suffix
- mat-form-field-infix to mat-mdc-form-text-infix
- mat-form-field-label to mat-mdc-floating-label

# No Change:
- mat-button-toggle
- mat-button-toggle-checked
- mat-button-toggle-disabled
- mat-button-toggle-focus-overlay

# Removed:
- mat-checkbox-layout

# Unknowns:
- mat-checkbox-inner-container

