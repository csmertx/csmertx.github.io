---
title: 💻 Ranger File Manager
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-04
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

> Links to the project [below](#resources)

## Custom Commands

- ```vim ~/.config/ranger/commands.py```

- Add command at the bottom following a comment

    - Included additional libraries if needed (```from``` ...)

## File Compression Command

```
from ranger.core.loader import CommandLoader

class compress(Command):
    def execute(self):
        """ Compress marked files to current directory """
        cwd = self.fm.thisdir
        marked_files = cwd.get_selection()

        if not marked_files:
            return

        def refresh(_):
            cwd = self.fm.get_directory(original_path)
            cwd.load_content()

        original_path = cwd.path
        parts = self.line.split()
        au_flags = parts[1:]

        descr = "compressing files in: " + os.path.basename(parts[1])
        obj = CommandLoader(args=['apack'] + au_flags + \
                [os.path.relpath(f.path, cwd.path) for f in marked_files], descr=descr, read=True)

        obj.signal_bind('after', refresh)
        self.fm.loader.add(obj)

    def tab(self, tabnum):
        """ Complete with current folder name """

        extension = ['.zip', '.tar.gz', '.rar', '.7z']
        return ['compress ' + os.path.basename(self.fm.thisdir.path) + ext for ext in extension]
```

## File Extraction Command

```
from ranger.core.loader import CommandLoader

class extract_here(Command):
    def execute(self):
        """ extract selected files to current directory."""
        cwd = self.fm.thisdir
        marked_files = tuple(cwd.get_selection())

        def refresh(_):
            cwd = self.fm.get_directory(original_path)
            cwd.load_content()

        one_file = marked_files[0]
        cwd = self.fm.thisdir
        original_path = cwd.path
        au_flags = ['-x', cwd.path]
        au_flags += self.line.split()[1:]
        au_flags += ['-e']

        self.fm.copy_buffer.clear()
        self.fm.cut_buffer = False
        if len(marked_files) == 1:
            descr = "extracting: " + os.path.basename(one_file.path)
        else:
            descr = "extracting files from: " + os.path.basename(
                one_file.dirname)
        obj = CommandLoader(args=['aunpack'] + au_flags
                            + [f.path for f in marked_files], descr=descr,
                            read=True)

        obj.signal_bind('after', refresh)
        self.fm.loader.add(obj)
```

## Resources

- [Ranger &mdash; console file manager with VI key bindings](https://ranger.github.io/)

- [GitHub - ranger/ranger: A VIM-inspired filemanager for the console](https://github.com/ranger/ranger)

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/ranger.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Ranger File Manager">
       History 🕵️
    </a>
</div>