/\*<!\[CDATA\[\*/ div.rbtoc1718320102676 {padding: 0px;} div.rbtoc1718320102676 ul {list-style: none;margin-left: 0px;} div.rbtoc1718320102676 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [State Details](#DivingState-StateDetails)
    *   [State Overview](#DivingState-StateOverview)
    *   [Entry Requirements](#DivingState-EntryRequirements)
*   [Parameters](#DivingState-Parameters)
    *   [Base State Parameters](#DivingState-BaseStateParameters)
    *   [State Specific Parameters](#DivingState-StateSpecificParameters)

State Details
=============

State Overview
--------------

The Diving state sends the player downward into an object that is specified in the swimmable layer mask. The player will shoot downwards until smoothly coming to a stop and ascending back to the surface. This state will also be exited if a surface is detected mid-dive, causing the player to return to the surface.

When attempting to dive from a Swimming state, surrounding checks are in place to detect surfaces that are too close to the player that may interfere with the dive. These surrounding checks can be configured to be less or more constrained by configuring the Dive Check Settings parameters in the Swimming state configuration.

Entry Requirements
------------------

To enter a Diving state, the player must be in a Swimming state along the surface of the Swimmable object. The player must press the dive input which is set in the Player Input System configuration to begin the dive.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

These state does not contain any state specific base state parameters.

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 100.0px;"><col style="width: 198.0px;"><col style="width: 864.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Diving Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The speed at which gravity is decreased. This variable is used to slow the dive until the maximum depth is reached or a surface is detected, in which the player will begin to rise back to the surface.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr></tbody></table>