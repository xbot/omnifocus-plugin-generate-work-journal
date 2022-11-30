# omnifocus-plugin-generate-work-journal
Collect today's work log and put it in the clipboard.

Each line starts with a task name, ends up with a status description. The status description will always be empty except when there is a note for the task or you've set the label for the 'done' status, links in the note content will be filtered out when appended to the work log.

## Quick Start Guide

### Installation

Clone the repo and link it in the Automation Configuration dialog in OmniFocus, or add it as a git submodule to the default plugin folder of OmniFocus. I recommend the latter for an easier synchronization with other devices.

```shell
cd ~/Library/Mobile Documents/iCloud~com~omnigroup~OmniFocus/Documents/Plug-Ins

git init

git submodule add https://github.com/xbot/omnifocus-plugin-generate-work-journal.git generate-work-journal

# For updating:
git submodule update --remote --recursive
```

### Configuration

This plugin must be configured to make it work.

Hold the Ctrl key and click the menu item Automation → generate-work-journal → Generate work journal, the preferences dialog will be opened.

#### Work journal folder

The work projects should always be put in a specified folder, set this option according to your situation.

#### Label for the done status

This label will be appended to each log if it is done. For example, if you set this option to 'Done!', then the generated journal may be as the following:

`DEV-2123 Send SMS Notification When a Session Is Started at an Abnormal Place Done!`

Leave it empty if you do not need anything appended.

#### Generic projects

Normally the work journal is in a format like 'PROJECT_NAME TASK_NAME STATUS', for those short tasks, we always put them in a specified project and don't want to append the project name in the generated content.

This option is in this purpose, select your generic projects and those names won't appear in the work journal.

#### Ignored tags

There are always some tasks that are not suitable to put in the work journal, you can identify them by using tags. Logs with tags selected in this option won't be put the generated content.

### Generate the work journal

You can either click the menu item 'Automation → generate-work-journal → Generate work journal' or the toolbar action.
