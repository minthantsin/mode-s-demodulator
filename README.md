# mode-s-decoder

A JavaScript module for decoding Mode S / ADS-B messages from aviation
aircrafts.

## Installation

```
npm install mode-s-decoder --save
```

## API

### Constants

- `UNIT_FEET`
- `UNIT_METERS`

### `state = init()`

Initialize the state object (used as an argument to other functions).

### `computeMagnitudeVector(data, mag, size)`

- `data` - A buffer object containing raw IQ samples
- `mag` - An `Uint16Array` to which the magnitude of each sample will be
  written
- `size` - The size of the `data` buffer

### `detect(state, mag, size, callback)`

- `state` - A state object returned from `init()`
- `mag` - The `mag` object computed using `computeMagnitudeVector()`
- `size` - The size of the `mag` array
- `callback` - Called every time a new message is detected. Will be
  called with two arguemnts: `state` and `message`

## License

MIT
