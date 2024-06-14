/\*<!\[CDATA\[\*/ div.rbtoc1718320077572 {padding: 0px;} div.rbtoc1718320077572 ul {list-style: none;margin-left: 0px;} div.rbtoc1718320077572 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [State Details](#SoftLanding|HardLanding|SplattingStates-StateDetails)
    *   [State Overview](#SoftLanding|HardLanding|SplattingStates-StateOverview)
    *   [Entry Requirements](#SoftLanding|HardLanding|SplattingStates-EntryRequirements)
*   [Parameters](#SoftLanding|HardLanding|SplattingStates-Parameters)
    *   [Base State Parameters](#SoftLanding|HardLanding|SplattingStates-BaseStateParameters)
    *   [State Specific Parameters](#SoftLanding|HardLanding|SplattingStates-StateSpecificParameters)

State Details
=============

Due to the similar nature of the Soft Landing, Hard Landing and Splatting states, all three states are described here.

State Overview
--------------

The Soft Landing, Hard Landing and Splatting states are provided to allow the player experience impact when falling for a configured about of time.

Unlike the Soft & Hard Landing states, Splatting requires the player to enter a Getting Up state after the Splatting state has finished its lifecycle.

Entry Requirements
------------------

These states can be entered only when the player has been in a Falling state for a configured period of time without becoming grounded.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

These state does not contain any state specific base state parameters.

### State Specific Parameters

This table defines configurable parameters that are utilized solely by these states.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 100.0px;"><col style="width: 354.0px;"><col style="width: 708.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>State Duration</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Soft Landing | Hard Landing | Splatting Settings</p></td><td class="confluenceTd"><p>The length of time to stay in this state. (Typically the length of the given animation, taking into account the animation speed) but this is completely up to the developer as to suit their needs.</p></td></tr></tbody></table>