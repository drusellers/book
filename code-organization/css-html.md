# CSS / HTML

Some things that I've learned about designing CSS / HTML widgets.

### Components

* They should be built with the idea of taking up all the width possible
* Their width will instead be controlled by the external grid.

## Screens

These are routable to, and should be the target of React Router

## The Layout/Chrome

### A sample layout

```text
<Layout>
    <Nav />
    <Stage><XxxScreen></Stage>
    // or
    <Stage screen={XxxScreen} />
</Layout> 
```

### A Dynamic Nav

```text
<Nav data={data} />

export function Nav(data) => {
  // check if mobile or non-mobile
  if (mobile) {
    <MobileNav {data} />
  } else {
    <ScreenNav {data} />
  }
}
```

Could include a dynamic layout possibly too to account for the sidebar vs hamburger menu. :thinking-face:

