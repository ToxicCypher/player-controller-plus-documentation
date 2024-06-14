/\*<!\[CDATA\[\*/ div.rbtoc1718320053190 {padding: 0px;} div.rbtoc1718320053190 ul {list-style: none;margin-left: 0px;} div.rbtoc1718320053190 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [State Details](#IdleState-StateDetails)
    *   [State Overview](#IdleState-StateOverview)
    *   [Entry Requirements](#IdleState-EntryRequirements)
*   [Parameters](#IdleState-Parameters)
    *   [Base State Parameters](#IdleState-BaseStateParameters)
    *   [State Specific Parameters](#IdleState-StateSpecificParameters)

State Details
=============

State Overview
--------------

This state is a general grounded state, supplying no movement whatsoever.

Entry Requirements
------------------

This state can be entered only when grounded and when the players directional input is not detected.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

This state does not contain any state specific base state parameters.

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 100.0px;"><col style="width: 198.0px;"><col style="width: 864.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Idle Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Jump Height From Idle</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Jump Variables</p></td><td class="confluenceTd"><p>The jump height applied from this state.</p></td></tr><tr><td class="confluenceTd"><p>Jump Time From Idle</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Jump Variables</p></td><td class="confluenceTd"><p>The jump duration applied from this state.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Moderate Slope Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Idle Settings</p></td><td class="confluenceTd"><p>The speed at which movement speed will be slowed while traveling up a moderate slope.</p></td></tr></tbody></table>