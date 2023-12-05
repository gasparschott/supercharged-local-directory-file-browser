# Changelog

### **VERSION 8.0.9.2** (2023-10-20)
**FIXED:** Audio player would be hidden when certain content types were being loaded.

### **VERSION 8.0.9.1** (2023-10-20):
**FIXED:** If the audio player was positioned at the bottom of the window it would revert to the default top position upon window resize.

### **VERSION 8.0.8.2** (2023-10-04): 
Another small fix for "quicklooked" audio files.

### **VERSION 8.0.8.1** (2023-09-25): 
A couple of fixes for the previous fixes.

### **VERSION 8.0.8** (2023-09-22): Mainly cuesheet menu improvements.
Note that .cue files cannot be read by the browser; however, if you change the extension to .cuetxt (and ensure that the file name exactly matches that of the associated media file), when you select the media file the script will automatically locate the .cuetxt file and load it for display in a menu item in the title area of the content pane.  
**FIXED:** Long cuesheet menus could not be scrolled.  
**FIXED (or improved):** The cuesheet tracklist menu only displayed the cumulative times for each track; now both the duration of the track and the cumulative time is displayed.  
**IMPROVED:** Click the cuesheet tracklist icon to keep the menu open without hovering; click again to toggle closed.  
**IMPROVED:** Added arrow key navigation to cuesheet tracklist menu.  
**IMPROVED:** Display the name of the currently playing cuesheet track in the audio player.  
**IMPROVED:** Automatically select the currently playing cuesheet track in the cuesheet menu when the player position changes (either by ordinary playback, user scrubbing, or clicking the audio player).  
**FIXED:** Video did not stop playing when other content was selected.  
**FIXED:** Remove cover art from quick-viewed audio items.  
**FIXED:** A few other small UI issues.

### **VERSION 8.0.7** (2023-09-04)  
**FIXED:** Clicking audio title w/o any other content open closes audio.
**FIXED:** Close quickview content when selected item is an ignored type.
**FIXED:** A nasty bug when changing the sidebar sort with open subdirectories.
**FIXED:** Multiple issues with selecting multiple dirs or files (images and fonts only) via the keyboard (Shift+ArrowKey); images and fonts now correctly open in the grid view and permit further selections.
**FIXED:** An issue where the texteditor would not receive focus on clicking.
**FIXED:** Various minor UI issues.
**IMPROVED:** Added UI Pref option to position audio player at bottom of content pane.
**IMPROVED:** Added the ability to select a range of items (dirs, fonts, or images only) by shift+click.
**IMPROVED:** Reselect sidebar item when content focused if it is not selected.
**IMPROVED:** Shuffle media play will now choose an item selected via the up/down arrow keys as the next item to play.
**OTHER:** Updated and overhauled the help page.

### **VERSION 8.0.6** (2023-08-22)  
**IMPROVED:** On autoload audio coverart, don't scroll sidebar item into view.  
**FIXED:** Several issues with fetching and refreshing media durations, especially when opening multiple subdirectories.  

### **VERSION 8.0.5** (2023-08-12)
**FIXED:** Some issues with arrow key navigation in font and image grids.  
**FIXED:** Clicking the checkbox next to the "Name" sorting item didn't toggle all media checkboxes.  
**FIXED:** An audio file loaded into the audio player from an opened subdirectory was not reselected after closing and opening the subdir.  
**FIXED:** Some issues with shuffle media play.
**FIXED:** An issue with hovering and simultaneously using the arrow keys to navigate the main menu.  
**FIXED:** Various issues that caused inaccurate media durations to be reported in the stats.  
**FIXED:** Various issues with the text file editor.  
**FIXED:** Closing a playlist where the media durations had not fully loaded could produce duration errors in media files (if any) in the previously opened directory.  
**FIXED:** Don"t reload currently playing video when arrow navigating from video to audio file and back to video.  
**FIXED:** Other minor UI issues.  
**IMPROVED:** Added an icon in the content title to allow quick toggling between text editing enabled/disabled modes.  
**IMPROVED:** Allow toggling between raw and styled text views when text editing is disabled.  
**IMPROVED:** Hide some text editing menu items when text editing is disabled.  
**OTHER:** Some code cleanup.

### **VERSION 8.0.4:** 2022-07-10
**FIXED:** Highlighting problem with items in previewed dirs.  
**CHANGED:** Allow pointer events in quicklooked items.

### **VERSION 8.0.3:** 2022-07-08  
A few more bugfixes
**FIXED:** Don't style list elements in previewed text and html files.
**FIXED:** Disable quicklook feature in previewed text and html files.
**FIXED:** Quicklooked text files should not display text editor UI.

### **VERSION 8.0.2**
**Quick fix:** Removed "about:blank" from @match rules.

### **VERSION 8.0.1: 2022-06-25**
Bugfixes
**FIXED:** Closing a previewed font glyph would close the font itself.  
**FIXED:** Quicklooked font files could not be closed.  
**FIXED:** Quicklooked text files should not display text editor UI.  
**FIXED:** Fonts in grid view could not be Quicklooked.  
**FIXED:** An issue with font specimen glyph display.  
**FIXED:** Scroll selected grid item into view after closing quicklooked grid item. 
**FIXED:** Text files would not display if text editing was disabled.  
**FIXED:** An issue with grid navigation.  
**FIXED:** Several issues with text editor split view display.  
Other small UI fixes.

