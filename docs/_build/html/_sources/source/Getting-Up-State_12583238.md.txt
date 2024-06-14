/\*<!\[CDATA\[\*/ div.rbtoc1718320079835 {padding: 0px;} div.rbtoc1718320079835 ul {list-style: none;margin-left: 0px;} div.rbtoc1718320079835 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [State Details](#GettingUpState-StateDetails)
    *   [State Overview](#GettingUpState-StateOverview)
    *   [Entry Requirements](#GettingUpState-EntryRequirements)
*   [Parameters](#GettingUpState-Parameters)
    *   [Base State Parameters](#GettingUpState-BaseStateParameters)
    *   [State Specific Parameters](#GettingUpState-StateSpecificParameters)

State Details
=============

State Overview
--------------

The GettingUp state allows the player to experience a more devastating repercussion when falling for a configured about of time.

Entry Requirements
------------------

This state is only accessible from two states, the Splatting state and the Sliding state. In the case of entering a GettingUp state from a Sliding state, the player must be sliding in an up-slope facing fashion.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

These state does not contain any state specific base state parameters.

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 100.0px;"><col style="width: 354.0px;"><col style="width: 708.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>State Duration</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Getting Up Settings</p></td><td class="confluenceTd"><p>The length of time to stay in this state. (Typically the length of the given animation, taking into account the animation speed) but this is completely up to the developer as to suit their needs.</p></td></tr></tbody></table>