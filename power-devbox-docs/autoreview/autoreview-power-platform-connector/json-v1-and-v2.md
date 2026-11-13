---
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

# JSON (v1 & v2)

{% hint style="info" %}
A fully working flow can be found here&#x20;

[https://powerdevbox.com/assets/AutoReviewDemo\_2\_0\_0\_1.zip](https://powerdevbox.com/assets/AutoReviewDemo_2_0_0_1.zip)
{% endhint %}



### Inputs (required)

<figure><img src="../../.gitbook/assets/image (223).png" alt="" width="563"><figcaption></figcaption></figure>

Display Name

Display name of the flow

#### Flow ID

Unique ID of the flow, recomed using Resource id or workflowid

#### Owner

Flow owner/maker

#### Environment

Environment name

#### Definition

Flow definition/clientData

### Inputs Optional

AutoReview allows configuration of the review metrics,  if left blank the review will follow the default values.

<figure><img src="../../.gitbook/assets/image (224).png" alt="" width="563"><figcaption></figcaption></figure>

* [complexity](../configs/complexity/ "mention")
* [naming-convention](../configs/naming-convention/ "mention")

_Scoring and Ratings are not currently used in JSON, but will be in a future update_

#### Complexity

New complexity items can be added with the 'Add new item' button. Though we recommend using the text mode (small pen in top right corner).&#x20;

<figure><img src="../../.gitbook/assets/image (88).png" alt="" width="185"><figcaption></figcaption></figure>

The [complexity json](../configs/complexity/complexity-template.md) object can then be edited in a source code editor (like Visual Studio Code or Notepad++) and then pasted in its entirety into the aComplexityTemplate input. With the reference inputted to the Reference Complexity.

<figure><img src="../../.gitbook/assets/image (225).png" alt="" width="563"><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (226).png" alt="" width="563"><figcaption></figcaption></figure>

#### Naming Convention

The [naming convention json](../configs/naming-convention/naming-template.md) has to be placed in 2 inputs.

<figure><img src="../../.gitbook/assets/image (227).png" alt=""><figcaption></figcaption></figure>

* Naming Char - char
* Data - data array.&#x20;



### Outputs

The JSON action returns all the key information about the flow in a json object. A full copy of the schema can be found here [data-json.md](../data-json.md "mention")

#### Data Object

<table><thead><tr><th width="231">Key</th><th width="316.66668701171875">Description</th><th width="873">Example</th></tr></thead><tbody><tr><td>name</td><td>Flow Display name</td><td>Test Flow</td></tr><tr><td>id</td><td>Flow Resource Id</td><td> a219f90b-b883-45af-aaf8-a3e7ba4d199c,</td></tr><tr><td>environment</td><td>Environment (not currently used)</td><td>Default</td></tr><tr><td>owner</td><td>Email of owner</td><td><a href="mailto:david@mail.com">david@mail.com</a></td></tr><tr><td>trigger</td><td>Trigger name</td><td> When_a_new_email_arrives_in_a_shared_mailbox_(V2),</td></tr><tr><td>triggerData</td><td>Stringifed JSON with all the key information about the trigger </td><td>{\"mailboxAddress\":\"testMailbox@mail.com;\",\"folderId\":\"Inbox\",\"importance\":\"Any\",\"hasAttachments\":false,\"includeAttachments\":false}</td></tr><tr><td>triggerParam</td><td>Stringifed JSON with all parameters from trigger</td><td>{\"host\":{\"apiId\":\"/providers/Microsoft.PowerApps/apis/shared_office365\",\"connectionName\":\"shared_office365\",\"operationId\":\"SharedMailboxOnNewEmailV2\"},\"parameters\":{\"mailboxAddress\":\"testMailbox@mail.com;\",\"folderId\":\"Inbox\",\"importance\":\"Any\",\"hasAttachments\":false,\"includeAttachments\":false},\"authentication\":\"@parameters('$authentication')\"}</td></tr><tr><td>triggerConfig</td><td>Stringifed JSON with trigger settings</td><td>none</td></tr><tr><td>triggerExpress</td><td>Any trigger conditions</td><td> @or(contains(triggerOutputs()?['body/subject'],'Report'),contains(triggerOutputs()?['body/subject'],'Data'))</td></tr><tr><td>triggerInputs</td><td>Any trigger inputs</td><td>{\"text\":{\"title\":\"resourceid\",\"type\":\"string\",\"x-ms-dynamically-added\":true,\"description\":\"Please enter your input\",\"x-ms-content-hint\":\"TEXT\"},\"text_1\":{\"title\":\"flowid\",\"type\":\"string\",\"x-ms-dynamically-added\":true,\"description\":\"Please enter your input\",\"x-ms-content-hint\":\"TEXT\"}}</td></tr><tr><td>triggerRecur</td><td>Trigger schedule (if applic)</td><td>{\"interval\":1,\"frequency\":\"Week\",\"timeZone\":\"UTC\",\"startTime\":\"2024-07-12T09:00Z\",\"schedule\":{\"weekDays\":[\"Sunday\"],\"hours\":[\"10\"],\"minutes\":[0]}}</td></tr><tr><td>premium</td><td>Uses premium connectors</td><td> false</td></tr><tr><td>connectionRefs</td><td>Count of Connection References</td><td>3</td></tr><tr><td>connectors</td><td>Count of api actions</td><td>13</td></tr><tr><td>steps</td><td>Count of all actions</td><td>55</td></tr><tr><td>variables</td><td>Count of variables</td><td>8</td></tr><tr><td>complexity</td><td>Complexity score</td><td>100</td></tr><tr><td>varNaming</td><td>All variables follow naming convention</td><td> true</td></tr><tr><td>varNameConsts</td><td>Declared variables follow const naming convention</td><td> false</td></tr><tr><td>varNameUse</td><td>All variables used</td><td> true</td></tr><tr><td>composes</td><td>Count of composes</td><td>4</td></tr><tr><td>exception</td><td>Count of exception actions (runAfter Failed)</td><td>0</td></tr><tr><td>exceptionHandleScope</td><td>Exception scope used</td><td> false</td></tr><tr><td>exceptionScope</td><td>Exception scope named 'Exception'</td><td> false</td></tr><tr><td>exceptionTerminate</td><td>Terminate used in exception block</td><td> false</td></tr><tr><td>exceptionLink</td><td>Exception expression link to run used</td><td> false</td></tr><tr><td>mainScope</td><td>Scope named 'Main'</td><td> false</td></tr><tr><td>variableArray</td><td>All variables in an array</td><td>SEE VARIABLE ARRAY</td></tr><tr><td>actionArray</td><td>All actions in an array</td><td>SEE ACTION ARRAY</td></tr><tr><td>apiActionArray</td><td>All actions that are api type in an array</td><td>SEE ACTION ARRAY</td></tr><tr><td>exceptionArray</td><td>All actions that have runAfter Failed in an array</td><td>SEE EXCEPTION ARRAY</td></tr><tr><td>connectionArray</td><td>All connection references used in an array</td><td>SEE CONNECTION ARRAY</td></tr><tr><td>actionObjectArray</td><td>All actions in an array but includes raw json object</td><td>SEE ACTIONOBJECTARRAY</td></tr></tbody></table>

#### Variable Array

<table><thead><tr><th width="173">Key</th><th width="338">Description</th><th width="873">Example</th></tr></thead><tbody><tr><td>name</td><td>Variable name</td><td>aTestVar</td></tr><tr><td>type</td><td>Type of variable</td><td>array</td></tr><tr><td>value</td><td>initialised Value</td><td>['a','b']</td></tr><tr><td>used</td><td>Is the variable used</td><td>FALSE</td></tr><tr><td>named</td><td>Does variable follow naming convention</td><td>TRUE</td></tr></tbody></table>

#### ActionArray

<table><thead><tr><th width="158">Key</th><th width="397.3333740234375">Description</th><th width="873">Example</th></tr></thead><tbody><tr><td>name</td><td>Action Display Name</td><td> Send_an_email_from_a_shared_mailbox_(V2)</td></tr><tr><td>step</td><td>Action Name</td><td> SharedMailboxSendEmailV2</td></tr><tr><td>type</td><td>Action Type</td><td> OpenApiConnection</td></tr><tr><td>id</td><td>Action ID</td><td> 1dafa9cb-455e-42fc-8445-4187dfa32fa5</td></tr><tr><td>hashId</td><td>As action id not uique, creates unique ref for flow</td><td> 1dafa9cb-455e-42fc-8445-4187dfa32fa5###32</td></tr><tr><td>tier</td><td>Premium or Standard</td><td> Standard</td></tr><tr><td>connector</td><td>Connection group</td><td> shared_office365</td></tr><tr><td>imgURL</td><td>Icon url</td><td><a href="https://connectoricons-prod.azureedge.net/releases/v1.0.1664/1.0.1664.3477/sharepointonline/icon.png">https://connectoricons-prod.azureedge.net/releases/v1.0.1664/1.0.1664.3477/sharepointonline/icon.png</a></td></tr><tr><td>runAfter</td><td>What the action runs after and method</td><td> Store_on_Exception_list: Succeed</td></tr><tr><td>exception</td><td>Does the runAdter include 'Failed'</td><td> Non-Exception</td></tr><tr><td>index</td><td>Order action processed (this is the order the actions are created in the designer)</td><td>4</td></tr><tr><td>complexity</td><td>Complexity score</td><td>3</td></tr><tr><td>detail</td><td>Stringified json of the actions inputs</td><td>{\"emailMessage/MailboxAddress\":\"ECSO_waste@tjxeurope.com\",\"emailMessage/To\":\"@variables('sEmail')\",\"emailMessage/Subject\":\"Wasted Journey Notification – Store @{items('Apply_to_each')?['store']} @{items('Apply_to_each')?['postcode']}\",\"emailMessage/Body\":\"\\n@{if(equals(items('Apply_to_each')?['img'],'Yes')\\r\\n,\\r\\n\\treplace(\\r\\n\\t\\toutputs('Update_email_YTD')\\r\\n\\t,\\r\\n\\t\\t'[Photo]'\\r\\n\\t,\\r\\n\\t\\t'*See attached picture taken.'\\r\\n\\t)\\r\\n,\\r\\n\\treplace(\\r\\n\\t\\toutputs('Update_email_YTD')\\r\\n\\t,\\r\\n\\t\\t'[Photo]'\\r\\n\\t,\\r\\n\\t\\t''\\r\\n\\t)\\r\\n)}\<br>\\n\",\"emailMessage/Attachments\":\"@variables('aImages')\",\"emailMessage/ReplyTo\":\mail@mail.com\"}</td></tr><tr><td>filter</td><td>Get Items filter parameter</td><td>Title eq 'Hello'</td></tr><tr><td>pagination</td><td>Get Items pagination threshold</td><td>1000</td></tr><tr><td>secure</td><td>Secure properties</td><td>{\"properties\":[\"inputs\",\"outputs\"]} *inputs,outputs</td></tr><tr><td>retry</td><td>Retry type</td><td>exponential</td></tr><tr><td>timeout</td><td>Timeout time</td><td>P1D</td></tr><tr><td>position</td><td>What the action runs after</td><td> | Store_on_Exception_list|</td></tr><tr><td>positionInfo</td><td>Is it inside a container (internal/external)</td><td>internal</td></tr><tr><td>environmentVariables</td><td>Environment variables within the action</td><td> null</td></tr><tr><td>environmentB</td><td>Contains environment variable</td><td> false</td></tr><tr><td>notes</td><td>Action notes</td><td>This is a note</td></tr><tr><td>parent</td><td>Name of parent container</td><td> Apply_to_each</td></tr><tr><td>branch</td><td>If inside branching container shows name</td><td>Yes</td></tr><tr><td>positionIndex</td><td>Index of parent container</td><td> |15</td></tr><tr><td>positionType</td><td>Parent Runs after type</td><td> |OpenApiConnection</td></tr><tr><td>nested</td><td>Levels of nesting (Example action is within action index 3 which is inside exception with index 24)</td><td> "3|24"</td></tr></tbody></table>

{% hint style="info" %}
* Proposed update to V2 API and V3.2.0 app/ext update to clean json to plane text
{% endhint %}



#### apiActionArray

Same structure as ActionArray

#### ExceptionArray

Same structure as ActionArray



#### ConnectionArray

<table><thead><tr><th width="158">Key</th><th width="317">Description</th><th width="873">Example</th></tr></thead><tbody><tr><td>conName</td><td>Connection name</td><td> shared_excelonlinebusiness,</td></tr><tr><td>appId</td><td>Connection id url */Connection Refernce</td><td> /providers/Microsoft.PowerApps/apis/shared_excelonlinebusiness * new_sharedsharepointonline_faec2</td></tr><tr><td>opId</td><td>Connection type</td><td> RunScriptProd,</td></tr><tr><td>count</td><td>Count of connection usage</td><td>1</td></tr></tbody></table>

{% hint style="info" %}
\*Propsed update for V2 api/connector and V3.2.0 App/Ext

In this update if it is a legacy export then will still show Connection id url, if its a solution aware export then it will show the connection reference name
{% endhint %}



#### ActionObjectArray

<table><thead><tr><th width="158">Key</th><th width="346.6666259765625">Description</th><th width="873">Example</th></tr></thead><tbody><tr><td>step</td><td>Action Name</td><td> If</td></tr><tr><td>connector</td><td>API connection type (only for actions with connection)</td><td> shared_excelonlinebusiness</td></tr><tr><td>name</td><td>Action Display Name</td><td> Condition</td></tr><tr><td>id</td><td>Action ID</td><td> ffbca394-0e04-4da7-8459-b70c7b74e98a</td></tr><tr><td>hashId</td><td>As action id not unique, creates unique ref for flow</td><td> ffbca394-0e04-4da7-8459-b70c7b74e98a###4</td></tr><tr><td>object</td><td>Stringified json of the action</td><td>{\"runAfter\":{\"Create_item\":[\"Succeeded\"]},\"expression\":{\"equals\":[\"@items('Apply_to_each')?['img']\",\"Yes\"]},\"metadata\":{\"operationMetadataId\":\"ffbca394-0e04-4da7-8459-b70c7b74e98a\"},\"type\":\"If\",\"operationName\":\"Condition\",\"nestedLevel\":1,\"parent\":\"Apply_to_each\",\"branch\":\"Yes\"</td></tr><tr><td>type</td><td>Action type</td><td> If</td></tr><tr><td>index</td><td>Order action processed (this is the order the actions are created in the designer)</td><td>4</td></tr><tr><td>parent</td><td>Container within</td><td> Apply_to_each</td></tr></tbody></table>



***

**Next Steps - File**

{% content-ref url="file-v2.md" %}
[file-v2.md](file-v2.md)
{% endcontent-ref %}

{% content-ref url="file-v1.md" %}
[file-v1.md](file-v1.md)
{% endcontent-ref %}
