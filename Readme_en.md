# Important Notice
1. This plugin is not provided for free, and I have no plans to sell it externally.
2. If you like this plugin and want to unlock all its features, please click the free "star" button, and then send your machine code to my email address. I will reply with an activation code.
    1. The activation code has no time limit or functional restrictions.
    2. The activation code is only valid for your current device and will become invalid if you change the device.
3. In the unactivated state, the plugin only supports 1 sln project, and the second IDE instance will not be loaded.
4. Currently, there are no plans to open source the plugin.

# Plugin Background
When developing based on the product manager's prototype, each function usually has a corresponding implementation. As the amount of code increases, the common approach is to find the corresponding method or search using keywords. However, in the following situations, the efficiency of locating the function implementation will be significantly reduced:
- When working on a project with multiple people collaborating, and you are temporarily maintaining or taking over someone else's code.
- When performing function maintenance or adjustments after the product has been delivered.
At this time, I hope to be able to quickly locate the specific implementation through the common language in the project.

# Usage
1. How to open the window: View -> Other Windows -> CodeMark
2. Usage method: Describe the content in CSV format in the document

  - Variable symbol description

      | Variable Symbol  | Description                 | Remarks            |
      | --------- | -------------------- | --------------- |
      | {catalog} | Catalog                 |   Multiple-level folders can use / or \              |
      | {mark}    | Content description             | Cannot contain a comma |
      | {fn}      | Current file name         | fn means: fileName |
      | {number}  | Sorting sequence number in the current directory | Used for display sorting. Decimals and complex numbers can be used, but it is recommended to use positive integers (1-N) for number. When the sorting is reset, it will start regenerating from 1 |
      
  - Examples

       | Format                        | Example Value                       | Remarks                                           |
       | --------------------------- | ---------------------------- | ---------------------------------------------- |
       | //m,{mark}                  | //m,Device Limit Judgment            | When the sorting is reset, [fn] will be added |
       | //m,{catalog},{mark} | //m.User/Login,Device Limit Judgment   | Recommended                         |
       | //m,{catalog},{mark},{number} | //m.User/Login,Device Limit Judgment | Recommended |
       | //m,[fn],{mark}             | //m,[fn],Device Limit Judgment       | Has the same effect as: //m,{mark} |
       | //m,[fn],{mark},{number}    | //m.User/Login,Device Limit Judgment,1 |               |

   - A little trick for adjusting the sorting: Set {number} to a specific decimal and then regenerate the sorting sequence number

# Functional Features
- The plugin supports both English and Chinese, and the language display is automatically adjusted according to the language of Visual Studio (manual setting is not supported).
- Supports the Dark mode of Visual Studio.
- Save button: Automatically synchronizes the content to the CodeMark window.
- Search:
  - When entering characters, if there is no input for more than 500 milliseconds, the search will be executed automatically.
  - Case-insensitive, and keywords are split by default for the search.
- Automatically loads when opening a project (can be set to turn off).

# Currently Known Issues

| Issue                                                         | Remarks                         |
| ------------------------------------------------------------ | ---------------------------- |
| Only supports.cs files.                                              | There are currently no plans to change it to a configuration.             |
| The UI display of the CodeMark window is not as smooth as that of the Solution Explorer in Visual Studio. | I'm not a professional in WPF, so it's like this for now. |
| When performing "Save All" (Ctrl+Shift+S), it only responds to the content of the currently active document (in practice, when it responds to all documents, Visual Studio will freeze). | Processed and completed.                     |
| The {path} value cannot be renamed in batches.                                    | Use ctrl+f for batch replacement.             |
| Export content as XML                                                | Tentative                         |

# todo:
1. Structured support

```
  /**
    * showdoc
    * @catalog User/Login
    * @mark Device Limit Judgment
    * @description User login interface
    * @remark Here is the remark information
    * @number 2
    */
    
``` 
