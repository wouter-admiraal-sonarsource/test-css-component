Test (S)CSS Components
======================

This is a POC for maintaining and re-using CSS and SCSS components across projects using `yarn`.

This package contains some variables and helpers. To re-use them in another project, install as follows:

```sh
yarn add https://github.com/wouter-admiraal-sonarsource/test-css-component.git
```

This will install this package in your local `node_modules/` folder. Next, add the following script to your `package.json`:

```json
  "scripts": {
    "build:css": "node-sass --include-path=node_modules/ -o dist src/*.scss"
  },
```

_Note: adapt input and output paths as needed._

You can then reference the SCSS files directly in your own:

```scss
@import "test-css-component/utils/variables";
@import "test-css-component/utils/helpers";

.my-class {
  color: $blue;

  @include mq(1200) {
    max-width: 400px;
  }
}
```

You can find an example here: https://github.com/wouter-admiraal-sonarsource/test-reuse-components
