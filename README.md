
# ngx-wizard
Simple angular library for creating wizard. For now without styles

[![NPM](https://nodei.co/npm/ngx-wizard.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/ngx-wizard/)

# Prerequisite
 Angular is required.
 Bootstrap is required.

# Installation
#### npm
```
npm install ngx-wizard
```
#### yarn
```
yarn add ngx-wizard
```
# Integration
1. Install library
2. Import Module into the app.module
```ts
import { WizardModule } from "ngx-wizard";

@NgModule({
    imports: [..., WizardModule],
    declarations: [...],
    bootstrap: [...],
    providers: [...]
})
```
3.  Also for now bootstrap is needed.

# Examples
``` html
<wizard nextButtonClass='my-custom-class' prevButtonClass='my-custom-class'>
	<tab [index]="1" previousButton="hidden" [isNextButtonDisabled]='true' nextButton="hidden" icon="iso" class="my_class">
		<!--Any content that you need-->
	</tab>
	<tab [index]="0" (isSelect)="doSomeAction()" nextButton="go next">
		<!--other tab-->
		<!--Any content that you need-->
	</tab>
	<!-- Any anounts of tabs -->
</wizard>
```
# Wizard Options
``` ts
/*Input params*/
 nextButtonClass: string = "pull-right" //=> will add custom class to the nextButton, default class is "btn btn-next btn-fill btn-wd"
 prevButtonClass: string = "pull-left" //=> will add custom class to the previousButton, default class is "btn btn-previous btn-fill btn-default btn-wd"
```
# Tab Options
``` ts
/*Input params*/
 heading = "string" //=> name of tab that will be displayed
 disabled = boolean //=> set enable or disabe tab
 customClass ="string" //=> will add custom class to the header
 icon = "string" //=> name of icon in the material dashboard
 previousButton ="string" //=> name of previous button, if name is "hidden" then won't show this button
 nextButton ="string" //=> name of next button, if name is "hidden" then won't show this button
 index = number //=> ordering for tabs, the lowens index wil be at the start
 active = boolean //=> manually set the active tab
 isNextButtonDisabled = boolean //=> set enable or disabe nextButton

/*Output params*/
isSelect - EventEmitter //=> fires when tab selected
deselect - EventEmitter //=> fires when tab deselected
removed- EventEmitter //=> fires when tab removed
check - EventEmitter //=> fires when tab checked
onContinueClicked - EventEmitter //=> fires when nextButton clicked

```

# GitHub
Please feel free to declare issues or contribute: https://github.com/AlexYaroschuck/ngx-wizard
