# Flow Screen

The Flow Screen is for creating and modifying flows. The screen is split into 2, left pane for modifying the flows, right for modifying the solution.



### Left Pane

Each flow is stacked in the left pane, to open the flow click on the expand button in the top right corner

<figure><img src="../../.gitbook/assets/image (31).png" alt="" width="563"><figcaption></figcaption></figure>

#### Flow Details

The top of the Flow card shows key information and has 3 inputs

* Flow Name - click to edit
* Daily Runs - average daily times the flow will be triggered
* Days of Week - days flow runs



* Run Calls - how many api calls are used when the flow runs
* Daily Calls - how many total api calls per day (Run Calls \* Daily Runs)



#### Flow Builder

Below the Flow Details is the Flow Builder. The top level actions are any actions not in a loop or condition (aka containers).

{% hint style="info" %}
Please note:

Switches are not currently support (but averages can be used as a condition)

Both Apply to Each and Do Until's are loops

Scopes are counted as action

Get/List Item pagination calls are not counted
{% endhint %}



**Loop**

<figure><img src="../../.gitbook/assets/image (34).png" alt="" width="563"><figcaption></figcaption></figure>

Inside a loop there are 3 inputs:

* Loop Name - click to edit
* Child Actions - number of actions inside the Loop (excluding loops and conditions)
* Iterations - how many times the loop runs

**Condition**

<figure><img src="../../.gitbook/assets/image (33).png" alt="" width="563"><figcaption></figcaption></figure>

Inside a condition there are 5 inputs

* Condition Name - click to edit
* Yes % - how often this branch runs
* Yes Child Actions - number of actions inside the yes branch (excluding loops and conditions)
* No % - how often this branch runs
* No  Child Actions - number of actions inside the no branch (excluding loops and conditions)

{% hint style="info" %}
As both the loop and condition action use a api call there will be 1 added to the loop and 1 added to the Yes branch
{% endhint %}



To add a loop or condition click the relevant button, loops and conditions can be nested, with the container indenting a small amount to show.

<figure><img src="../../.gitbook/assets/image (32).png" alt="" width="563"><figcaption></figcaption></figure>

### Right Pane

The Right pane shows the Solution and is split into 3 main areas.

<figure><img src="../../.gitbook/assets/image (38).png" alt="" width="563"><figcaption></figcaption></figure>

Action Buttons

The action buttons update the solution.

* Add Flow - adds new flow to the Left Pane
* Save Solution - saves solution (will now appear in the solution screen and is saved locally)
* New Solution - resets the Flow screen for new solution
* Upload Solution Zip - imports a Power Automate Solution export and converts to Utilized flows
* Download Solution - downloads the solution as a Yaml file (so it can be imported to different instance of Flow Utilizer or to edit and re-import). See [solution-download.md](solution-download.md "mention")

#### Upload Solutions Additional Information

{% hint style="info" %}
Uploads Solution files are limited to information in the flows, so by default they will reset all loop iterations and condition ratios, but this information can be added to the flow, see Flow Tags section
{% endhint %}

If Flow Utilizer is [install](../install.md) as a app on your PC you are able to right click on solution.zip exports and load the solution directly into the app.

<figure><img src="../../.gitbook/assets/image (270).png" alt="" width="563"><figcaption></figcaption></figure>



#### Solution Details

Similar to the Flow Details, Solution Details includes key information and 1 input

* Solution Name - click to edit



* Flow Count - number of flows in the solution
* Total Daily Calls - all flow api calls. This does not take into account daily schedule, it is a theoretical maximum (Sum of all flow Daily Calls)

#### Flow Table

Shows list of all flows in the solution, with key information

<figure><img src="../../.gitbook/assets/image (39).png" alt="" width="563"><figcaption></figcaption></figure>
