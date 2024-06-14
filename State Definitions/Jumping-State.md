*   [State Details](#JumpingState-StateDetails)
    *   [State Overview](#JumpingState-StateOverview)
    *   [Entry Requirements](#JumpingState-EntryRequirements)
*   [Parameters](#JumpingState-Parameters)
    *   [Base State Parameters](#JumpingState-BaseStateParameters)
    *   [State Specific Parameters](#JumpingState-StateSpecificParameters)
*   [General Usage](#JumpingState-GeneralUsage)
    *   [Ceiling Detection](#JumpingState-CeilingDetection)
    *   [Jump Magnitude](#JumpingState-JumpMagnitude)

State Details
=============

State Overview
--------------

This state is used to send the player traveling upwards. This state only remains active while the player is holding the jump input, or when the players upward movement comes to a halt. If the player is actively traveling upwards and jump input is pressed, the player will remain in a jumping state up until the apex of the jump is reached.

Players will have control over the height of the jump depending on the length of time that jump input remains detected.

Entry Requirements
------------------

To enter the Jumping state, the player must be grounded while the player supplies jump input.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

This table defines configurable parameters that are related to this state but are shared between multiple states.

<table data-table-width="1382" data-layout="default" data-local-id="77a5e117-5ba8-4fa4-9128-9c4e0980aa84" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 100.0px;"><col style="width: 198.0px;"><col style="width: 864.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Ceiling Check Layer Mask</p></td><td class="confluenceTd"><p>LayerMask</p></td><td class="confluenceTd"><p>Ceiling Check Settings</p></td><td class="confluenceTd"><p>Detect a ceiling belonging to the supplied layers.</p></td></tr><tr><td class="confluenceTd"><p>Ceiling Check Distance</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Ceiling Check Settings</p></td><td class="confluenceTd"><p>The distance above the players origin that should be checked for a ceiling.</p></td></tr></tbody></table>

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 225.0px;"><col style="width: 95.0px;"><col style="width: 198.0px;"><col style="width: 864.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Movement Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Jumping Settings</p></td><td class="confluenceTd"><p>The speed at which the player should be able to redirect the character while in mid-air.</p></td></tr><tr><td class="confluenceTd"><p>Jump Cooldown</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Jumping Settings</p></td><td class="confluenceTd"><p>The duration the player must wait to jump again.</p></td></tr><tr><td class="confluenceTd"><p>Initial Jump Speed From Idle</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Jumping Settings</p></td><td class="confluenceTd"><p>The directional speed of the players jump, when jump is invoked from an Idle state. As the player should be still in an Idle state, to compensate for this, developers can provide an initial speed when entering the Jumping state from Idle to allow the player to move while jumping from an Idle state.</p></td></tr><tr><td class="confluenceTd"><p>Perform Initial Jump Rotation</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Initial Jumping Rotation</p></td><td class="confluenceTd"><p>Snap the players direction to the target direction when the jump state is entered.</p></td></tr></tbody></table>

General Usage
=============

This section covers some general usage topics for this state.

### Ceiling Detection

Using the ceiling detection parameters Ceiling Check Layer Mask and Ceiling Check Distance, developers can configure what surfaces can be used to detect what objects should be considered a ceiling. When a ceiling is detected and the player is in an airborne state, the player will be immediately sent back towards the ground, stopping all upward movement.

### Jump Magnitude

Jump magnitude is supplied by the state that has initiated the jump, this provides the ability for developers to configure how high a player can jump depending on its current state. For example, a developer may prefer that the player is only allowed to perform a short jump while jumping from an idle state and a long jump when jumping from a running state.