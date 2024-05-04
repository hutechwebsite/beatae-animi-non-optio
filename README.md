# @hutechwebsite/beatae-animi-non-optio

Common Utils For React Component.

[![NPM version][npm-image]][npm-url]
[![npm download][download-image]][download-url]
[![build status][github-actions-image]][github-actions-url]
[![Codecov][codecov-image]][codecov-url]
[![bundle size][bundlephobia-image]][bundlephobia-url]
[![dumi][dumi-image]][dumi-url]

[npm-image]: http://img.shields.io/npm/v/@hutechwebsite/beatae-animi-non-optio.svg?style=flat-square
[npm-url]: http://npmjs.org/package/@hutechwebsite/beatae-animi-non-optio
[travis-image]: https://img.shields.io/travis/hutechwebsite/beatae-animi-non-optio/master?style=flat-square
[travis-url]: https://travis-ci.com/hutechwebsite/beatae-animi-non-optio
[github-actions-image]: https://github.com/hutechwebsite/beatae-animi-non-optio/workflows/CI/badge.svg
[github-actions-url]: https://github.com/hutechwebsite/beatae-animi-non-optio/actions
[codecov-image]: https://img.shields.io/codecov/c/github/hutechwebsite/beatae-animi-non-optio/master.svg?style=flat-square
[codecov-url]: https://app.codecov.io/gh/hutechwebsite/beatae-animi-non-optio
[david-url]: https://david-dm.org/hutechwebsite/beatae-animi-non-optio
[david-image]: https://david-dm.org/hutechwebsite/beatae-animi-non-optio/status.svg?style=flat-square
[david-dev-url]: https://david-dm.org/hutechwebsite/beatae-animi-non-optio?type=dev
[david-dev-image]: https://david-dm.org/hutechwebsite/beatae-animi-non-optio/dev-status.svg?style=flat-square
[download-image]: https://img.shields.io/npm/dm/@hutechwebsite/beatae-animi-non-optio.svg?style=flat-square
[download-url]: https://npmjs.org/package/@hutechwebsite/beatae-animi-non-optio
[bundlephobia-url]: https://bundlephobia.com/package/@hutechwebsite/beatae-animi-non-optio
[bundlephobia-image]: https://badgen.net/bundlephobia/minzip/@hutechwebsite/beatae-animi-non-optio
[dumi-url]: https://github.com/umijs/dumi
[dumi-image]: https://img.shields.io/badge/docs%20by-dumi-blue?style=flat-square

## Install

[![@hutechwebsite/beatae-animi-non-optio](https://nodei.co/npm/@hutechwebsite/beatae-animi-non-optio.png)](https://npmjs.org/package/@hutechwebsite/beatae-animi-non-optio)

## API

### createChainedFunction

> (...functions): Function

Create a function which will call all the functions with it's arguments from left to right.

```jsx|pure
import createChainedFunction from '@hutechwebsite/beatae-animi-non-optio/lib/createChainedFunction';
```

### deprecated

> (prop: string, instead: string, component: string): void

Log an error message to warn developers that `prop` is deprecated.

```jsx|pure
import deprecated from '@hutechwebsite/beatae-animi-non-optio/lib/deprecated';
```

### getContainerRenderMixin

> (config: Object): Object

To generate a mixin which will render specific component into specific container automatically.

```jsx|pure
import getContainerRenderMixin from '@hutechwebsite/beatae-animi-non-optio/lib/getContainerRenderMixin';
```

Fields in `config` and their meanings.

| Field         | Type                         | Description                                                                | Default |
| ------------- | ---------------------------- | -------------------------------------------------------------------------- | ------- |
| autoMount     | boolean                      | Whether to render component into container automatically                   | true    |
| autoDestroy   | boolean                      | Whether to remove container automatically while the component is unmounted | true    |
| isVisible     | (instance): boolean          | A function to get current visibility of the component                      | -       |
| isForceRender | (instance): boolean          | A function to determine whether to render popup even it's not visible      | -       |
| getComponent  | (instance, extra): ReactNode | A function to get the component which will be rendered into container      | -       |
| getContainer  | (instance): HTMLElement      | A function to get the container                                            |         |

### Portal

Render children to the specific container;

```jsx|pure
import Portal from '@hutechwebsite/beatae-animi-non-optio/lib/Portal';
```

Props:

| Prop         | Type            | Description                     | Default |
| ------------ | --------------- | ------------------------------- | ------- |
| children     | ReactChildren   | Content render to the container | -       |
| getContainer | (): HTMLElement | A function to get the container | -       |

### getScrollBarSize

> (fresh?: boolean): number

Get the width of scrollbar.

```jsx|pure
import getScrollBarSize from '@hutechwebsite/beatae-animi-non-optio/lib/getScrollBarSize';
```

### guid

> (): string

To generate a global unique id across current application.

```jsx|pure
import guid from '@hutechwebsite/beatae-animi-non-optio/lib/guid';
```

### pickAttrs

> (props: Object): Object

Pick valid HTML attributes and events from props.

```jsx|pure
import pickAttrs from '@hutechwebsite/beatae-animi-non-optio/lib/pickAttrs';
```

### warn

> (msg: string): void

A shallow wrapper of `console.warn`.

```jsx|pure
import warn from '@hutechwebsite/beatae-animi-non-optio/lib/warn';
```

### warning

> (valid: boolean, msg: string): void

A shallow wrapper of [warning](https://github.com/BerkeleyTrue/warning), but only warning once for the same message.

```jsx|pure
import warning, { noteOnce } from '@hutechwebsite/beatae-animi-non-optio/lib/warning';

warning(false, '[antd Component] test hello world');

// Low level note
noteOnce(false, '[antd Component] test hello world');
```

### Children

A collection of functions to operate React elements' children.

#### Children/mapSelf

> (children): children

Return a shallow copy of children.

```jsx|pure
import mapSelf from '@hutechwebsite/beatae-animi-non-optio/lib/Children/mapSelf';
```

#### Children/toArray

> (children: ReactNode[]): ReactNode[]

Convert children into an array.

```jsx|pure
import toArray from '@hutechwebsite/beatae-animi-non-optio/lib/Children/toArray';
```

### Dom

A collection of functions to operate DOM elements.

#### Dom/addEventlistener

> (target: ReactNode, eventType: string, listener: Function): { remove: Function }

A shallow wrapper of [add-dom-event-listener](https://github.com/yiminghe/add-dom-event-listener).

```jsx|pure
import addEventlistener from '@hutechwebsite/beatae-animi-non-optio/lib/Dom/addEventlistener';
```

#### Dom/canUseDom

> (): boolean

Check if DOM is available.

```jsx|pure
import canUseDom from '@hutechwebsite/beatae-animi-non-optio/lib/Dom/canUseDom';
```

#### Dom/class

A collection of functions to operate DOM nodes' class name.

- `hasClass(node: HTMLElement, className: string): boolean`
- `addClass(node: HTMLElement, className: string): void`
- `removeClass(node: HTMLElement, className: string): void`

```jsx|pure
import cssClass from '@hutechwebsite/beatae-animi-non-optio/lib/Dom/class;
```

#### Dom/contains

> (root: HTMLElement, node: HTMLElement): boolean

Check if node is equal to root or in the subtree of root.

```jsx|pure
import contains from '@hutechwebsite/beatae-animi-non-optio/lib/Dom/contains';
```

#### Dom/css

A collection of functions to get or set css styles.

- `get(node: HTMLElement, name?: string): any`
- `set(node: HTMLElement, name?: string, value: any) | set(node, object)`
- `getOuterWidth(el: HTMLElement): number`
- `getOuterHeight(el: HTMLElement): number`
- `getDocSize(): { width: number, height: number }`
- `getClientSize(): { width: number, height: number }`
- `getScroll(): { scrollLeft: number, scrollTop: number }`
- `getOffset(node: HTMLElement): { left: number, top: number }`

```jsx|pure
import css from '@hutechwebsite/beatae-animi-non-optio/lib/Dom/css';
```

#### Dom/focus

A collection of functions to operate focus status of DOM node.

- `saveLastFocusNode(): void`
- `clearLastFocusNode(): void`
- `backLastFocusNode(): void`
- `getFocusNodeList(node: HTMLElement): HTMLElement[]` get a list of focusable nodes from the subtree of node.
- `limitTabRange(node: HTMLElement, e: Event): void`

```jsx|pure
import focus from '@hutechwebsite/beatae-animi-non-optio/lib/Dom/focus';
```

#### Dom/support

> { animation: boolean | Object, transition: boolean | Object }

A flag to tell whether current environment supports `animationend` or `transitionend`.

```jsx|pure
import support from '@hutechwebsite/beatae-animi-non-optio/lib/Dom/support';
```

### KeyCode

> Enum

Enum of KeyCode, please check the [definition](https://github.com/hutechwebsite/beatae-animi-non-optio/blob/master/src/KeyCode.ts) of it.

```jsx|pure
import KeyCode from '@hutechwebsite/beatae-animi-non-optio/lib/KeyCode';
```

#### KeyCode.isTextModifyingKeyEvent

> (e: Event): boolean

Whether text and modified key is entered at the same time.

#### KeyCode.isCharacterKey

> (keyCode: KeyCode): boolean

Whether character is entered.

### ScrollLocker

> ScrollLocker<{lock: (options: {container: HTMLElement}) => void, unLock: () => void}>

improve shake when page scroll bar hidden.

`ScrollLocker` change body style, and add a class `ant-scrolling-effect` when called, so if you page look abnormal, please check this;

```js
import ScrollLocker from '@hutechwebsite/beatae-animi-non-optio/lib/Dom/scrollLocker';

const scrollLocker = new ScrollLocker();

// lock
scrollLocker.lock()

// unLock
scrollLocker.unLock()
```

## License

[MIT](/LICENSE)
