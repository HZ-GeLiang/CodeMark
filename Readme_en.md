# Important Notes

1. This plugin is not provided for free, and I have no plans to sell it publicly.
2. If you like this plugin and wish to unlock all features, please click the free "Star" button and send your machine code to my email. I will reply with an activation code.
   1. The activation code has no time or feature restrictions.
   2. The activation code is only valid for your current device and will become invalid if you switch devices.
3. By default, the plugin displays up to 50 markers; any exceeding this limit will not appear in the directory.
4. There are currently no plans to open-source the plugin.

# Plugin Background

When developing based on a product manager's prototype, each feature typically corresponds to a specific implementation. As the codebase grows, common methods to locate implementations include finding the corresponding method or searching via keywords. However, efficiency in locating feature implementations drops significantly in the following scenarios:

- Collaborating on a project with multiple developers, temporarily maintaining, or taking over someone else's code.
- Performing feature maintenance or adjustments after product delivery.

In such cases, I wanted a way to quickly locate specific implementations using the project's common terminology.

# Usage Instructions

1. How to open the window: View -> Other Windows -> CodeMark

2. Usage: Describe content in CSV format within the document.

   | Format                            | Notes                                                  | Example                             |
   | --------------------------------- | ------------------------------------------------------ | ----------------------------------- |
   | //m, {path1}/{path2},{mark}       | Multi-level folders can use / or \                     | //m, User/Login, DeviceLimitCheck   |
   | //m, {mark}                       | Automatically adds [fn], equivalent to below           | //m, DeviceLimitCheck               |
   | //m,[fn], {mark}                  | [fn] is a fixed value, same effect as above            | //m, [fn], DeviceLimitCheck         |
   | //m,[fn], {mark},{SequenceNumber} | SequenceNumber is a positive integer (1-N) for sorting | //m, User/Login, DeviceLimitCheck,1 |

   - Tip for adjusting sorting: Set SequenceNumber to a specific decimal and regenerate the sort order.

# Features

- The plugin supports English and Chinese, with the language display automatically adjusting based on Visual Studio’s language (manual setting is not supported).
- Supports Visual Studio’s Dark mode.
- Save button: Automatically syncs content to the CodeMark window.
- Search:
  - When typing, if no input is detected for over 500 milliseconds, the search executes automatically.
  - Case-insensitive, with keywords split by default for searching.
- Automatically loads when opening a project (can be disabled in settings).

# Known Issues

- Only supports .cs files.
- The UI display of the CodeMark window is not as smooth as Visual Studio’s Solution Explorer.
- During "Save All" (Ctrl+Shift+S), only the content of the currently active document is processed (testing showed that processing all documents causes Visual Studio to lag).
- {path} values cannot be renamed in bulk.

# Unreleased Features

- Export content as XML (feature completed but not yet released).
