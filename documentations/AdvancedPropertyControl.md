
# Advanced Property Controls

There are more possibilities in terms of property controls than what the official documentation covers. See below extra gems for Property Controls:

1. [Use the `ControlType.Font`](#controltypefont)
2. [Use the `ControlType.ResponsiveImage`](#controltyperesponsiveimage)
3. [Display Icons in the Property Controls](#icons-in-property-controls)
4. [Get the Property Controls from a component](#get-the-property-controls-from-a-component)


## ControlType.Font
The `ControlType.Font` allow you to use the Official Font Picker

<img width="279" alt="Screenshot 2024-04-17 at 11 43 32" src="https://github.com/VictorienDotNet/Framer-Developer-Gems/assets/5654077/8aea73db-64dd-47ac-b00b-c9a8806d3ba6">

```js
font: {
    //@ts-ignore
    type: ControlType.Font,
    controls: "extended",
    displayFontSize: true,
    displayTextAlignment: false,
    defaultFontType: "monospace",
    defaultValue: {
        fontSize: 14,
        lineHeight: "1.5em"
    },
},
```


## ControlType.ResponsiveImage
The `ControlType.ResponsiveImage` allow you to use the [src](https://www.w3schools.com/tags/att_src.asp), [srcSet](https://www.w3schools.com/TAgs/att_source_srcset.asp), and [alt](https://www.w3schools.com/TAGS/att_alt.asp) HTML attributes from the `<image />` tag, and the `positionX` and `positionY` for the CSS attribute [object-position](https://css-tricks.com/almanac/properties/o/object-position/).

<img width="275" alt="Screenshot 2024-04-17 at 11 42 39" src="https://github.com/VictorienDotNet/Framer-Developer-Gems/assets/5654077/86a21e7b-23d1-4c03-b9f0-76d7d6541a48">

```js
export default function ResponsiveImage({ image, style }) {
    return <img
            {...image} //apply the src, srcSet and alt attribute
            style={{
                ...style,
                objectPosition: `${image.positionX} ${image.positionY}`,
            }}
        />
}

addPropertyControls(ResponsiveImage, {
    image: {
        type: ControlType.ResponsiveImage,
    },
})
```

## ControlType.Cursor
`grabing`, `cursor`
<img width="286" alt="Screenshot 2024-04-30 at 18 53 54" src="https://github.com/VictorienDotNet/Framer-Developer-Gems/assets/5654077/55d683f2-b8b1-4aaf-bcf2-2bd078a9f102">


## ControlType.BoxShadow
`0px 1px 2px 0px rgba(0,0,0,0.25)`
<img width="275" alt="Screenshot 2024-04-30 at 18 54 05" src="https://github.com/VictorienDotNet/Framer-Developer-Gems/assets/5654077/6f9c8fbb-75e4-4d8b-9df4-9e16c2269cd2">

## ControlType.Link
`/contact`
<img width="280" alt="Screenshot 2024-04-30 at 18 54 14" src="https://github.com/VictorienDotNet/Framer-Developer-Gems/assets/5654077/9ae4a4f1-4fe2-4a30-97ad-abcdfc915d38">



## ControlType.Border
<img width="276" alt="Screenshot 2024-04-30 at 18 54 21" src="https://github.com/VictorienDotNet/Framer-Developer-Gems/assets/5654077/7c94a13f-cab0-4ec3-b069-efb2c2538e0b">

## ControlType.BorderRadius
`0px 7px 0px 0px`
<img width="250" alt="Screenshot 2024-04-30 at 18 54 55" src="https://github.com/VictorienDotNet/Framer-Developer-Gems/assets/5654077/aceba171-a5b5-4a1b-b184-e2d8287c3bfe">

## ControlType.padding
`0px 8px 0px 0px`
<img width="249" alt="Screenshot 2024-04-30 at 18 55 03" src="https://github.com/VictorienDotNet/Framer-Developer-Gems/assets/5654077/2adbebf7-b02b-4ce6-a4dd-cb2c06e766a6">


## Icons in Property Controls

Framer display icons on really specific property as Text Alignement or Device Orientation. You can reproduce this Control by mentionning the correct `optionTitles` or `optionIcons`. You can see below the different Property Controls:

### Horizontal
![Horizontal](https://github.com/VictorienDotNet/Framer-Components-Documentaion/assets/5654077/ef4f30f1-5e54-4798-b473-d2c71c542832)

```js
horizontal: {
    type: ControlType.Enum,
    defaultValue: "center",
    options: ["left", "center", "right"],
    optionTitles: ["Left", "Center", "Right"],
    displaySegmentedControl: true,
},
```
### Vertical
![Vertical](https://github.com/VictorienDotNet/Framer-Components-Documentaion/assets/5654077/1c4f0dfb-f63c-45ca-beb7-a484982e36f9)
```js
vertical: {
    type: ControlType.Enum,
    defaultValue: "center",
    options: ["top", "center", "bottom"],
    optionTitles: ["Top", "Center", "Bottom"],
    displaySegmentedControl: true,
},
```
### Text Align Horizontal
![Text Align H](https://github.com/VictorienDotNet/Framer-Components-Documentaion/assets/5654077/e9a8f11a-82b5-42c5-a799-3e59372e5ef5)
```js
textAlignH: {
      type: ControlType.Enum,
      options: ["text-align-left", "text-align-center", "text-align-right"],
      optionIcons: [
          "text-align-left",
          "text-align-center",
          "text-align-right",
      ],
      displaySegmentedControl: true,
},
```
### Text Align Vertical
![Text Align V](https://github.com/VictorienDotNet/Framer-Components-Documentaion/assets/5654077/0a96df8d-bf74-40ca-b50e-09217ef24b20)
```js
textAlignV: {
    type: ControlType.Enum,
    options: ["text-align-top", "text-align-middle", "text-align-bottom"],
    optionIcons: [
        "text-align-top",
        "text-align-middle",
        "text-align-bottom",
    ],
    displaySegmentedControl: true,
},
```
### Directions
![Directions](https://github.com/VictorienDotNet/Framer-Components-Documentaion/assets/5654077/93f844ce-2e77-43ee-a579-541a19fe03e0)
```js
directions: {
    type: ControlType.Enum,
    defaultValue: "Left",
    options: ["left", "right", "top", "bottom"],
    optionTitles: ["Left", "Right", "Top", "Bottom"],
    optionIcons: [
        "direction-left",
        "direction-right",
        "direction-up",
        "direction-down",
    ],
    displaySegmentedControl: true,
},
```

### Direction
![Direction](https://github.com/VictorienDotNet/Framer-Components-Documentaion/assets/5654077/872db1ea-7ea4-4eec-a687-a88bc31691b3)
```typescript
direction: {
    type: ControlType.Enum,
    defaultValue: "horizontal",
    options: ["horizontal", "vertical"],
    displaySegmentedControl: true,
},
```
### Any Direction
![Any Direction](https://github.com/VictorienDotNet/Framer-Components-Documentaion/assets/5654077/d70f53d7-fa2c-4e8e-969a-1aa555c3494d)
```js
anyDirection: {
    type: ControlType.Enum,
    defaultValue: "horizontal",
    options: ["vertical", "horizontal", "both"],
    displaySegmentedControl: true,
},
```
### Alignement
![Alignement](https://github.com/VictorienDotNet/Framer-Components-Documentaion/assets/5654077/dd8bb795-dd81-4720-b943-be200ef4cce1)
```js
alignment: {
    type: ControlType.Enum,
    options: ["flex-start", "center", "flex-end"],
    optionIcons: {
        directions: {
            right: ["align-top", "align-middle", "align-bottom"],
            left: ["align-top", "align-middle", "align-bottom"],
            top: ["align-left", "align-center", "align-right"],
            bottom: ["align-left", "align-center", "align-right"],
        },
    },
    defaultValue: "center",
    displaySegmentedControl: true,
},
```
### Orientation
![Orientation](https://github.com/VictorienDotNet/Framer-Components-Documentaion/assets/5654077/d3f29857-80b2-44e3-b021-224718f945fa)
```js
orientation: {
    type: ControlType.Enum,
    options: ["portrait", "landscape"],
    optionTitles: ["Portrait", "Landscape"],
    optionIcons: ["orientation-portrait", "orientation-landscape"],
    displaySegmentedControl: true,
},
```


## Get the Property Controls from a component
The function `getPropertyControls` lets you get property controls from a Code or Design component. It returns an object that lists each control by their ID:

```js
{
    RgCWTcpQA: {
        defaultValue: true
        title: "Primary"
        type: "boolean"
    }
}

```

For example, you can pass by property controls from Design to Code components. From here, you can add any extra controls and overrides that you would like to apply to your design component:

```js

import { addPropertyControls, ControlType, getPropertyControls } from "framer"
import MyDesignComponent from "https://framer.com/m/MyDesignComponent-d94O.js"

export default function Frame(props) {
    const { content } = props
    //You can modify props here
    return (
        <MyDesignComponent {...props} />
    )
}


addPropertyControls(Frame, {
    //You can add here any extra controls you would like
    ...getPropertyControls(MyDesignComponent),
})
```


## References

1. 💬 [Discussion about Icons in Property Controls](https://www.framer.community/c/developers/how-can-i-get-icons-in-the-enum-property-control)
2. 💬 [Disccusion about ControlType.Font](https://www.framer.community/c/developers/code-component-with-text-control)
3. 💬 [Disccusion about ControlType.ResponsiveImage](https://www.framer.community/c/tutorials/responsive-images-in-code-components)

