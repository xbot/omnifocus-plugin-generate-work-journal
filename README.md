# omnifocus-plugin-generate-work-journal
Collect today's work log and put it in the clipboard.

Each line starts with a task name, ends up with a status description. The status description will always be empty except when there is a note for the task or you've set the label for the 'done' status, links in the note content will be filtered out when appended to the work log.

## Quick Start Guide

### Dependencies

This plugin depends on the [omnifocus-plugin-libdev](https://github.com/xbot/omnifocus-plugin-libdev) library.

### Installation

Clone the repo and link it in the Automation Configuration dialog in OmniFocus, or add it as a git submodule to the default plugin folder of OmniFocus. I recommend the latter for an easier synchronization with other devices.

```shell
cd ~/Library/Mobile Documents/iCloud~com~omnigroup~OmniFocus/Documents/Plug-Ins

git init

# Install the dependent library, ignore this if you have already installed it.
git submodule add https://github.com/xbot/omnifocus-plugin-libdev.git libdev

git submodule add https://github.com/xbot/omnifocus-plugin-generate-work-journal.git generate-work-journal

# For updating:
git submodule update --remote --recursive
```

### Configuration

This plugin must be configured to make it work.

Hold the Ctrl key and click the menu item 'Automation → generate-work-journal → Generate work journal', the preferences dialog will be opened.

#### Work journal folder

The work projects should always be put in a specified folder, set this option according to your situation.

#### Output format

The generated content can be in any of the following formats:

- Plain text (default)
- Markdown ordered list
- Markdown unordered list

#### Status labels

Each completed task may have a status label appended. For example, if you set the label of the status 'done' to 'Done!', then the generated journal may be as the following:

`DEV-2123 Send SMS Notification When a Session Is Started at an Abnormal Place Done!`

Currently, there are three types of statuses: **in-progress**, **done** and **custom status**.

The in-progress status indicates that the completed task is a repeated one and there is still a remaining instance. For example, if I set a task to be repeated daily and marked it as completed today, then the task is considered to be in-progress. If I delete the remaining instance of this task, it indicates that the task is done.

Besides, if the situation is complicated and you have put some content in the note input box. It will be taken as the status label and appended to the end of the corresponding line instead of the previous labels.

If a completed task does not have a note and the status labels have not been set in the preferences, no status labels are appended to the end of each line.

#### Generic projects

Normally the work journal is in a format like 'PROJECT_NAME TASK_NAME STATUS', for those short tasks, we always put them in a specified project and don't want to append the project name in the generated content.

This option is in this purpose, select your generic projects and those names won't appear in the work journal.

#### Ignored tags

There are always some tasks that are not suitable to put in the work journal, you can identify them by using tags. Logs with tags selected in this option won't be put in the generated content.

### Generate the work journal

You can either click the menu item 'Automation → generate-work-journal → Generate work journal' or the toolbar action.
