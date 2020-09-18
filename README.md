
### USAGE of Responsive for React

#### Add to top component
```
import { WindowDimensionsProvider } from './components/Responsive'

const App = () => (
  <WindowDimensionsProvider>
    <div className="App">
      <Content items={items} />
    </div>
  </WindowDimensionsProvider>
)
```


#### Use to mount components related to a breakpoint width

```
import { ResponsiveLayout } from './components/Responsive'

const Content = ({ items }) => (
  <ResponsiveLayout
    breakpoint={767}
    renderDesktop={() => (
      <DesktopView items={items} />
    )}
    renderMobile={() => (
      <MobileView items={items} />
    )}
  />
)
```


#### Use width or height as variable for something
```
import { useWindowDimensions } from './components/Responsive'

const DesktopView = ({ items }) => {
  const { width, height } = useWindowDimensions()
  return (
    <div
      className={'tile is-ancestor '
        .concat(width < 1088 ? 'is-vertical' : '')}
    >
      {items.map((item, idx) => (
        <Tile
          key={item.title}
          {...item}
        />
      ))}
    </div>
  )
}
```
