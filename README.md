# React Tag Cloud

React component for [Cong Min](https://github.com/cong-min)s [TagCloud](https://github.com/cong-min/TagCloud)

## Installation

```bash
npm install @frank-mayer/react-tag-cloud
```

## Usage

The component can be imported as a named export or as a default export (useful for lazy components).

The `id` property is needed to identify each wrapper element, because there could be multiple instances of the component on the same page. [Cong Min](https://github.com/cong-min)s Code needs a query selector of the wrapping element to work.

The `options` property can modify the behaviour of the tag cloud. You can provide the options as a `object` or as a `function`. If you provide a function, the `window` object will be passed as an argument. This is useful if you want to use the window size to calculate the radius of the tag cloud.

Pass an `Array` of `string`s as children to the component. This will be used as the tags.

```tsx
import React from "react";
import { TagCloud } from "@frank-mayer/react-tag-cloud";
// same as: import TagCloud from "@frank-mayer/react-tag-cloud"

const App = () => (
    <TagCloud
        id="web"
        options={(w: Window & typeof globalThis): TagCloudOptions => ({
            radius: Math.min(500, w.innerWidth, w.innerHeight) / 2,
            maxSpeed: "fast",
        })}
    >
        {[
            "VSCode",
            "TypeScript",
            "React",
            "Preact",
            "Parcel",
            "Jest",
            "Next",
            "ESLint",
            "Framer Motion",
            "Three.js",
        ]}
    </TagCloud>
);
```
