# CHANGELOG

## v1.2.0

**New features**
- Provide the ability of printing document
- Add new `selectionMode` option indicates the selection mode:

~~~ javascript
import Viewer, { SelectionMode } from '@phuocng/react-pdf-viewer';

<Viewer
    fileUrl="..." 
    // By default, it will be SelectionMode.Text
    selectionMode={SelectionMode.Hand}
/>
~~~

- Add `onDocumentLoad` callback that uis invoked when the document is loaded completely

~~~ javascript
import Viewer, { PdfJs } from '@phuocng/react-pdf-viewer';

const documentLoad = (doc: PdfJs.PdfDocument) => {
    console.log(`Document is loaded: ${doc.numPages}`)
};

<Viewer
    fileUrl="..."
    onDocumentLoad={documentLoad}
/>
~~~

- Add `onZoom` callback that is invoked when zooming in/out the document

~~~ javascript
import Viewer, { PdfJs } from '@phuocng/react-pdf-viewer';

const zoom = (doc: PdfJs.PdfDocument, scale: number) => {
    console.log(`Zoom document to ${scale}`);
};

<Viewer
    fileUrl="/path/to/document.pdf"
    onZoom={zoom}
/>
~~~

## v1.1.0

**New features**
- Add new, optional `defaultScale` parameter that indicates the default zoom level:

~~~ javascript
<Viewer defaultScale={1.5} ... />
~~~

**Improvement**
- The document should fit best in the container initially

## v1.0.2

**Improvement**
- Support SSR

**Bug fixes**
- Cannot re-export a type when --isolatedModules is set to true
- The CSS files are missing in es6 package

## v1.0.0

First release