### **VERSION 8: 2023-06-18**
**MAJOR UPDATE** with many additions, bugfixes, and potentially **BREAKING CHANGES**.

**IMPORTANT:** *After updating to this version, select “User Settings > Reset User Settings” from the main script menu, **or** delete the query string from the URL on all open tabs that use this script.* If you have bookmarked any pages, you will have to do the same thing and replace the bookmark. This is necessary because the behavior of user settings has changed and some old query strings no longer work. 
 
**IMPROVED:** Better handling of some remote server configurations.  
**IMPROVED:** Better handling of very large directories, which may take a long time to process.   
  - If the directory contains more than 5000 items, an alert will allow the user to cancel opening it.   
  - If there are more than 1000 image files, thumbnail display will be automatically disabled; it can be manually enabled *or* the user can select a new menu item, “Always show image thumbnails” to override this behavior.   
  - If there are more than 1000 media files, only the durations for the first 1000 items will requested.

**ADDED:** Pressing the “Escape” key or Cmd/Ctr + . will cancel content loading.  
**IMPROVED:** Better handling of php-based directories (e.g., those containing “index.php?folder=xyzxyz” items).  
**IMPROVED:** Some servers don’t correctly report media durations on initial page load; in such cases the script shows the duration as 0:00, and the file is marked disabled, even though the file is available on the server. Now you can refresh the duration individually by selecting such files, or globally (both in the sidebar and the content pane) via the main script menu > “Media Preferences > Refresh Media Durations.” Of course, if there really is a problem with the file or it is missing (e.g., from a playlist), the duration will not be updated and the file will still be disabled.  
**ADDED:** “Quicklook”-like feature (as in MacOS) for previewed directories: with the content pane focused, press spacebar to show a preview of the selected item, press again to close. Works for directories, image grids, and font glyph grids. Use arrow keys to navigate as usual.   
**CHANGED:** Rearranged main menu; removed “My Sample Bookmark Menu” and “Export Settings” items.  
**ADDED:** Menu item to show image thumbnails for dir items (in small or larger sizes) from main menu.  
**ADDED:** Menu item and shortcut to go to a sidebar item by its row number.  
**ADDED:** Set custom UI font from new main menu item.  
**ADDED:** Scale the UI (75%–125%) from new main menu item.  
**ADDED:** Select multiple dir items, either by Cmd-click, Shift-Up/Down Arrow, or Cmd-A (to select all). This allows multiple subdirectories to be opened or closed with one keystroke (Cmd-Left/Right Arrow). Multiple images/fonts will be displayed in a grid view. Other file types will be ignored (at least for now).  
**ADDED:** Font specimen previews: added ability to adjust font size, letter spacing, line height, text color, and text stroke (with browser support).  
**IMPROVED:** Font preview layout.  
**IMPROVED:** Font file glyph display and scaling.  
**IMPROVED:** Audio cover art: if there is an image file with *exactly* the same name as the selected audio file in the directory, it will be loaded as cover art; otherwise, images files named “cover”, “front”, etc., will be used (previous behavior). This allows each audio file to have its own cover art.  
**IMPROVED:** Audio cover art now loads only from the same directory as the selected audio item; useful when playing audio from subdirectories.  
**ADDED:** Show count of remaining media items when shuffle playback is checked.  
**ADDED:** Initial support for youtube links in m3u playlists  
**IMPROVED:** Playlists now use the name defined in EXTM3U instead of creating one from the link  
**IMPROVED:** Completed “Help” instructions on how to use the script.  
**IMPROVED:** Better notification for “file not found” errors; this happens mainly when clicking links in html files or using playlists.  
**IMPROVED:** Better handling of link files (.webloc/.url); now a clickable link is shown in content pane; (link files can still be opened from sidebar by double-clicking or cmd/ctr-arrowdown.)  
**IMPROVED:** Video player display.  
**IMPROVED:** Set default media volume to 50%.  
**IMPROVED:** Help menu: added more information and trouble-shooting section.  
**ADDED:** Display item description in remote directories (if provided by server).  
**ADDED:** Select main menu items by typed string and arrow navigation  
**FIXED:** Various issues with warnings not being shown when they should have been.  
**FIXED:** Sorting header display for previewed directories containing media files.  
**FIXED:** An issue with playing the next user-selected media item.  
**FIXED:** Media durations in subdirectories were not always displayed correctly.  
**FIXED:** Tab key navigation was not working in all cases.  
**FIXED:** Navigation history was not properly stored in some circumstances (mainly when opening subdirectories).  
**FIXED:** Long-standing problem with checkboxes in Firefox.  
**IMPROVED:** Reopening a subdirectory will reselect the currently displayed content pane item, if it is contained in that subdirectory.  
**REMOVED:** Option to set text editor theme independently from main UI theme as it added complexity without corresponding benefit.  
**OTHER:** Many other small improvements and bugfixes.  

-----
