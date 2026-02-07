# Zed-Vento

Adds support for the Vento template language to the Zed code editor.

## Features

- **Syntax highlighting** for Vento templates (`.vto`, `.vento` files)
- **YAML front matter support** with full YAML syntax highlighting
- **HTML injection** for template content
- **JavaScript injection** for code blocks
- **Auto-closing brackets** and intelligent pairing

## Install

### Development Installation

1. Clone this repository
2. In Zed, open the command palette (`Cmd+Shift+P` on macOS)
3. Run the command "zed: install dev extension"
4. Select the cloned repository folder

The extension will be loaded and Vento files will automatically use the syntax highlighting.

## Example

```vento
---
title: My Page
date: 2024-02-01
tags:
  - vento
  - template
layout: base.vto
---

<!DOCTYPE html>
<html>
<head>
  <title>{{ title }}</title>
</head>
<body>
  <h1>{{ title }}</h1>
  <p>Date: {{ date }}</p>
  
  {{ for tag of tags }}
    <span>{{ tag }}</span>
  {{ /for }}
</body>
</html>
```

## Features in Detail

### YAML Front Matter

The extension recognizes YAML front matter blocks between `---` delimiters and applies full YAML syntax highlighting:

```vento
---
title: My Document
author:
  name: Bob
  email: bob@example.com
tags: [vento, templates]
---
```

### Template Syntax

- `{{ expression }}` - Output expressions
- `{{- expression -}}` - Output with whitespace trimming
- `{{ if condition }}...{{ /if }}` - Conditional blocks
- `{{ for item of items }}...{{ /for }}` - Loops
- `{{# comment #}}` - Comments
- `{{ expression |> filter }}` - Filters

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## License

See [LICENSE](LICENSE) file for details.

## Credits

- Original extension by [Deniz Akşimşek](https://github.com/dz4k)
- Grammar updates and front matter support by Bob Rockefeller
- Based on [tree-sitter-vento](https://codeberg.org/dz4k/zed-vento)
