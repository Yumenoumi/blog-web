---
title: data_class
date: 2024-05-19T12:18:21+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1715645942867-4c8649966352?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MTYwOTIxOTd8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1715645942867-4c8649966352?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MTYwOTIxOTd8&ixlib=rb-4.0.3
---

# [felangel/data_class](https://github.com/felangel/data_class)

# data_class

[![build](https://github.com/felangel/data_class/actions/workflows/main.yaml/badge.svg)](https://github.com/felangel/data_class/actions/workflows/main.yaml)
[![pub package](https://img.shields.io/pub/v/data_class_macro.svg)](https://pub.dev/packages/data_class_macro)
[![License: MIT](https://img.shields.io/badge/license-MIT-purple.svg)](https://opensource.org/licenses/MIT)

**🚧 Experimental** support for data classes in Dart using [macros](https://dart.dev/language/macros).

## ✨ Features

🪨 `const` constructors with required, named parameters

🖨️ `copyWith` with optional, nullable, named parameters

✨ `toString` for an improved string representation

☯️ `operator==` and `hashCode` for value equality

## 🧑‍💻 Example

```dart
import 'package:data_class_macro/data_class_macro.dart';

@Data()
class Person {
  final String name;
}

void main() {
  // 🪨 Create a const instance with required, name parameters.
  const dash = Person(name: 'Dash');

  // 🖨️ Create copies of your object.
  final sparky = dash.copyWith(name: () => 'Sparky');

  // ✨ Human-readable string representation.
  print(dash); // Person(name: Dash)
  print(sparky); // Person(name: Sparky)

  // ☯️ Value equality comparisons.
  print(dash == dash.copyWith()); // true
  print(dash == sparky); // false
}
```

## 🚀 Quick Start

1. Switch to the Flutter `master` channel
   `flutter channel master`

1. Add `package:data_class_macro` to your `pubspec.yaml`

   ```yaml
   dependencies:
     data_class_macro: ^0.0.0-dev.1
   ```

1. Enable experimental macros in `analysis_options.yaml`

   ```yaml
   analyzer:
     enable-experiment:
       - macros
   ```

1. Use the `@Data` annotation (see above example).

1. Run it

   ```sh
   dart --enable-experiment=macros run main.dart
   ```

_\*Requires Dart SDK >= 3.5.0-152.0.dev_
