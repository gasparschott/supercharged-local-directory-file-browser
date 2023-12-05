# supercharged-local-directory-file-browser

Available at [https://openuserjs.org/users/gaspar_schot/scripts](https://openuserjs.org/scripts/gaspar_schot/Supercharged_Local_Directory_File_Browser)

This userscript works on **local directories** as well as many remote server-generated index pages (“**open directories**”). 
- By default, userscripts do not run on local file:/// urls, so for this script to work on local directories you will need to enable it in your browser's extension settings (e.g.: For Tampermonkey in Chrome, open the Chrome extensions page, click the details button for Tampermonkey and check 'Allow access to file URLs'). 
- To make the script work on a remote **open directory**, you must add its URL to the list of allowed sites in the settings for this userscript, as provided by your userscript manager.
- Because server configurations vary, the script may not work perfectly (or at all) on some open directories. You may also need to allow—or block—javascript on some ODs, and/or allow cookies. Please let me know if you encounter any problems.
- This script was developed in the latest version of Vivaldi, running on the latest MacOS. It has been *minimally* tested in other Chrome-based browsers, Safari, and Firefox, and has been **not** been tested in any other browsers or OSes. No effort has been made to ensure compatibility with older browsers. Please report any issues.

See screenshots and description below. For more detailed usage information, see the “Help” item in the main menu of the script UI.

&rarr; If you like this script, please consider **leaving a RATING** or [*buying me a coffee*](https://www.buymeacoffee.com/fiLtliTFxQ) or making a [*donation*](https://paypal.me/mschrauzer), or sending me a [*comment*](mailto:mshroud@protonmail.com) to let me know what you think. Thank you!

----

### Screenshots

**BEFORE**
![Before](https://greasyfork.s3.us-east-2.amazonaws.com/x9owm4idamdrkaj2oz0ampq1cfzy "Before")

**AFTER** _with dark theme and image grid_
![After with dark theme and image grid](https://greasyfork.s3.us-east-2.amazonaws.com/yvb8ja33sc5e4ixnv4556esp5gsh "After with dark theme and image grid")

**MEDIA PLAYBACK** _with dark theme and cover art_
![Audio player with dark theme and cover art](https://greasyfork.s3.us-east-2.amazonaws.com/2kllxq95zh39nzs9f4mbcs67slbs "Audio player with dark theme and cover art")

**MARKDOWN** _editing and preview, with subdirectory browsing_
![Markdown editing and preview](https://greasyfork.s3.us-east-2.amazonaws.com/rii4vqph16a2p1aki6lwo1gnv5nn "Markdown editing and preview, with subdirectory browsing")

**FONT GRID**
![Light theme with image and font grid](https://greasyfork.s3.us-east-2.amazonaws.com/vm44oyuiqstq52pkdxuez649ubcy "Light theme with font and image grid")

----

### **DESCRIPTION**
This script transforms the default local directory page (and many server-generated index pages) into a full-featured file browser, with a resizable sidebar and preview pane. (See screenshots below.)

If you like this script, please consider [*buying me a coffee*](https://www.buymeacoffee.com/fiLtliTFxQ) or making a [donation](https://paypal.me/mschrauzer) to encourage development. Thanks!

**FEATURES INCLUDE:**
- Resizable sidebar and directory/file preview pane.
- Arrow navigation in sidebar:
  - Up and Down Arrows select next/prev item.
  - Left and Right Arrows select next/prev item of same type.
- Navigate sidebar by typed string.
- Show/Hide file details (size (if avail), date modified (if avail), kind, extension).
- Sort sidebar items by name or file details.
  - Default sort = sort by name with folders on top.
- Preview all file types supported by browser (html, text, images, pdf, audio, video) plus fonts.
- Preview and edit markdown and plain text files.
  - Markdown rendered with markdownit.js ( https://github.com/markdown-it/markdown-it ).
  - Uses Github Markdown styles for preview ( https://github.com/sindresorhus/github-markdown-css ), with a few customizations.
  - Support for:
    - TOC creation ( `${toc}` ) ( https://github.com/nagaozen/markdown-it-toc-done-right )
    - Multimarkdown table syntax ( https://github.com/RedBug312/markdown-it-multimd-table )
    - Live checkboxes ( `\[ ], [x]` ), allowed in lists and deflists.
    - Superscript ( `^sup^` ) ( https://github.com/markdown-it/markdown-it-sup )
    - Subscript ( `~sub~` ) ( https://github.com/markdown-it/markdown-it-sub )
    - Definition lists ( https://github.com/markdown-it/markdown-it-deflist; for syntax, see http://pandoc.org/MANUAL.html#definition-lists )
    - Centered text ( `->centered<-` ) ( https://github.com/jay-hodgson/markdown-it-center-text )
    - Footnotes ( https://github.com/markdown-it/markdown-it-footnote )
  - View source text, preview, or split pane with proportional sync scroll.
  - Save edited source text or previewed HTML.
- Audio and video playback, with shuffle, loop, skip audio +/- 10 or 30 sec via keyboard.
  - Preview other files (e.g., lyrics or cover art) in same directory while playing audio.
  - User setting to autoload cover art (if any images in directory, load "cover.ext" or first image found)
- Open m3u playlists.
- Open fonts and view glyph repertoire.
  - Save glyphs as SVG.
- Grid views for images and/or fonts with keyboard navigation.
- User settings (see $settings in code; some settings can be changed via the main menu in the UI and will be remembered in URL query):
  - Light or Dark theme.
  - Bookmarks for local or remote directories.
  - Default image grid size.
  - Default UI font size and font-family.
  - Default UI font and font-size.
  - Default file sorting.
  - Sort with directories on top.
  - Treat apps as directories (MacOS and *nix only)
  - Show or hide invisible files.
  - Show or hide ignored files in the ignored files list (see $row_settings in code below $settings).
  - Show or hide file details.
  - Use custom file icons or browser defaults.
  - Autoload index.ext files.
  - Autoload cover art in directories with audio files.
  - Text editing default view: split, source, or preview.
  - Text editing sync scroll: on or off.

----

**KEYBINDINGS (These don't work in all browsers):**
- <kbd>Arrow Up/Down</kbd>: Select prev/next item.
  - If audio is playing, and prev/next file is also audio, it will be highlighted but not loaded in the audio player; press return to load it.
- <kbd>Arrow Left/Right</kbd>: Select prev/next row of the same kind as the current selection.
  - If current selection is a media file, select and begin playback of the next media item.
- <kbd>Opt/Alt + Arrow Left/Right</kbd>: Skip audio ±10s
- <kbd>Opt/Alt + Shift + Arrow Left/Right</kbd>: Skip audio ±30s
- <kbd>Cmd/Ctrl + Arrow Up</kbd>: Go to parent directory
- <kbd>Cmd/Ctrl + Arrow Down</kbd>: Open selected directory
- <kbd>Return</kbd>: Open selected directory, select file, or pause/play media.
- <kbd>Space</kbd>: Pause/Play media files
- <kbd>Cmd/Ctrl + D</kbd>: Toggle file details (size, date modified) in some index page types.
- <kbd>Cmd/Ctrl + G</kbd>: Show or Reset Grid
- <kbd>Cmd/Ctrl + I</kbd>: Toggle Invisibles
- <kbd>Cmd/Ctrl + Shift + O</kbd>: Open selected item in new window/tab
- <kbd>Cmd/Ctrl + R</kbd>: Reload grids and previewed content, reset scaled images/fonts, reset media files to beginning.
- <kbd>Cmd/Ctrl + W</kbd>: Close previewed content (doesn't work in all browsers; use close button instead), or close window if no content is being previewed.
- <kbd>Cmd/Ctrl + Shift + < or ></kbd>: Scale preview items and grids.

--------


