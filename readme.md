# React-Simple-ColorPicker

> A simple(r) colorpicker written using React.

A fork of [react-colorpicker](https://github.com/stayradiated/react-colorpicker), but with the extra stuff removed.

## Why?

* Improved performance
* Smaller file size (only 3.8kb gzipped)
* Easily composed into more complex color pickers (e.g. see [example/src](example directory))
* Bug fixes

## Install

Via npm:

```bash
npm install react-simple-colorpicker --save
```

Or if you want a UMD-compatible served from a CDN:

[https://npmcdn.com/react-simple-colorpicker/umd/index.js](https://npmcdn.com/react-simple-colorpicker/umd/index.js)

## Usage

```javascript
var React = require("react");
var ReactDOM = require("react-dom");
var ColorPicker = require("react-simple-colorpicker");

var App = React.createClass({

  getInitialState : function() {
    return {
      color : this.props.initialColor
    };
  },

  render : function() {
    return (
      <ColorPicker color={this.state.color} onChange={this.handleChange} opacitySlider />
    );
  },

  handleChange : function(color) {
    console.log(color); // color is rgb(a) string
    this.setState({ color : color });
  }

});

ReactDOM.render(<App initialColor="rgb(0,0,0,1)" />, document.querySelector("#app"));
```

## Changelog

### v1.3.0

* `react` and `react-dom` now peer dependencies (fixes #9)
* Performance improvements
* Will now work if rendered into an iframe from another document
* Switch to webpack
* Add release script

### v1.2.0

* Compatibility with react v0.14

### v1.1.2

* Drop `classSet` in favour of `classnames` module
* Switch out tinycolor2 for pure-color
* Improved example

### v1.1.1

* Fix issue with extreme saturation values caused by tinycolor2
* Better propTypes
* Some internal code cleanup

### v1.1.0 (deprecated)

* Add option for alpha slider
* React v0.13 compatibility

### v1.0.1

* Fix broken dependencies

### v1.0.0 (deprecated)

* React v0.11 compatibility

### v0.5.0

* Small tweaks

### v0.1.0

* Forked @stayradiated's [react-colorpicker](https://github.com/stayradiated/react-colorpicker)
* Remove extraneous functionality
* Drop reflux
* Fix a few bugs
* Add touch support
* Some simple perf wins with PureRenderMixin