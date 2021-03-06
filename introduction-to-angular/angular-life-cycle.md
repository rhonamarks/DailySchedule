# Angular life cycle

Every component has a life cycle managed by Angular. We have access to key moments such as ngOnChanges\(\) or ngOnInit\(\). For more information, visit the official website

[https://angular.io/guide/lifecycle-hooks](https://angular.io/guide/lifecycle-hooks)

In this section, we are going to use ngOnInit\(\) to set the list of activities

```text
ng generate component activites/list-activites
```

In list-activities.component.ts, add the following code

```typescript
import { Component, OnInit } from '@angular/core';
import { ActivitiesConst } from '../../Data/activities';

@Component({
  selector: 'app-list-activities',
  templateUrl: './list-activities.component.html',
  styleUrls: ['./list-activities.component.css']
})
export class ListActivitiesComponent implements OnInit {
  activitiesList: ActivitiesModel;

  constructor() { }

  ngOnInit() {
    this.activitiesList = ActivitiesConst;
  }
}
```

In list-activities.component.ts, add the following code

```markup
<section id="activity-list">
  <h1> List of activities</h1>
  <article class="activity-item" *ngFor="let activity of activitiesList">
    <i class="fas {{activity.image}} circle-icon"></i>
    <h2>{{activity.name}}</h2>
    <button class="btn-add">+ Add</button>
  </article>
</section>
```

Now add the app-list-activities selector to the activities.component.html

```text
<app-list-activities></app-list-activities> 
```



