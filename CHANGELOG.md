## FazerWM 2026.10.29-beta — 2026-10-29

## What's new

- Overview thumbnails now carry a label showing the app icon and window title, so windows are easier to tell apart at a glance. Configure them under Settings > Overview > Window Labels.
- Recent windows cards show the app icon next to the app name. Toggle it under Settings > Recent Windows.

## Fixes

- Fixed a wake bug where a display's windows could end up on another display and stay there after the display returned, leaving conflicting layouts and an empty desktop.
- Windows keep their display and workspace assignments through brief display reconfigurations, such as waking from sleep or switching inputs.
- Dragging a file or selected text out of a window no longer brings up the drop-zone overlay when the pointer crosses onto another display.
- Apps that insist on their own window size, like a browser restoring its previous session, are now sized correctly instead of keeping the wrong height.
- Reopening the overview no longer shows a stale app label or a stuck expanded label.

---

## FazerWM 2026.10.26 — 2026-10-26

FazerWM 2026.10.26 (stable channel). See https://fazerwm.app for details.

---

## FazerWM 2026.10.26-beta — 2026-10-26

## What's new

- Pausing a window drag at a screen edge now moves between workspaces: left and right edges scroll the workspace a column at a time, top and bottom switch to the workspace above or below, and the bottom edge offers a new workspace when the last one is occupied. Parked-window thumbnails drag the same way, and with coupled workspaces every display switches together. A quick pass through an edge does nothing, so dragging between displays is unchanged. (Pro)
- Pressing the overview key mid-drag continues the drag inside the overview, so a window can be dropped on any workspace, on any display. (Pro)
- Dragging a thumbnail past the edge of an overview row now scrolls that row while the pointer rests on the band. The row keeps its scrolled position after the drop and springs back otherwise.
- Drop zones have a new pill style with an icon and a label naming the action ("New column", "Stack above", "Add as tab"), and the edge bands have bolder indicators that stand out against window borders.
- The Pro pane in Settings now lists the drag features included with Pro.

## Fixes

- Releasing a drag away from every drop zone after an edge switch now moves the window onto the workspace in view, instead of leaving it behind on the workspace it came from.

---

## FazerWM 2026.10.26-beta — 2026-10-26

## What's new

- Drag a parked window by its thumbnail's title band to pick up the real window and drop it straight onto a drop zone.
- The trial-expired dialog is now an animated rundown of what the free tier removes, and its Continue button waits out a 10-second countdown before it can be clicked.
- Text editing shortcuts (⌘C, ⌘V, ⌘X, ⌘Z, ⌘A) now work in Settings and setup-assistant text fields; previously only the right-click context menu did.
- The Screen Recording button in the setup assistant reads "Request Access" instead of "Request…", which looked like truncated text.

## Fixes

- Drop zones during a window drag now appear without delay, including drags that cross from one display to another, which could previously leave the zone missing entirely.
- A long drag no longer teleports the window off the pointer partway through.
- Clicking or dragging a partially offscreen window no longer jumps the workspace view mid-gesture.
- After dropping a window to the right of a column, the view no longer scrolls to it and then snaps back.
- A window whose position took a moment to settle no longer gets repositioned over and over, which could steal focus for several seconds.
- Fixed a rare case where the setup assistant's keybindings step could overwrite an existing config file, losing settings such as window rules.

Also includes internal improvements.

---

## FazerWM 2026.10.21-beta — 2026-10-21

## What's new

- Settings got a full visual overhaul: every pane now shares one row and section layout, controls line up across tabs, text fields for rule names and regexes get more room, and locked or inactive settings share one dimmed look.
- New Support section in Settings, with a "Copy support summary" action that puts the version, build and device ID on the clipboard, plus links to Discord, email and the docs.
- The first-launch assistant is easier to follow: steps show plain-language statuses, and the Screen Recording permission now leads with what it is for, window previews in Overview, the switcher and tab hovers, and notes that captures stay in memory and are never saved or sent.
- Deactivating a license key now asks for confirmation first.

## Fixes

- License activation failures are no longer silent: an invalid, refunded or device-limited key now shows an error message instead of appearing to do nothing.
- Several settings displayed defaults the app never used, including the tab gap, the overview thumbnail toggle and the focus ring corner radius; the shown values now match the real ones.
- Firefox windows relocated to avoid the mouse across displays no longer land mid-screen.
- Moves issued over IPC now place windows correctly.
- In the Binds tab, clicking a workspace group's title now expands it; previously only the small caret worked.
- Pressing Record on a keybind no longer shifts the shortcut field sideways.

Also includes internal improvements.

---

## FazerWM 2026.10.19-beta — 2026-10-19

## What's new

- Keybind and gesture settings now flag duplicate bindings. A banner and captions on the affected rows name the conflicts, and a conflict you introduce while editing blocks saving until it's resolved. Conflicts already present in the config file stay advisory.
- The Pro pane now links to the website for current plans and pricing instead of embedding prices in the app, and purchase links are enabled again.
- The free tier now tiles up to 8 windows. The cap applies only to newly tiled windows, so a trial ending mid-layout never evicts what's already laid out; windows beyond it float in place, the status bar shows how many slots are in use, and upgrading re-tiles everything the cap floated.
- Deactivate now works from lapsed installs too, so a Mac whose coverage window has passed can still free its license slot for another machine. A failed deactivate now shows an error instead of failing silently.

