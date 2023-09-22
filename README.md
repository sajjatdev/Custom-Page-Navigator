# Custom Page Navigator

``` dart
import 'package:flutter/material.dart';

class CustomRoute<T> extends PageRoute<T> {
  CustomRoute({
    required this.builder, // Replace this with your widget builder function
    RouteSettings? settings,
  }) : super(settings: settings);

  // Implement barrierColor
  @override
  Color? get barrierColor => null; // You can set a color or return null

  // Implement barrierLabel
  @override
  String? get barrierLabel => null; // You can provide a label or return null

  // Implement buildPage to return your custom content
  @override
  Widget buildPage(BuildContext context, Animation<double> animation,
      Animation<double> secondaryAnimation) {
    // Replace this with your widget creation logic
    return builder(context);
  }

  // Implement maintainState
  @override
  bool get maintainState => true; // Adjust as needed

  // Implement transitionDuration
  @override
  Duration get transitionDuration => Duration(milliseconds: 400); // Adjust as needed

  // Implement your custom transition animation if needed
  @override
  Widget buildTransitions(BuildContext context, Animation<double> animation,
      Animation<double> secondaryAnimation, Widget child) {
    // You can define custom transitions here if needed
    return FadeTransition(
      opacity: animation,
      child: child,
    );
  }

  final WidgetBuilder builder;
}


```
