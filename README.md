Squiz Matrix Multiple File Upload jQuery Plugin
=============

This plugin is for the `Squiz Matrix` CMS and when used in conjunction with an `Asset Builder` you can have simple and beautiful multiple file upload using jQuery and javascript.

How It Works
---

1. Create an `Asset Builder`.
2. Configure `Asset Types to Create`. Choose only the types that you want to be allowed to upload.
3. Set the `Create Location`.
4. Add `%create_form%` to the `Logged In` or `Not Logged In` bodycopy.
5. Include `jquery.matrixupload2.js` and `matrixupload2.css` in your page or `Design` file. Optionally include [Font Awesome](http://fortawesome.github.io/Font-Awesome/) if you want icons to be used for various asset types (recommended).
6. Include the plugin:

In the `Logged In` or `Not Logged In` bodycopy add the following script:

```javascript
$('form[id*="asset_builder"]').matrixUpload();
```

Additional options can be included if you want to change the layout or use some of the callbacks:

```javascript
$('form[id*="asset_builder"]').matrixUpload({
    progress: function(progress) {
        console.log(progress);	
    },
    filesSelected: function(files) {
        console.log(files.length);	
    }
});
```
**Make sure to call the plugin inside of the `jQuery` [ready method](http://api.jquery.com/ready) so that the DOM will be fully loaded.**

Options
---

The full list of options that can be used:

| Option     | Default   | Type  | Description  |
| :------------- | :-------------| :----- | :----- |
| hideMatrixLabels | true  | boolean | Hides all labels that the Asset Builder includes. |
| showAttributes   | false | boolean | Shows attribute fields for each file. |
| uploadOnSelected | true  | boolean | If the files should upload after they are chosen. Else use an upload button. **NOT READY FOR USE** |
| layoutType       | ZSSMatrixLayoutGrid | string | Which layout to use. Options are `ZSSMatrixLayoutGrid` and `ZSSMatrixLayoutList`. |
| numColumns       | 6     | number  | How many columns to use for the desktop layout. Mobile and tablet done automatically. |
| errorFileTooLarge | File size too large to upload | string | Label to use when a file is too large to upload |
| uploadButtonTitle | Upload Files | string | Label to use for the upload button |

Callbacks

| Callback     | Returned objects  | Description  |
| :------------- | :-------------| :----- | :----- |
| filesSelected | files |  Called when files are selected or dropped |
| progress | progress |  Progress of the upload |
| start | e |  When the upload starts for a file |
| complete | e |  When the upload completes for a file |
| failed | e |  When the upload fails for a file |
| cancelled | e |  When the upload is cancelled for a file |


Requirements
--------------
`MatrixUpload2` requires `jQuery 1.7` or later.
