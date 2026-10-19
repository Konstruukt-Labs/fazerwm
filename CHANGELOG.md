# Changelog

Every FazerWM release, newest first. Entries are archived here at publish
time, so their notes survive even if a release is later removed from the
[releases page](https://github.com/Konstruukt-Labs/fazerwm/releases). The
same text appears in the app's update dialog.

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
