---
id: dxRangeSelector.Options.background.image
type: Object
---
---
##### shortDescription
Specifies image properties.

---
You can display an image as the background of a range selector instead of the default color. Set the image's URL and location using the corresponding properties of the **image** object to do this.

The width of the specified image must be less than or equal to the UI component's [width](/api-reference/10%20UI%20Components/dxRangeSelector/1%20Configuration/size/width.md '/Documentation/ApiReference/UI_Components/dxRangeSelector/Configuration/size/#width').

The height of the specified image must be less than or equal to the following value ("-" stands for subtract): *the UI component's [height](/api-reference/10%20UI%20Components/dxRangeSelector/1%20Configuration/size/height.md '/Documentation/ApiReference/UI_Components/dxRangeSelector/Configuration/size/#height')* - *the scale's [placeholderHeight](/api-reference/10%20UI%20Components/dxRangeSelector/1%20Configuration/scale/placeholderHeight.md '/Documentation/ApiReference/UI_Components/dxRangeSelector/Configuration/scale/#placeholderHeight')*.

If the image size is smaller than the background size, a default background color will be displayed in the remaining area. You can set a custom color (e.g. an empty color) for the background using the **color** property of the **background** configuration object.

#include common-demobutton with {
    url: "https://js.devexpress.com/Demos/WidgetsGallery/Demo/RangeSelector/ImageOnBackground/"
}