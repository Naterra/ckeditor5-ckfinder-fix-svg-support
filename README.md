# CKEditor 5's CKFinder integration Plugin.

## Fix to support SVG files

Currently, @ckeditor/ckeditor5-ckfinder plugin does not correctly support SVG images.

### Original behavior

SVG image recognized as Link ![image](https://user-images.githubusercontent.com/8204364/96328543-39328500-1012-11eb-9b8e-24e095846534.png)

### Desired behavior

Display as an Image ![image](https://user-images.githubusercontent.com/8204364/96328577-ae9e5580-1012-11eb-9acc-411c6f0ccfa8.png)

### Usage

You can simply comment out import of @ckeditor/ckeditor5-ckfinder plugin and point to fixed solution until they fix this bug.

```
//CKEditorComponent.js 

// @ckeditor/ckeditor5-ckfinder temporary not supporting SVG files
// import CKFinder from '@ckeditor/ckeditor5-ckfinder/src/ckfinder';
import CKFinder from '../../ckeditor5-ckfinder/src/ckfinder';
```

### Installation

1.Download this repo and place somewhere in your project.

2.Install as NPM module

```
npm install Naterra/ckeditor5-ckfinder-fix-svg-support.git
```

edit your component

```
//CKEditorComponent.js 
import CKFinder from 'ckeditor5-ckfinder-fix-svg-support/src/ckfinder';
...

<CKEditor
    editor={ClassicEditor}
    data={value}
    config={{
        plugins:[  CKFinder,  FileRepository,  ...],
        toolbar: [ 'ckfinder', "heading", ...],
        table: {...},
        image: {...},
        ckfinder: { ...	}
    }}
/>
```

## Related Issues
- https://github.com/ckeditor/ckeditor5/issues/5707
