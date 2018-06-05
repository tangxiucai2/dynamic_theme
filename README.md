# dynamic_theme
## Dynamicall chaning your theme without hassle

![](https://github.com/Norbert515/dynamic_theme/blob/master/assets/theme.png)

This packages manages changing your theme during runtime and persiting that theme.

### I wrote a medium post about this, check it out here!

## Include in your project
```
dependencies:
  dynamic_theme:
    git:
      url: git://github.com/Norbert515/dynamic_theme.git
```
and import it
```

```

## Usage
Wrap your material app like this:
```dart

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return new DynamicTheme(
      defaultBrightness: Brightness.light,
      data: (brightness) => new ThemeData(
        primarySwatch: Colors.indigo,
        brightness: brightness,
      ),
      themedWidgetBuilder: (context, theme) {
        return new MaterialApp(
          title: 'Flutter Demo',
          theme: theme,
          home: new MyHomePage(title: 'Flutter Demo Home Page'),
        );
      }
    );
  }
}

```

Change the theme like this:
```dart
  void changeBrightness() {
    DynamicTheme.of(context).setBrightness(Theme.of(context).brightness == Brightness.dark? Brightness.light: Brightness.dark);
  }
  
  void changeColor() {
    DynamicTheme.of(context).setThemeData(new ThemeData(
        primaryColor: Theme.of(context).primaryColor == Colors.indigo? Colors.red: Colors.indigo
    ));
  }

```

## Also included

### A dialog widget to change the birghtness!
![](https://github.com/Norbert515/dynamic_theme/blob/master/assets/dialogs.png)

## Getting Started

For help getting started with Flutter, view our online [documentation](https://flutter.io/).

For help on editing package code, view the [documentation](https://flutter.io/developing-packages/).
