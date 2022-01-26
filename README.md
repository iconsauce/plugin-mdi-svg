# plugin-mdi-svg

This plugin scrapes Material Design Icons node module `@mdi/svg` icon library to make you use it with `iconsauce`:

```js
module.exports = {
  content: [
    './src/**/*.{tsx,ts}',
  ],
  fontSize: '24px',
  plugin: [
    require('@iconsauce/plugin-mdi-svg'),
  ],
}
```

You will be able to use these icons in your project.

```jsx
const Component = () => {

  const icon = 'mdi/grass'

  return <section className={ icon }>
    <div className="grid desktop:grid-cols-4 mdi/emoticon-happy tablet:grid-cols-2 grid-cols-1 desktop:gap-6 gap-12 desktop:auto-rows-fr desktop:items-end">
      <i className="mdi/access-point"/>
      <span className='bg-adjust-tone-01/24 mgg/terminal'/>
      <div>
        <footer title="mdi/gondola"></footer>
      </div>
    </div>
  </section>
}
export default Component
```

This plug-in will generate only icons used:

```css
@font-face {
  font-family: "iconsauce";
  src: url(data:font/truetype;charset=utf-8;base64,AA...D;);
}
[class^="mdi/"],
[class*=" mdi/"] {
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  font-family: "iconsauce" !important;
  font-size: 24px;
  font-style: normal;
}
.mdi\/access-point::before { content: "\ea01"; }
.mdi\/emoticon-happy::before { content: "\ea02"; }
.mdi\/gondola::before { content: "\ea03"; }
.mdi\/grass::before { content: "\ea04"; }
.mdi\/harddisk::before { content: "\ea05"; }
```
