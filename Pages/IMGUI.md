# IMGUI

IMGUI is the standard GUI drawing method for all Editor GUI up until 2020.1 (UIToolkit is now recommended by Unity). IMGUI stands for Immeditate Mode GUI, this means that it is redrawn every frame. This makes it really easy to use for quickly creating new UIs and constantly the visual representation with the data. However because of this IMGUIs are often relatively expensive to render as it is hard to do virtualization and to only redraw elements that have changed.

## Layouting

Unity supports 2 different layouting methods for IMGUI. The automatic or GUILayout method, as the name implies tries to automatically place the elements based on hints given by the developer. The other is the manual layouting mode, this lets you place elements at specific screen coordinates and no automatic layouting or sizing is done on these elements. 

In most cases you won't have to mix these methods however it is useful to know as not all controls are available in both methods (mostly GUI methods not being available in GUILayout).

### Automatic / GUILayout

As previously mentioned, the automatic layout method tries to place the UI elements based on hints provided by the developer. This makes it easier to quickly create new UIs in a similar style in exchange for a little less control. It starts by placing controls in the top left corner.

All automatically layouted controls are defined in the (Editor)GUILayout class, most general purpose controls are defined in GUILayout. Some have an equivalent in EditorGUILayout, these often have extra functionality specific to the editor.

There are several ways to influence the placement of GUILayout controls, most often you'll be using Horizontal (`Begin/EndHorizontal` or `HorizontalScope`) and Vertical (`Begin/EndVertical` or `VerticalScope`) groups, these allow for most basic UIs. You can also pass `GUILayoutOption`s to most controls, these allow you to change that control specifically, it's a bit counter intuitive however these are also defined in `GUILayout` (e.g. `GUILayout.Width` or `GUILayout.Min/MaxWidth`). 

Placing controls at either the right or bottom side can be done by using a layout group and the `GUILayout.FlexibleSpace` control, which will take up all leftover space.

### Manual / GUI

### Mixing manual and automatic modes

## Styling