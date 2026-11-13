---
icon: share-nodes
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: false
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
  anchors:
    visible: true
---

# Utility

<figure><img src="../../../.gitbook/assets/utility grey 128.png" alt=""><figcaption></figcaption></figure>

### Setup

Power DevBox Utility is a side panel extension, so it is designed to be open with Power Automate. Clicking on the icon will open the side panel, clicking the top left cross will close the panel.

Utility defaults to Power Automate screen you are on, if you are editing a flow it will show Clipboard mode, else it will show History Mode

### Functionality

Utility has the following functions:

* UI
  * Classic
  * Automatic
* Mode
  * History
    * Previous Flows
  * Clipboard
    * Actions Available
    * Add to Clipboard
    * Import to Clipboard
* Close after paste
* Hot Keys
* Beta UI
* Guide
* Buy Me a Coffee

### UI

The UI settings allows you to override the default to New UI and forces Power Automate to load in the Classic UI. The Automatic option follows what you have selected, so defaults to New but remembers if you toggle to Classic for that flow.

### Mode

#### History

<figure><img src="../../../.gitbook/assets/image (204).png" alt="" width="415"><figcaption></figcaption></figure>

Utility runs in the background and saves the last 50 flows you have edited. Clicking on the flow name will open the flow in the editor mode.

Clicking the trash can icon <img src="../../../.gitbook/assets/image (99).png" alt="" data-size="line">will delete the flow from the history.

Entering a flow name or environment name will filter the history to show related flows.

<figure><img src="../../../.gitbook/assets/image (205).png" alt="" width="408"><figcaption></figcaption></figure>

#### Clipboard

Clipboard saves copied actions and containers for future use. Due to how Power Automate is setup the Classic and New UI save actions differently, so you will see only actions added for the relevant UI (i.e. you will have to add the action in both UI's if you want to use it in both).

<figure><img src="../../../.gitbook/assets/image (206).png" alt="" width="416"><figcaption></figcaption></figure>

For Classic UI users see [here](classic-ui-clipboard.md) and for New UI users click [here](new-ui-clipboard.md)

### Import to Clipboard

<figure><img src="../../../.gitbook/assets/image (100).png" alt="" width="173"><figcaption></figcaption></figure>

To import export clipboard item, click the Import to Clipboard menu option, this will open fil picker, select your export file (will be a .txt file) and if it is valid it will add to the clipboard list.

Please note it is possible to open the export files in any text editor (like notepad) and make changes to the action/container json. So in theory you could create your own configured actions/containers.

### Close after paste

<figure><img src="../../../.gitbook/assets/image (211).png" alt="" width="284"><figcaption></figcaption></figure>

This setting will automatically close the Utility side panel after pasting. If set to false then the side panel will remain open.

### Hot Keys

<figure><img src="../../../.gitbook/assets/image (102).png" alt="" width="152"><figcaption></figcaption></figure>

Hot Keys enable shortcut keys for Power Automate.

| ALT  + t   |  Rerun most recent test                         |
| ---------- | ----------------------------------------------- |
| ALT  + p   |  Adds most recent action to flow                |
| ALT  + s   |  Saves flow (Classic UI) / Saves draft (New UI) |
| ALT  + z   |  Undo                                           |
| ALT  +  c  |  Opens flow checker                             |
| ALT + q    | Edit mode from flow run screen                  |
| ALT + x    | Toggle Copilot on/off (New UI only)             |
| ALT + +    | Zoom in (New UI only)                           |
| ALT + -    | Zoom out (New UI only)                          |

### Beta UI (Classic UI Only)

<figure><img src="../../../.gitbook/assets/image (101).png" alt="" width="145"><figcaption></figcaption></figure>

The Beta UI automatically enables the Experimental Features option from the  'View all Power Automate Settings'.

<figure><img src="../../../.gitbook/assets/image (103).png" alt=""><figcaption></figcaption></figure>

The Beta UI shows a new improved Dynamic Value and Expression selector popup in the Classic UI

<figure><img src="../../../.gitbook/assets/image (105).png" alt=""><figcaption></figcaption></figure>

Please note as stated, this is experimental and support has been discontinued due to the New UI, so this will not improve and is buggy (so it does not always show and has other issues, this is not caused by Power DevBox Utility).
