# Pdfvuer

> A PDF viewer for Vue using Mozilla's PDF.js

## Install

(WIP)

## Example

(WIP)

## API

### Props

#### :src <sup>String / Object - default: ''<sup>

The url of the pdf file. `src` may also be a `string|TypedArray|DocumentInitParameters|PDFDataRangeTransport` for more details, see [`PDFJS.getDocument()`](https://github.com/mozilla/pdf.js/blob/8ff1fbe7f819513e7d0023df961e3d223b35aefa/src/display/api.js#L117).

#### :page <sup>Number - default: 1<sup>

The page number to display.

#### :rotate <sup>Number - default: 0<sup>

The page rotation in degrees, only multiple of 90 are valid.

#### :scale <sup>Number / String - default: 'page-width' - .sync</sup>

The scaling factor. By default, the pdf will be scaled to match the page width
with the container width.
When passed value `page-width` and / or using `resize` prop, will send back the scale
computed accordingly via `update:scale` event (use it with `scale.sync="scale"`)

#### :resize <sup>Boolean - default: false</sup>

Enable Auto Resizing on window resize. By default, autoresizing is disabled.

#### :annotation <sup>Boolean - default: false</sup>

Show the annotations in the pdf. By default, annotation layer is disabled.

#### :text <sup>Boolean - default: true</sup>

Show the text layer in the pdf. By default, text layer is enabled.

### Events

#### @numpages <sup>Number<sup>

The total number of pages of the pdf.

#### @loading <sup>Boolean<sup>

The provided PDF's loading state

#### @error <sup>Function<sup>

Function handler for errors occurred during loading/drawing PDF source.

#### @link-clicked <sup>Function<sup>

Function handler for errors occurred during loading/drawing PDF source.
Example:

```js
    handle_pdf_link: function (params) {
      // Scroll to the appropriate place on our page - the Y component of
      // params.destArray * (div height / ???), from the bottom of the page div
      var page = document.getElementById(String(params.pageNumber));
      page.scrollIntoView();
    }
```

### Public static methods

#### createLoadingTask(src)

- `src`: see `:src` prop  
  This function creates a PDFJS loading task that can be used and reused as `:src` property.

## License

MIT

## Credits

arkokoley - https://github.com/arkokoley/pdfvuer
