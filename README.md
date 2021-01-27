# sublime-dbc

## Overview

[DB/C Language](http://dbcsoftware.com/) support for Sublime 3.0

## Installation

### Install from git

- Checkout repository in Sublime packages directory
  - Windows: %APPDATA%\Sublime Text 3\Packages
  - Mac: $HOME/Library/Application Support/Sublime Text 3/Packages

### Manually

- Create a dbc directory in sublime packages directory (Preferences -> Browse Packages)
- Download this repository & copy to the files to the dbc directory

## TODO

- Fix invalid continue/endif etc
- Indentation defaults
- Trap functions
- Find a way to override goto-definition word seperators

## Helpful Settings

You can add these in addition to your current settings

### Settings

```
{
	"auto_complete_commit_on_tab": true,
	"auto_complete_delay": 50,
	"auto_find_in_selection": true,
	"bold_folder_labels": true,
	"caret_style": "phase",
	"fade_fold_buttons": false,
	"highlight_line": true,
	"highlight_modified_tabs": true,
	"line_padding_bottom": 2,
	"line_padding_top": 1,
	"rulers":
	[
		80
	],
	"show_encoding": true,
	"tab_completion": true,
	"trim_trailing_white_space_on_save": true,
	"word_wrap": true
}

```

### Keybinding

```
[
	{ "keys": ["ctrl+shift+o"], "command": "clone_file" },
	{ "keys": ["ctrl+shift+t"], "command": "reopen_last_file" },
	{ "keys": ["ctrl+alt+p"], "command": "prompt_select_workspace" }
]
```

## Recommended Plugins

### [All AutoComplete](https://packagecontrol.io/packages/All%20Autocomplete)

### [BracketHighlighter](http://facelessuser.github.io/BracketHighlighter/)

bh_core.sublime-settings

```
{
        "user_brackets": [
        // DBC conditional statements
        {
            "name": "dbc_conditional",
            "open": "^\\s+(IF|SWITCH)\\s",
            "close": "^\\s+(ENDIF|ENDSWITCH)\\s",
            "style": "if_switch",
            "scope_exclude": ["string", "comment"],
            "language_filter": "whitelist",
            "language_list": ["dbc", "DBC"],
            "enabled": true
        },
        // DBC loop statements
        {
            "name": "dbc_loop",
            "open": "^\\s+(FOR|LOOP)\\s",
            "close": "^\\s+(REPEAT)\\s",
            "style": "default",
            "scope_exclude": ["string", "comment"],
            "language_filter": "whitelist",
            "language_list": ["dbc", "DBC"],
            "enabled": true
        },
        // DBC list statements
        {
            "name": "dbc_list",
            "open": "\\s(LIST)\\n",
            "close": "^\\s+(LISTEND)\\s",
            "style": "default",
            "scope_exclude": ["string", "comment"],
            "language_filter": "whitelist",
            "language_list": ["dbc", "DBC"],
            "enabled": true
        },
        // DBC routines
        {
            "name": "dbc_routines",
            "open": "\\s(ROUTINE|LROUTINE)\\s",
            "close": "^\\s+(ENDROUTINE)\\s",
            "style": "routine",
            "scope_exclude": ["string", "comment"],
            "language_filter": "whitelist",
            "language_list": ["dbc", "DBC"],
            "enabled": true
        },
        // DBC compiler conditionals
        {
            "name": "dbc_compiler",
            "open": "^\\s+#(IFDEF|IFNDEF|IFLABEL|IFNLABEL)\\s",
            "close": "^\\s+#(ENDIF)\\s",
            "style": "c_define",
            "scope_exclude": ["string", "comment"],
            "language_filter": "whitelist",
            "language_list": ["dbc", "DBC"],
            "enabled": true
        }

    ],
    "user_bracket_styles": {
        "routine": {
            "icon": "tag",
            "color": "region.purplish",
            "style": "outline"
        },
        "if_switch": {
            "icon": "dot",
            "color": "region.bluish",
            "style": "outline"
        }
    },
}
```

### Default (Windows).sublime-keymap

```
//Package: Bracket highligher
	// Go to left bracket
    {
        "keys": ["alt+shift+up"],
        "command": "bh_key",
        "args":
        {
            "no_outside_adj": null,
            "no_block_mode": null,
            "lines" : true,
            "plugin":
            {
                "type": ["__all__"],
                "command": "bh_modules.bracketselect",
                "args": {"select": "left"}
            }
        }
    },
    // Go to right bracket
    {
        "keys": ["alt+shift+down"],
        "command": "bh_key",
        "args":
        {
            "no_outside_adj": null,
            "no_block_mode": null,
            "lines" : true,
            "plugin":
            {
                "type": ["__all__"],
                "command": "bh_modules.bracketselect",
                "args": {"select": "right"}
            }
        }
    },
    // Fold contents between brackets
    {
        "keys": ["alt+shift+["],
        "command": "bh_key",
        "args":
        {
            "plugin": {
                "type": ["__all__"],
                "command" : "bh_modules.foldbracket"
            }
        }
    },
    // Fold contents between brackets
    {
        "keys": ["alt+shift+]"],
        "command": "unfold"
    },
    // Select text including brackets
    {
        "keys": ["alt+shift+d"],
        "command": "bh_key",
        "args":
        {
            "no_outside_adj": null,
            "lines" : true,
            "plugin":
            {
                "type": ["__all__"],
                "command": "bh_modules.bracketselect",
                "args": {"always_include_brackets": true}
            }
        }
    },
    // Select text between brackets
    {
        "no_outside_adj": null,
        "keys": ["alt+shift+s"],
        "command": "bh_key",
        "args":
        {
            "lines" : true,
            "plugin":
            {
                "type": ["__all__"],
                "command": "bh_modules.bracketselect"
            }
        }
    },
```
