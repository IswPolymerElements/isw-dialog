# \<isw-dialog\>

A paper-dialog with remote-control.

Place your dialog somewhere save from stacking-context, and access it over a remote in your view.

Designed as a workshift solution till the stacking context issues in paper-input are fixed.

```html
<isw-dialog name="myUniqueDialogName" data="{{dataFromRemote}}">
  <h2>Header</h2>
  <paper-dialog-scrollable>
    Lorem ipsum: [[dataFromRemote.someTextProperty]]
  </paper-dialog-scrollable>
  <div class="buttons">
    <paper-button dialog-dismiss>Cancel</paper-button>
    <paper-button dialog-confirm autofocus>Accept</paper-button>
  </div>
</isw-dialog>
```

```html
<isw-dialog-remote
    id="dialogRemote"
    dialog="myUniqueDialogName"
    data="[[dataForDialog]]"
    on-iron-overlay-closed="_closed">
</isw-dialog-remote>
```

```javascript
open() {
  this.$.dialogRemote.open();
}
_closed( event ) {
  console.log( event );
}
```