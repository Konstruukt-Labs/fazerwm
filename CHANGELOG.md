## FazerWM 2026.11.06 — 2026-11-06

## What's new

- Session restore (Pro). FazerWM saves your layout as you work and puts it back after a FazerWM restart, a reboot or a logout: each window returns to its display, workspace and column, stacked and tabbed columns regroup, manual widths and floating positions come back, and the window you were using gets focus again. After a reboot it waits up to a minute for your apps to reopen their windows and shows a "Restoring your layout" panel while it places them. Plugging in a display setup you have used before moves windows back to the displays they were on, and a setup it has not seen is laid out from the most recent one.
- macOS native fullscreen now works alongside the tiling layout. A fullscreen window keeps its column, with a placeholder holding the gap on the desktop and in the Overview, and fullscreen windows show an icon in Recent Windows. Leaving fullscreen puts the window back in its column and takes you to its workspace. Starting FazerWM while an app is fullscreen now finds the windows on the desktop behind it. Window rules take precedence over fullscreen: the green button on a rule-managed window shows a short note instead.
- Minimizing windows works. A minimized window leaves its column and the others close up. Restoring it from the Dock, Recent Windows or the Overview brings it back as a new column after the focused window, on that window's display, and focuses it. Minimizing the focused window passes focus on the way closing one does. The Overview shows minimized windows along the bottom edge of each display: hover one to see it in full, click to restore.
- Overview column drags (Pro). Hold the column-drag modifier while dragging a thumbnail to move a whole column, with stacked windows and tab indicators carried along. The drag keeps going when you close the Overview mid-drag or carry it onto the desktop. Dropping a column on another column's middle merges it as a stack or as tabs. Dragging from desktop to Overview works as well.
- The Recent Windows switcher can take over ⌘Tab, ⌘⇧Tab, ⌘` and ⌘⇧` (Pro, off by default).
- Overview window labels and app icons in the Recent Windows switcher are new Pro features.
- The trial-ended dialog and the Pro tab link to the full Free vs Pro table.
- FazerWM launches faster. Windows are tiled about 45 percent sooner, the menu bar icon and login-item setup no longer delay the first layout, and keybinds and gestures stay responsive while it starts.

## Fixes

- Fixed-size windows such as balenaEtcher no longer flick between sizes or make the focus ring jitter, and windows with a minimum height such as Bambu Studio are no longer fought over their size.
- Pointer follows focus now lands inside the window when you focus a column that was off screen.
- Apps hidden with ⌘H come back when their window returns to the visible layout. Before, the window could stay invisible until you focused it.
- A window that an app rebuilds, such as an Electron reload, now returns to its tile instead of staying invisible.
- A quick click on a title bar no longer switches workspaces or hides the windows you were looking at.
- Dropping a window in the gap between stacked windows now inserts it between them.
- Switching workspaces with a keybind while dragging now refreshes the drop zones, so the drop lands on the workspace you can see.
- Closing the Overview in the middle of a drag no longer leaves it blank the next time you open it.
- Fixed a crash when dragging a window across displays.

Also includes internal improvements.

---

## FazerWM 2026.10.26 — 2026-10-26

## What's new

This is the first stable release of FazerWM, a keyboard-driven tiling window manager for macOS. It is free to try.

- Windows tile into columns across workspaces, and every display keeps its own stack of numbered or named workspaces. A first-launch assistant walks you through permissions and hyper-key setup, with plain-language statuses and an explanation of what Screen Recording is used for.
- Move things three ways: keyboard chords (Shift moves a window, Option moves a column), trackpad gestures, or dragging with live drop-zone previews for new columns, stacks, tabs and cross-display moves. Drop zones cover the whole window, use a labeled pill style, and torn-off tabs (Chrome included) land in their own column.
- Pausing a window drag at a screen edge moves between workspaces: left and right scroll a column at a time, top and bottom switch workspace, and the bottom edge offers a new workspace when the last is occupied. Pressing the overview key mid-drag continues the drag inside the overview. (Pro)
- The overview lays out every workspace as live thumbnails: click a window to jump to it, or drag one to another workspace or display. Rows scroll while you drag past their edge, and a parked window can be picked up by its thumbnail's title band.
- Option+Tab and Option+` flip through your most recent windows, window by window instead of app by app.
- A column can hold its windows as tabs or a stack, native macOS tab groups included, and any window can park at a screen edge with a narrow peek.
- Step through workspaces one at a time with Hyper+' and Hyper+/, or by swiping up or down with three fingers while holding hyper. With coupled workspaces, all displays step together.
- Layouts adapt when the menu bar's auto-hide setting changes or SketchyBar starts, quits or changes its inset.
- Window rules and named workspaces can be duplicated in Settings, and unsafe regex patterns are flagged instead of stalling the app.
- Keybind and gesture settings flag duplicate bindings, and a conflict you introduce while editing blocks saving until it is resolved.
- Settings has a new layout across every pane and a Support section with a "Copy support summary" action. Text editing shortcuts work in Settings text fields.
- The free tier tiles up to 8 windows and has one workspace per display. When a trial ends, windows from other workspaces fold into Workspace 1 and nothing already laid out is evicted. Pro features carry a lock badge, and configured bindings are kept and reactivate when you upgrade.
- License activation failures show an error message. Deactivating asks for confirmation first and works from lapsed installs, so a Mac can free its license slot for another machine.
- Update dialogs show the notes for each release.

Also includes internal improvements.

---

