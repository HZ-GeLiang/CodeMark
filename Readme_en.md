# Important Notice

1. This plugin is not available for free, and I have no plans to sell it publicly.
2. If you like this plugin and wish to unlock all features, please click the free "star" button and send your machine code to my email. I will reply with an activation code.
3. By default, the plugin displays up to 50 markers; any additional markers will not appear in the directory.
4. There are currently no plans to open source this plugin.

# Plugin Background

When developing based on a product manager's prototype, each feature typically has a corresponding implementation. As the codebase grows, the common approach is to find the corresponding method or search by keywords. However, in the following situations, the efficiency of locating feature implementations significantly decreases:

- When multiple people collaborate on a project, temporarily maintaining or taking over someone else's code.
- Performing maintenance or adjustments on features after product delivery.

At this point, I hope to quickly locate specific implementations through the common language within the project.

# Usage Instructions

1. How to open the window: View -> Other Windows -> CodeMark
2. Usage: Describe the content in CSV format within the document

   | Format                             | Note                                                         | Example                       |
   | ---------------------------------- | ------------------------------------------------------------ | ----------------------------- |
   | //m, {path1}/{path2},{mark}        | Multi-level folders can use / or \                           | //m.user/login,device check   |
   | //m, {mark}                        | If there is no folder, the current file name will be used as the folder name | //m, device check             |
   | //m,[fn], {mark}                   | [fn] is a fixed value representing fileName, equivalent to the above | //m, [fn],device check        |
   | //m,[fn], {mark} ,{SequenceNumber} | SequenceNumber is a natural number from 1-N for display sorting | //m.user/login,device check,1 |

# Features

- The plugin supports both English and Chinese, with language display automatically adjusted based on Visual Studio's language settings (manual setting is not supported).

- Save button: Automatically syncs content to the CodeMark window.

- Search:
  - Automatically performs a search if no input is detected for more than 500 milliseconds.
  - Case-insensitive, and keywords are split by default for searching.

- Automatically loads when the project is opened (can be set to disable).

# Known Issues

- Only supports .cs files.

- Display in dark mode may cause the plugin to be unusable.

- The UI display of the CodeMark window is not as smooth as Visual Studio's Solution Explorer.

- When saving all (Ctrl+Shift+S), only the content of the currently active document is responded to (testing shows that responding to all documents causes Visual Studio to lag).

- Path values cannot be batch renamed or custom sorted.

- Export is not currently supported.