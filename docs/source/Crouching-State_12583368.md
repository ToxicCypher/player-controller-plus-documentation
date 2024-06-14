/\*<!\[CDATA\[\*/ div.rbtoc1718320084499 {padding: 0px;} div.rbtoc1718320084499 ul {list-style: none;margin-left: 0px;} div.rbtoc1718320084499 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [State Details](#CrouchingState-StateDetails)
    *   [State Overview](#CrouchingState-StateOverview)
    *   [Entry Requirements](#CrouchingState-EntryRequirements)
*   [Parameters](#CrouchingState-Parameters)
    *   [Base State Parameters](#CrouchingState-BaseStateParameters)
    *   [State Specific Parameters](#CrouchingState-StateSpecificParameters)

State Details
=============

State Overview
--------------

The Crouching state is used as a means for crouching while moving while grounded. This state is toggled on/off by providing the required crouch input, sending the player into this state. Crouching can be used for various gameplay mechanics such as ducking and sneaking.

Entry Requirements
------------------

To enter a crouching state, players must be in a grounded state while providing crouch input. Crouch input is set in the Player Input System configuration.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

These state does not contain any state specific base state parameters.

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 100.0px;"><col style="width: 198.0px;"><col style="width: 864.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Crouching Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Crouch Walk Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state while crouch walking.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Couch Cooldown</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Crouching Settings</p></td><td class="confluenceTd"><p>The wait time between crouches.</p></td></tr><tr><td class="confluenceTd"><p>Crouch Walking Settings</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Crouch Walking Settings</p></td><td class="confluenceTd"><p>The speed at which movement speed will be slowed while traveling up a moderate slope.</p></td></tr></tbody></table>