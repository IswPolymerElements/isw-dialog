# \<isw-dialog\>

A paper-dialog with remote-control.

Place your dialog somewhere save from stacking-context, and access it over a remote in your view.

```html
<isw-dialog name="myUniqueDialogName">
  <h2>Header</h2>
  <paper-dialog-scrollable>
    Lorem ipsum...
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