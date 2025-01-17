# Text3D

`<Text3D />` is a component that renders a 3D text. It is a wrapper around the [TextGeometry](https://threejs.org/docs/#api/en/geometries/TextGeometry) class.

<DocsDemo>
  <Text3Demo />
</DocsDemo>

## Usage

To use the `<Text3D />` component you need to pass the `font` prop with the URL of the font JSON file you want to use. TextGeometry uses `typeface`.json generated fonts, you can generate yours [here](http://gero3.github.io/facetype.js/)

```vue
<template>
  <TresCanvas>
    <Text3D
      text="TresJS"
      font="/fonts/FiraCodeRegular.json"
    >
      <TresMeshNormalMaterial />
    </Text3D>
  </TresCanvas>
</template>
```

Notice that you need to pass the `<TresMeshNormalMaterial />` component as a child of the `<Text3D />` component. This is because `<Text3D />` is a `Mesh` component, so it needs a material. The geometry is created automatically. Also you can pass the text as a slot or as a prop like this:

```vue
<template>
  <TresCanvas>
    <Text3D font="/fonts/FiraCodeRegular.json">
      TresJS
      <TresMeshNormalMaterial />
    </Text3D>
  </TresCanvas>
</template>
```

In addition, you can use the power of Vue to add reactivity, but you need to apply the needUpdates prop, for example you can create a reactive value, apply a v-model and make the bound, the Text3D component will update

```vue
<template>
  <input v-model="myReactiveText">
  <TresCanvas>
    <Text3D
      :text="myReactiveText"
      font="/fonts/FiraCodeRegular.json"
      center
      need-updates
    />
  </TresCanvas>
</template>
```

## Props

| Prop               | Description                                                            | Default |
| :----------------- | :--------------------------------------------------------------------- | ------- |
| **font**           | The font data or font name to use for the text.                        |         |
| **text**           | The text to display.                                                   |         |
| **size**           | The size of the text.                                                  | 0.5     |
| **height**         | The height of the text.                                                | 0.2     |
| **curveSegments**  | The number of curve segments to use when generating the text geometry. | 5       |
| **bevelEnabled**   | A flag indicating whether beveling should be enabled for the text.     | true    |
| **bevelThickness** | The thickness of the beveled edge on the text.                         | 0.05    |
| **bevelSize**      | The size of the beveled edge on the text.                              | 0.02    |
| **bevelOffset**    | The offset of the beveled edge on the text.                            | 0       |
| **bevelSegments**  | The number of bevel segments to use when generating the text geometry. | 4       |
| **center**         | To center the text                                                     | false   |
| **needUpdates**    | This props add reactivity                                              | false   |

## References

<a id="1">[1]</a>
This table was generated by [ChatGPT](https://chat.openai.com/chat) based on the Vue component props.
