# ng2-dual-selector

An Angular 4 component forked from http://ng2-duallistbox-demo.surge.sh/ 

Uses symbolic titles instead of Glyphicons.

## Demo

http://ng2-duallistbox-demo.surge.sh/

## Installation

To install this library, run:

```bash
$ npm install ng-dual-list-box --save
```

and then from your Angular `AppModule`:

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';

// Import your library
import { DualListBoxModule } from 'ng-dual-list-box';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    DualListBoxModule.forRoot()
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Use it in your template like this. Check the documentation for other available fields, but these are mandatory

```html
<div class="row">
  <div class="col-md-8 col-md-offset-2">
    <ng2-dual-list-box [data]="items" valueField="id" textField="name"
                       (onAvailableItemSelected)="log($event)"
                       (onSelectedItemsSelected)="log($event)"
                       (onItemsMoved)="log($event)"></ng2-dual-list-box>
  </div>
</div>
```

You can also use ngModel and formControlName. When this is used the variable or form control used will have the value of the selected list box.

```html
<div class="row">
  <div class="col-md-8 col-md-offset-2">
    <ng2-dual-list-box [data]="items" valueField="id" textField="name"
                       [(ngModel)]="selected"
                       (onAvailableItemSelected)="log($event)"
                       (onSelectedItemsSelected)="log($event)"
                       (onItemsMoved)="log($event)"></ng2-dual-list-box>
  </div>
</div>
```

```html
<div class="row">
  <div class="col-md-8 col-md-offset-2" [formGroup]="form">
    <ng2-dual-list-box [data]="items" valueField="id" textField="name"
                       formControlName="selected"
                       (onAvailableItemSelected)="log($event)"
                       (onSelectedItemsSelected)="log($event)"
                       (onItemsMoved)="log($event)"></ng2-dual-list-box>
  </div>
</div>
```




## Development

To generate all `*.js`, `*.d.ts` and `*.metadata.json` files:

```bash
$ npm run build
```

To lint all `*.ts` files:

```bash
$ npm run lint
```

## License

MIT © [Eldar Granulo](mailto:eldar32@gmail.com)