## Fixes

- Powering a monitor off and back on no longer collapses the layout. Reconnects used to arrive staggered, and the first one-screen event would cram everything onto the surviving display, scrambling column order and stranding windows; the layout now waits for the full display set to return and comes back unchanged.
- Windows placed in a named workspace by a rule stay there while displays reconnect, instead of being dropped onto a numbered workspace.
- Switching windows no longer snaps focus back to a parked native tab group a second later.
- Fixed a positioning bug that could park a window with only its title bar visible.
- Parked native tab groups no longer show blank thumbnails, and clicking one brings the right tab forward.
- Native tab groups move as a single unit between workspaces, and closing a tab now returns focus to the group instead of an arbitrary window.
- When a trial expires, windows parked in named workspaces now move to Workspace 1 instead of becoming unreachable, and windows floated past the cap while parked off-screen are brought back on screen.
- Also includes internal improvements.


---

## FazerWM 2026.10.06-beta — 2026-10-06

## What's new

- The free tier now only has a single workspace per display. When a trial ends, windows from the other workspaces are folded into Workspace 1, and the trial-expired dialog explains what changed on screen.
- Layouts now adapt when the menu bar's auto-hide setting changes or when SketchyBar starts, quits, or changes its inset, so tiling no longer keeps reserving space that is not there.
- Window rules and named workspaces can be duplicated in Settings. Saving is prevented while a duplicate is still identical to its original, and a banner explains what needs to be resolved first.
- In the keybinds panel, workspace groups now carry the Pro lock badge on the free tier, with a caption explaining that the badge marks Pro features and that your bindings are kept.
- Workspace keybindings (focus workspace, move column to workspace, move window to workspace) are indicated as Pro features. Bindings you have already configured are preserved and reactivate when you upgrade.
- Settings sidebar sections are sorted alphabetically within their groups.

## Fixes

- Fixed a crash when clicking the Override button on a window rule's width field.
- Text in Settings no longer renders upside down when the window is opened from the trial-expired dialog's "Enter License Key" button.
- Tab indicators no longer stay in their old spot after a display is reconnected or reconfigured; they follow the window again.
- Also includes internal improvements to build and release tooling.


---

## FazerWM 2026.09.30-beta — 2026-09-30

## Fixes

- Fullscreen windows in Firefox, VS Code, and other Electron apps are now detected correctly, so FazerWM no longer raises other windows over fullscreen video or draws focus rings on top of it.
- A window rule with an unsafe regex pattern no longer stalls the app: the rule is flagged in Settings with a banner, a marker on the rule row, and a note in the editor, and the pattern simply stops matching until you edit it.
- The update window from "Check for Updates…" no longer opens hidden underneath the Settings window.
- Long error messages in Settings no longer stretch the window to the full height of the screen.


---

## FazerWM 2026.09.28-beta — 2026-09-28

## What's new

- Torn-off window tabs now land in their own column instead of stacking back into the window they came from.
- Drop zones now cover the whole window rather than just the title area, so tabs dragged out of side panels can be placed too. Firefox can't display zones during a drag, but its torn tabs still land correctly.
- Workspace up/down shortcuts now default to Hyper+' and Hyper+/ instead of PageUp/PageDown, which many laptop keyboards lack.
- Update dialogs now show the notes for each release instead of embedding webpage.

## Fixes

- The focus ring now redraws at the right size when layout resizes the focused window, for example when it expands after its column-mate closes. Previously it could stay at the old size until the next window event.
- Fixed the appcast download URLs so updates fetch the correct file.
- Also includes internal improvements to the release pipeline.


---

## FazerWM 2026.09.27-beta — 2026-09-27

## What's new

- Step through workspaces one at a time with hyper+Page Up/Page Down, or by swiping up or down with three fingers while holding hyper. Steps move through every workspace on a display, stop at the ends, and never create a new one; with coupled workspaces, all displays step together.

- Tearing a tab off in Chrome now works with drop zones. The torn window is held aside for the whole drag, so the layout doesn't reshuffle or steal focus while you're still moving, and it lands in the zone you release over.

Also includes internal improvements.


---

## FazerWM 2026.09.26-beta — 2026-09-26

## Notes

This is the first public beta release of FazerWM, a keyboard-driven tiling window manager for macOS. It is free to try.

- Windows tile into columns across workspaces, and every display keeps its own stack of numbered or named workspaces. A first-launch assistant walks you through permissions and hyper-key setup.
- Move things three ways: keyboard chords (Shift moves a window, Option moves a column), trackpad gestures, or dragging with live drop-zone previews for merges, tabs, and cross-display moves.
- The overview lays out every workspace as live thumbnails: click a window to jump to it, or drag one to another workspace or display.
- `Option+Tab` and `` Option+` `` flip through your most recent windows, window by window instead of app by app.
- A column can hold its windows as tabs or a stack, native macOS tab groups (like Terminal's ⌘T) included, and any window can park at a screen edge with a narrow peek.
- Everything is configurable in the settings window or a YAML config file, with per-app window rules, vi and emacs directional presets, and built-in SketchyBar integration.