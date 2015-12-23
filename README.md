# Picky

Picky is a jQuery plugin that provides a modern, flexible UI (using Bootstrap dropdowns) for `<select>` menus.

Requires jQuery (v1.9+ recommended) and Bootstrap (v2, v3+).

This is based on the great [Bootstrap Multiselect](http://davidstutz.github.io/bootstrap-multiselect/), but adds a number of features and improvements. _Note that the modified code has not yet been merged (it's currently tied up in a hacked version of bootstrap-multiselect in another project)._

- Handles both single-select and multi-select menus
- Supports tree-like menu options with nested (indented) children
  - Optionally select all descendants
  - Indented rows collapse when searching
- Improvements to UI behavior
  - Pressing [esc] does not open the dropdown when button is closed and has focus (Bootstrap issue, fixed in v.3.3.0; fix is only applied when using an older version of Bootstrap)
  - When used in a modal dialog, pressing [esc] closes open menus without also closing the dialog
  - Browser/OS keyboard shortcuts now work while a menu is open (key event listener no longer calls `event.preventDefault()` when the event includes a modifier key other than [shift])
  - Search field automatically gets focus when menu is opened
  - Search field is cleared when menu is closed
  - Use arrow up/down to move in and out of the search field
  - When a menu is closed and has focus, and filtering is enabled, you can just start typing; the dropdown immediately opens and keyboard input goes to search field
  - While filtering, press arrow up/down to select a result, and [return] to select it
  - For single-select menus, pressing [return] while the currently-selected item has focus no longer deselects it
  - Improved tab key behavior
    - When focus is on a menu item, shift + tab moves focus to the search field instead of just closing the dropdown (as expected, since tab moves focus from the search field to menu items)
    - When the search field has focus, shift + tab moves focus to the previous element in the same tabindex (previously it just closed the dropdown and did not move focus as expected)
  - Prevents closing dropdown when clicking non-actionable area in dropdown (such as small gaps between menu items)
