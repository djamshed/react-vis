## Hint

`Hint` is a simple component that shows tooltips inside the chart. `Hint` places itself to the place which is set by your data. In case a custom representation is needed, the component is also able to wrap custom JSX. Here is a short example:

```jsx
<Hint value={myValue}>
  <div style={{background: 'black'}}>
    <h3>Value of hint</h3>
    <p>{myValue.x}</p>
  </div>
</Hint>
```

#### value
Type: `Object`
The data point to show the value at. Hint component will automatically find the place where the data point is and put the hint there.

#### format (optional)
Type: `function`
Format function for a tooltip. Receives the data point, should return an array of objects containing `title` and `value` properties. Each item of an array is shown on a separate line by default.
_Note: please pass custom contents in case if you need different look for the hint._

#### orientation (optional)
Type: `(auto|topleft|topright|bottomleft|bottomright)`
Default: `auto`
The way to align the hint inside the chart. When `auto` is set the hint is trying to stay inside the bounding box of the chart.
Set the hint to `topleft` if you want to see a "conventional" hint alignment.

### Style (optional)
Type: `Object`
You can pass a style object to your Hint component to apply your own styles. See [style](style.md)
```jsx
<Hint value={value} style={{fontSize: 14}}/>
```

Style is a composite component, and individual parts of it can receive different parts.
The different parts are: content, row, title, value. To style a specific part, you can pass an object to the property with that name.
```jsx
<Hint value={value} style={{
  fontSize: 14,
  text: {
    display: 'none'
  },
  value: {
    color: 'red'
  }
}}/>
```
