# `@reason-react-native/image-picker`

[![Build Status](https://github.com/reason-react-native/image-picker/workflows/Build/badge.svg)](https://github.com/reason-react-native/image-picker/actions)
[![Version](https://img.shields.io/npm/v/@reason-react-native/image-picker.svg)](https://www.npmjs.com/@reason-react-native/image-picker)
[![Chat](https://img.shields.io/discord/235176658175262720.svg?logo=discord&colorb=blue)](https://reasonml-community.github.io/reason-react-native/discord/)

[ReScript](https://rescript-lang.org) / [Reason](https://reasonml.github.io) bindings for
[`react-native-image-picker`](https://github.com/react-native-community/react-native-image-picker).

Exposed as `ReactNativeImagePicker` module.

`@reason-react-native/image-picker` X.y.\* means it's compatible with
`react-native-image-picker` X.y.\*

## Installation

When
[`react-native-image-picker`](https://github.com/react-native-community/react-native-image-picker)
is properly installed & configured by following their installation instructions,
you can install the bindings:

```console
npm install @reason-react-native/image-picker
# or
yarn add @reason-react-native/image-picker
```

`@reason-react-native/image-picker` should be added to `bs-dependencies` in your
`bsconfig.json`:

```diff
{
  //...
  "bs-dependencies": [
    "reason-react",
    "reason-react-native",
    // ...
+    "@reason-react-native/image-picker"
  ],
  //...
}
```

## Usage

```reason
open ReactNativeImagePicker;

ImagePicker.(
  launchCamera(
    Options.make(
      ~title="Take a picture",
      ~cameraType=`back,
      ~mediaType=`photo,
      ~permissionDenied=
        Options.PermissionDenied.options(
          ~title="Permission denied !",
          ~text="text",
          ~reTryTitle="Retry",
          ~okTitle="Ok !",
        ),
      (),
    ),
    res => {
      Js.log(res##uri);
      Js.log(res##path);
    }
  )
);
```

---

## Changelog

Check the [changelog](./CHANGELOG.md) for more informations about recent
releases.

---

## Contribute

Read the
[contribution guidelines](https://github.com/reason-react-native/.github/blob/master/CONTRIBUTING.md)
before contributing.

## Code of Conduct

We want this community to be friendly and respectful to each other. Please read
[our full code of conduct](https://github.com/reason-react-native/.github/blob/master/CODE_OF_CONDUCT.md)
so that you can understand what actions will and will not be tolerated.
