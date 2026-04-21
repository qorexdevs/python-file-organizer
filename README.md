# Python File Organizer

A CLI tool that automatically organizes files in a directory by their type. Files are sorted into categorized folders like Images, Documents, Videos, Music, Archives, Code, and more.

## Features

- **Auto-sort** files into folders by extension
- **Dry-run mode** to preview changes before moving anything
- **Watch mode** to automatically organize new files as they appear
- **Undo** the last organization with a single command
- **Custom rules** via YAML config file
- **Rich output** with colored terminal logging
- **Conflict handling** - duplicate filenames get a numeric suffix

## Installation

```bash
git clone https://github.com/qorexdevs/python-file-organizer.git
cd python-file-organizer
pip install -e .
```

Or install dependencies directly:

```bash
pip install -r requirements.txt
```

## Usage

### Basic - organize current directory

```bash
organize
```

### Organize a specific directory

```bash
organize ~/Downloads
```

### Preview changes without moving files

```bash
organize ~/Downloads --dry-run
```

### Verbose output

```bash
organize ~/Downloads --verbose
```

### Watch mode - auto-organize new files

```bash
organize ~/Downloads --watch
```

### Undo the last organization

```bash
organize ~/Downloads --undo
```

### Use a custom config

```bash
organize ~/Downloads --config config.yaml
```

### Combine flags

```bash
organize ~/Downloads --dry-run --verbose --config my_rules.yaml
```

## CLI Reference

```
Usage: organize [OPTIONS] [PATH]

  Organize files in a directory by type.

Options:
  -d, --dry-run          Preview changes without moving files.
  -v, --verbose          Show detailed output.
  -w, --watch            Watch directory and auto-organize new files.
  -u, --undo             Undo the last organization.
  -c, --config PATH      Path to YAML config file.
  --version              Show the version and exit.
  --help                 Show this message and exit.
```

## Default Categories

| Folder       | Extensions                                          |
|:-------------|:----------------------------------------------------|
| Images       | jpg, jpeg, png, gif, bmp, svg, webp, ico, tiff, ... |
| Documents    | pdf, doc, docx, xls, xlsx, ppt, pptx, txt, csv, ... |
| Videos       | mp4, avi, mkv, mov, wmv, flv, webm, ...             |
| Music        | mp3, wav, flac, aac, ogg, wma, m4a, ...             |
| Archives     | zip, rar, 7z, tar, gz, bz2, xz, ...                 |
| Code         | py, js, ts, java, c, cpp, go, rs, html, css, ...    |
| Executables  | exe, msi, dmg, app, deb, rpm, apk                   |
| Fonts        | ttf, otf, woff, woff2, eot                           |
| 3D Models    | obj, stl, fbx, blend, 3ds                            |

## Custom Config

Create a `config.yaml` to add or extend categories. See `config.example.yaml` for reference:

```yaml
categories:
  Design:
    - .psd
    - .ai
    - .sketch
  Ebooks:
    - .epub
    - .mobi
```

## License

MIT

---

<p align="center">
  <sub>developed by <b>qorex</b></sub>
  <br>
  <a href="https://github.com/qorexdevs"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8z"/></svg></a>
  &nbsp;
  <a href="https://t.me/qorexdev"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16"><path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0M8.287 5.906q-1.168.486-4.666 2.01-.516.224-.516.437c0 .252.186.39.558.466.095.026.19.05.284.072.198.054.396.108.583.192.263.12.55.279.696.394l.003.002c.327.225.621.496.928.752l.082.066c.424.342.84.677 1.341.887.499.21 1.025.163 1.486-.106.172-.1.31-.221.45-.343l.037-.032c.254-.226.505-.454.813-.565a.2.2 0 0 1 .086-.013.15.15 0 0 1 .064.015c.055.03.09.098.095.18.006.09-.025.197-.09.293-.069.104-.17.2-.294.276a2 2 0 0 1-.217.124c-.252.127-.508.254-.722.445-.14.124-.27.265-.386.417-.327.424-.623.903-.94 1.353-.166.234-.34.47-.53.692-.192.223-.407.43-.683.556a1.26 1.26 0 0 1-.48.11c-.3.006-.56-.088-.806-.248a4 4 0 0 1-.455-.35 11 11 0 0 1-.5-.438L4.41 11.48c-.247-.228-.481-.461-.724-.682a3 3 0 0 0-.424-.337c-.272-.174-.542-.35-.8-.547-.259-.198-.503-.415-.699-.69a1.2 1.2 0 0 1-.186-.387c-.057-.2-.003-.386.107-.535.11-.148.275-.25.462-.3l.003-.001q3.446-1.5 4.668-2.01c2.203-.927 2.662-1.09 2.96-1.095h.007c.098 0 .317.023.459.144a.52.52 0 0 1 .177.37c.014.1.032.313.018.474a4.4 4.4 0 0 1-.411 1.485c-.074.163-.157.322-.243.477"/></svg></a>
</p>
