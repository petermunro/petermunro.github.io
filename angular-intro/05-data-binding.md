# Using data binding with existing components

What will be the output of the following component?

``` typescript
import { Component } from '@angular/core';

@Component({
  selector: 'property-binding-demo',
  template: `
    <p textContent="initializing?">A paragraph</p>
    <p [textContent]="initializing">A paragraph</p>
    <p [textContent]="'initializing'">A paragraph</p>
    <p bind-textContent="'initializing'">A paragraph</p>
    <p textContent="{{initializing}}">A paragraph</p>
  `,
})
export class PropertyBindingDemoComponent {
  initializing: string = "component instance property";
}
```

Compile and run the component to verify your answers.
