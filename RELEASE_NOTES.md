# Release Notes

##### 1.3.0.3
- Fixed issue [34](https://github.com/contrix09/XF-Material-Library/issues/34).
- Added new method `IMaterialDialog.DismissAsync()`. 
- Fixed `MaterialCard` showing original `Frame` shadow when `BorderColor` property was updated.
- Fixed `MaterialMenuButton` showing inaccurate position.

##### 1.3.0.2
- Fixed issue [32](https://github.com/contrix09/XF-Material-Library/issues/32).
- Fixed issue [33](https://github.com/contrix09/XF-Material-Library/issues/33).
- Fixed an issue in `MaterialButtonRenderer` in iOS not updating the color of the button when the background color was changed.

##### 1.3.0.1
- Fixed a bug in `MaterialButton` where the border color is not updating when the `ButtonType` is `Outlined`.
- Lowered the input field in `MaterialTextField` by 2.

##### 1.3.0
- Added `MaterialIconButton` and `MaterialSlider`.
- Replaced `MaterialMenu` to `MaterialMenuButton`. The latter inherits from `MaterialIconButton`.
- Added new properties `PressedBackgroundColor` and `DisabledBackgroundColor` to Material buttons.
- Refactored `MaterialButtonRenderer` in iOS. Instead of adding negative margin to shrink the view, it now changes the `UIView.Layer.Frame` property by decreasing the width and height by 12.
- Refactored `MaterialTextField`:
  - Added new input type `Choice`, along with a new property `Choices`. When the text field is clicked, shows a confirmation dialog from which the user will choose one from a list of choices.
  - Added new property `HasHorizontalPadding`. When set to `true`, removes the left and right padding of the text field.
  - `FloatingPlaceholderEnabled` property, when set to `true`, reduces the height of the text field from 72 to 56.
- Adjusted the bounds some of modal dialogs.
- Fixed an interaction bug in Android when using `PopupPage` from `Rg.Plugins.Popup` library.
- Fixed issue [26](https://github.com/contrix09/XF-Material-Library/issues/26).
- Fixed issue [31](https://github.com/contrix09/XF-Material-Library/issues/31).

##### 1.2.4
- Fixed issue [24](https://github.com/contrix09/XF-Material-Library/issues/24).
- Refactored `IMaterialDialog.AlertAsync()`.

##### 1.2.3
- Fixed `MaterialTextField` overlaping parent layout's bounds in iOS.
- Added a new `booelan` property `FloatingPlaceholderEnabled` to determine to animate the placeholder of the text field.

##### 1.2.2
- Fixed `MaterialTextField` overlaping parent layout's bounds in iOS.
- Fixed `MaterialButton` causing a crash in Android devices running Android 4.4 or later.

##### 1.2.1
- `MaterialRadioButton` constructor access modifier changed to public.
- Added maximum width for modal dialogs. This ensures that modals don't fill the entire screen when shown.
  - On tablets, dialogs has a maximum width of `560`. 
  - On phones, dialogs has a maximum width of `280`.
  - Snackbars has a maximum width of `344`.

##### 1.2.0
- Upgraded to use `Xamarin.Forms` version `3.3`.
- Added `IMaterialDialog.InputAsync`, which shows a dialog that allows the user to input text. A feature enhancement stated in this [issue](https://github.com/contrix09/XF-Material-Library/issues/18).
- Added `MaterialMenu` control, a view container that will show a menu that allows the user to select a choice.
- Reworked `MaterialNavigatioPage`.
  - Added an attached property `AppBarColor`. It can be attached to `Pages` to change the `NavigationPage.BarBackgroundColor` property.
  - Added an attached property `AppBarTitleTextAlignment`. It can be attached to `Pages` to change the `NavigationPage.Title` text alignment.
  - Added an attached property `AppBarTitleTextColor`. It can be attached to `Pages` to change the `NavigationPage.Title` text color.
  - Added an attached property `AppBarTitleTextFontFamily`. It can be attached to `Pages` to change the `NavigationPage.Title` text font family.
  - Added an attached property `AppBarTitleTextFontSize`. It can be attached to `Pages` to change the `NavigationPage.Title` text font size.
  - Added an attached property `StatusBarColor`. It can be attached to `Pages` to change the status bar color.
  - Added an attached property `HasShadow`. It can be attached to `Pages` that will determine whether the app bar will draw a shadow.
  - Added overrideable methods `OnPagePush` and `OnPagePop`.
- The status bar color will now be set automatically when `MaterialNavigationPage` is used. You can still use `Material.PlatformConfiguration.SetStatusBarColor` to manually change the status bar color.
- Added `BottomOffset` property to `MaterialSnackbarConfiguration` that can be used to adjust the bottom margin of the Snackbar. A feature enhancement stated in this [issue](https://github.com/contrix09/XF-Material-Library/issues/23).
- Fixed a bug where `MaterialCheckboxGroup` does not update the selected items when the property `SelectedIndices` has been changed.
- Renamed `XF.Material.Forms.Views` to `XF.Material.Forms.UI`. Removed  `XF.Material.Forms.Dialog` namespace, added dialogs to namespace `XF.Material.Forms.UI.Dialogs`.

##### 1.1.2.1
- Fixed a bug in Android causing `MaterialButtonRenderer` throwing a `System.NullReferenceException` when `MaterialButton` `Image` property is set. A bug reported in this [issue](https://github.com/contrix09/XF-Material-Library/issues/21).

##### 1.1.2
- Reworked `MaterialRadioButtonGroup`. Once a choice has been selected, you can no longer unselect a choice. A bug reported in this [issue](https://github.com/contrix09/XF-Material-Library/issues/11).
- Changed the minimum and target `MonoAndroid` framework version to `8.1`. Fixed also some inconsistencies in the referenced NuGet packages of the library. A bug reported in this [issue](https://github.com/contrix09/XF-Material-Library/issues/13).
- Removed the `font` directory in the `Resources` folder in `XF.Material.Droid`.
- Fixed a bug when calling `XF.Material.Forms.Material.Init(Application app)` causing `System.NullException`. A bug reported in this [issue](https://github.com/contrix09/XF-Material-Library/issues/14).
- Fixed a bug when canceling a confirmation dialog shown using `MaterialDialog.Instance.SelectChoicesAsync()` not clearing the currently selected choices.
- Fixed a bug in `MaterialRadioButtonGroup` and `MaterialCheckboxGroup` not updating `SelectedIndex` and `SelectedIndices` property, respectively.

##### 1.1.1
- Added parameters `selectedIndex` and `selectedIndices` to `IMaterialDialog.SelectChoiceAsync` and `IMaterialDialog.SelectChoicesAsync`. A feature enhancement as stated in this [issue](https://github.com/contrix09/XF-Material-Library/issues/9).
- Fixed `MaterialRadioButtonGroup` and `MaterialCheckboxGroup` having an extra empty row.
- Fixed `MaterialButtonRenderer` in iOS not responding to changes in `MaterialButton.AllCaps` property.

##### 1.1.0
- Added selection controls: `MaterialRadioButton`, `MaterialRadioButtonGroup`, `MaterialCheckbox`, and `MaterialCheckboxGroup`.
- Deprecated `MaterialDialogs`, you should use `MaterialDialog.Instance` for displaying modal dialogs.
- Added simple dialog and confirmation dialog to `MaterialDialog`.
- Added `ReturnType`, `ReturnTypeCommand`, and `ReturnTypeCommandParameter` properties to `MaterialTextField`. A feature enhancement stated in this [issue](https://github.com/contrix09/XF-Material-Library/issues/5).
- Changed the default color values of `MaterialColorConfiguration`.
- Fixed a bug in Android when using `MaterialIcon`, which causes all other views using the same resource image to change color when one of them was changed.
- Fixed a bug in Android when using `MaterialButton`, which causes text button type not having a disabled text state.
- Removed the back button title in iOS when using `MaterialNavigationPage`.
- Removed `ColorConfiguration` and `FontConfiguration` in `XF.Material.Forms.Material` class. Added static subclasses `Color` and `FontFamily` with static properties that will hold the values of the current color and font configurations.

##### 1.0.6
- Refactored `MaterialDialogs`. A feature enhancement stated in this [issue](https://github.com/contrix09/XF-Material-Library/issues/4).
  - Added `MaterialDialogs.ShowConfirmAsync()`. Use this for user confirmation of action. Returns a `boolean` value based on what the user chose.
  - `MaterialDialogs.ShowAlertAsync` is now only used for user acknowledgement purposes.
  - The overload method of `MaterialDialogs.ShowSnackbarAsync()` that has an action now also returns a `boolean` value.
- Changed the minimum `Xamarin.Android.Support.*` verion to `25.4.0.2` to address this [issue](https://github.com/contrix09/XF-Material-Library/issues/3). This is the same minimum version that the latest `Xamarin.Forms` Nuget package accepts. 
- Changed the assembly and namespace name from `XF.Material` to `XF.Material.Forms`.
- Added static properties `ColorConfiguration` and `FontConfiguration` to `XF.Material.Forms.Material` class.

##### 1.0.5
- Added NuGet Package icon.
- Added `MaterialAlertDialogConfiguration`, `MaterialLoadingConfiguration`, and `MaterialSnackbarConfiguration` for
styling modals created by `MaterialDialogs`.
- Added `MaterialConstants`, a static class to provide constant key values of Material Resources.
- Refactored methods in `MaterialDialogs`.
- Fixed `MaterialButton` throwing exception on devices running Android 4.2.
- Fixed `MaterialTextField` not showing error icon on iOS when the property `HasError` is set to `true`.

##### 1.0.4
- Fixed NuGet Package not including the features from version `1.0.3`.
- Updated to the latest Xamarin.Forms.

##### 1.0.3
- Added `MaterialTextField` and `MaterialIcon`.

##### 1.0.2
- Added type scale fonts in `MaterialFontConfiguration`.

##### 1.0.1
- Fixed some rendering bugs.
- Added a `FontAttribute.Bold` `DynamicResource` value to `MaterialButton`.
- Removed `Padding` values in `MaterialChip`.
- Pages pushed in `MaterialNavigationPage` will have a default `BackgroundColor` value equal to the `MaterialColorConfiguration.Background`, unless the `BackgroundColor` property is set in the page.

##### 1.0.0
- Initial release.