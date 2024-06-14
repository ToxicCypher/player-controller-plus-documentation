
*   [Summary](#SwimmingState-Summary)
*   [State Details](#SwimmingState-StateDetails)
    *   [State Overview](#SwimmingState-StateOverview)
    *   [Entry Requirements](#SwimmingState-EntryRequirements)
*   [Parameters](#SwimmingState-Parameters)
    *   [Base State Parameters](#SwimmingState-BaseStateParameters)
    *   [State Specific Parameters](#SwimmingState-StateSpecificParameters)
*   [General Usage](#SwimmingState-GeneralUsage)
    *   [Pre-Dive Checks](#SwimmingState-Pre-DiveChecks)

Summary
=======

State Details
=============

State Overview
--------------

The Swimming state is used as a means of aquatic traversal of objects that are supplied to any of the layers specified in the state manager base configurations Swimming Layer Mask parameter.

When entering a Swimming state, players can simply move into a Swimming state by walking/running into the object or players can jump/fall into the object. When jumping/falling into the swimmable object, the magnitude of the downward force will dictate the depth that the player will sink to before resurfacing when the Swimming state is entered, providing simulated buoyancy.

Entry Requirements
------------------

To enter a Swimming state, the player must come into contact with a game object that is provided to any of the specified layers in the base state manager configurations Swimming Layer Mask parameter.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

This table defines configurable parameters that are related to this state but are shared between multiple states.

<table data-table-width="1382" data-layout="default" data-local-id="ba3f828a-f7ee-489c-87b3-cc7749cdfdcd" class="confluenceTable"><colgroup><col style="width: 219.0px;"><col style="width: 105.0px;"><col style="width: 207.0px;"><col style="width: 851.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Swimming Layer Mask</p></td><td class="confluenceTd"><p>LayerMask</p></td><td class="confluenceTd"><p>Swimmable Check Settings</p></td><td class="confluenceTd"><p>The layers that Swimmable objects exist on.</p></td></tr><tr><td class="confluenceTd"><p>Swim Check Distance</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Swimmable Check Settings</p></td><td class="confluenceTd"><p>The downward distance from the players origin that checks for swimmable collision.</p></td></tr><tr><td class="confluenceTd"><p>Swim Check Origin Offset</p></td><td class="confluenceTd"><p>Vector3</p></td><td class="confluenceTd"><p>Swimmable Check Settings</p></td><td class="confluenceTd"><p>The offset from the player origin that the swimmable raycast starts from.</p></td></tr></tbody></table>

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 100.0px;"><col style="width: 198.0px;"><col style="width: 864.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Swimming Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Allow Jump From Swim</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Jump Variables</p></td><td class="confluenceTd"><p>When true, player can jump from swim.</p></td></tr><tr><td class="confluenceTd"><p>Jump Height From Swimming</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Jump Variables</p></td><td class="confluenceTd"><p>The jump height applied from this state.</p></td></tr><tr><td class="confluenceTd"><p>Jump Time From Swimming</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Jump Variables</p></td><td class="confluenceTd"><p>The jump duration applied from this state.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Buoyancy Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Swimming Settings</p></td><td class="confluenceTd"><p>The speed at which the player will reach peak buoyancy.</p></td></tr><tr><td class="confluenceTd"><p>Surfacing Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Swimming Settings</p></td><td class="confluenceTd"><p>The speed at which the player will rise to the surface after plunging into a Swimmable source.</p></td></tr><tr><td class="confluenceTd"><p>Swimmable Tilt Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Swimming Settings</p></td><td class="confluenceTd"><p>The speed at which the tilt will occur when swimming.</p></td></tr><tr><td class="confluenceTd"><p>Swimming Slope Limit</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Swimming Settings</p></td><td class="confluenceTd"><p>The Character Controller slope limit while swimming. Stops the player from grounding onto undesired surfaces.</p></td></tr><tr><td class="confluenceTd"><p>Climbable Distance From Surface</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Swimming Settings</p></td><td class="confluenceTd"><p>The minimum distance from the surface of a body of water that the player can be in-order to enter a Climbing state.</p></td></tr><tr><td class="confluenceTd"><p>Dive Check Layer Mask</p></td><td class="confluenceTd"><p>LayerMask</p></td><td class="confluenceTd"><p>Dive Check Settings</p></td><td class="confluenceTd"><p>A LayerMask containing all layers that if detected, should disable the ability to dive.</p></td></tr><tr><td class="confluenceTd"><p>Dive Check Distance</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Dive Check Settings</p></td><td class="confluenceTd"><p>This distance at which the player checks for ground beneath the player. If detected, diving becomes disabled.</p></td></tr></tbody></table>

General Usage
=============

This section covers some general usage topics for this state.

### Pre-Dive Checks

When in a Swimming state, configuration can be set to disallow the entry of a Diving state by providing some pre-transition checks. The two variables that control these checks are Dive Check Layer Mask and Dive Check Distance. These two variables are used in tandem to check the players surrounding area for any obstacles that may interfere with a dive.

Developers can disable these checks by simply setting the Dive Check Distance parameter to 0, or by providing no layers to the Dive Check Layer Mask parameter.