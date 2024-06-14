/\*<!\[CDATA\[\*/ div.rbtoc1718320090572 {padding: 0px;} div.rbtoc1718320090572 ul {list-style: none;margin-left: 0px;} div.rbtoc1718320090572 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [State Details](#ClimbingState-StateDetails)
    *   [State Overview](#ClimbingState-StateOverview)
    *   [Entry Requirements](#ClimbingState-EntryRequirements)
*   [Parameters](#ClimbingState-Parameters)
    *   [Base State Parameters](#ClimbingState-BaseStateParameters)
    *   [State Specific Parameters](#ClimbingState-StateSpecificParameters)
*   [General Usage](#ClimbingState-GeneralUsage)
    *   [Defining Climbable Surfaces](#ClimbingState-DefiningClimbableSurfaces)
    *   [Interval Climb](#ClimbingState-IntervalClimb)
    *   [Climb Jumping](#ClimbingState-ClimbJumping)
    *   [Ledge Climbing](#ClimbingState-LedgeClimbing)
    *   [Ledge Jumping](#ClimbingState-LedgeJumping)
    *   [Climbing Guard Rails](#ClimbingState-ClimbingGuardRails)
        *   Climbing Gallery

State Details
=============

State Overview
--------------

This state is used to scale over objects that have been configured in your scenes that are assigned to a layer that is configured to detect climbable surfaces. This state allows traversal over surfaces that are not walkable in an omni-directional fashion.

Entry Requirements
------------------

This state can be entered from multiple states that include airborne states, grounded states and aquatic states. The player can transition to a climbing state only when a climbable surface is detected, what a climbable surface is, is completely definable by the developer.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

This table defines configurable parameters that are related to this state but are shared between multiple states.

<table data-table-width="1382" data-layout="default" data-local-id="ba3f828a-f7ee-489c-87b3-cc7749cdfdcd" class="confluenceTable"><colgroup><col style="width: 219.0px;"><col style="width: 105.0px;"><col style="width: 198.0px;"><col style="width: 860.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Ledge Check Layer Mask</p></td><td class="confluenceTd"><p>LayerMask</p></td><td class="confluenceTd"><p>Climbing Check Settings</p></td><td class="confluenceTd"><p>Used to supply states that can be used to detect ledges when climbing. Ledges can be defined as the peaks of climbable surfaces.</p></td></tr><tr><td class="confluenceTd"><p>Climb Check Layer Mask</p></td><td class="confluenceTd"><p>LayerMask</p></td><td class="confluenceTd"><p>Climbing Check Settings</p></td><td class="confluenceTd"><p>Used to supply states that can be detected as climbable surfaces.</p></td></tr><tr><td class="confluenceTd"><p>Climb Check Distance</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Climbing Check Settings</p></td><td class="confluenceTd"><p>The distance from the player where climbable surfaces will be detected.</p></td></tr><tr><td class="confluenceTd"><p>Climb Check Origin Offset</p></td><td class="confluenceTd"><p>Vector3</p></td><td class="confluenceTd"><p>Climbing Check Settings</p></td><td class="confluenceTd"><p>The offset from the players origin that the climb check raycast originates from. This is used after the initial check has detected a climbable surface.</p></td></tr><tr><td class="confluenceTd"><p>Initial Climb Check Origin Offset</p></td><td class="confluenceTd"><p>Vector3</p></td><td class="confluenceTd"><p>Climbing Check Settings</p></td><td class="confluenceTd"><p>The offset from the players origin that the climb check raycast originates from. This is used for the initial check.</p></td></tr></tbody></table>

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 100.0px;"><col style="width: 198.0px;"><col style="width: 864.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Climbing Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Enable Interval Climb</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Interval Climb Variables</p></td><td class="confluenceTd"><p>When true, interval climb is enabled.</p></td></tr><tr><td class="confluenceTd"><p>Climbing Speed Interval Max</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Interval Climb Variables</p></td><td class="confluenceTd"><p>The maximum movement speed applied when climbing inside of the climb interval.</p></td></tr><tr><td class="confluenceTd"><p>Climbing Speed Interval Min</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Interval Climb Variables</p></td><td class="confluenceTd"><p>The maximum movement speed applied when climbing outside of the climb interval.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed Interval Max</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Interval Climb Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state while inside of the climb interval.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed Interval Min</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Interval Climb Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state while outside of the climb interval.</p></td></tr><tr><td class="confluenceTd"><p>Jump Height From Climb</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Jump Variables</p></td><td class="confluenceTd"><p>The jump height applied from this state.</p></td></tr><tr><td class="confluenceTd"><p>Jump Time From Climb</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Jump Variables</p></td><td class="confluenceTd"><p>The jump duration applied from this state.</p></td></tr><tr><td class="confluenceTd"><p>Climbing Jump Strength</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Jump Variables</p></td><td class="confluenceTd"><p>The strength applied to the jump.</p></td></tr><tr><td class="confluenceTd"><p>Can Jump From Climb</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Jump Variables</p></td><td class="confluenceTd"><p>Allow the player to jump from wall while climbing.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Auto Camera Follow</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Climbing Settings</p></td><td class="confluenceTd"><p>Allow the camera to automatically follow the player while climbing.</p></td></tr><tr><td class="confluenceTd"><p>Reset Current Speed</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Climbing Settings</p></td><td class="confluenceTd"><p>Reset the players current speed when entering a Climbing state.</p></td></tr><tr><td class="confluenceTd"><p>Apply Climbing Guard Rails</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Climbing Settings</p></td><td class="confluenceTd"><p>If true, climbing guard rails are applied.</p></td></tr><tr><td class="confluenceTd"><p>Climbing Guard Rails Width</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Climbing Settings</p></td><td class="confluenceTd"><p>The distance from the player origin to check if the sides of the climb is no longer detecting a scalable.</p></td></tr><tr><td class="confluenceTd"><p>Climb Tilt Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Climbing Settings</p></td><td class="confluenceTd"><p>The speed at which the player rotates depending on the contour of the climbable object.</p></td></tr><tr><td class="confluenceTd"><p>Allow Ledge Climb</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Ledge Climb Settings</p></td><td class="confluenceTd"><p>If true, the player will climb over ledges while in a climbing state. When false, the player jumps over the ledge.</p></td></tr><tr><td class="confluenceTd"><p>Ledge Check Distance</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Ledge Climb Settings</p></td><td class="confluenceTd"><p>The distance in front of the player that ledges will be checked for.</p></td></tr><tr><td class="confluenceTd"><p>Ledge Check Height</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Ledge Climb Settings</p></td><td class="confluenceTd"><p>The distance downward to look for a ledge. In other words, the length of the downward raycast that detects ledges.</p></td></tr></tbody></table>

General Usage
=============

This section covers some general usage topics for this state.

### Defining Climbable Surfaces

To define a climbable surface, the developer will need to supply the in-scene Game Object to the layer of their choice. This layer must then be added to the Climb Check Layer Mask parameter.

### Interval Climb

The interval climb feature is a togglable feature that allows the end user to align the movement speeds of the character to better follow the movements that the animation might represent. This feature requires the end user to supply animation events to the climbing animations that will tell the **Player Controller Plus** framework to adjust the movements of the player.

The animation events are titled simply as **AtFootOfClimb** and **NotAtFootOfClimb**. When the player should be move normally, place the event **AtFootOfClimb** and when the player should have movement altered, place the event **NotAtFootOfClimb**. This feature is not applied when the player is considered to be idle when climbing.

![image-20240330-042937.png](attachments/5963778/6455353.png?width=760)![image-20240330-183027.png](attachments/5963778/6455365.png?width=764)

Assuming the Enable Interval Climb parameter is true, when the **AtFootOfClimb** is triggered, the parameters Climbing Speed Interval Min and Smooth Speed Interval Min are used to determine player movement. When the **NotAtFootOfClimb** is triggered, the parameters Climbing Speed Interval Max and Smooth Speed Interval Max are used to determine player movement.

To use consistent movement disable the interval climb feature by setting the Enable Interval Climb parameter to false.

### Climb Jumping

Climb jumping allows for the player to jump from a climb while in a climbing state. To enable/disable this ability, toggle the Can Jump From Climb parameter.

### Ledge Climbing

Ledge climbing allows for the player to seemingly climb over a ledge when the apex of a climb has been reached and a ledge is detected. To enable the ledge climbing feature, set the Allow Ledge Climb parameter to true.

The ledge climbing animation will be used when this feature is enabled, using the Ledge Climbing animation node rather than the Ledge Jumping animation node.

![image-20240330-183603.png](attachments/5963778/6684677.png?width=534)

### Ledge Jumping

Ledge jumping allows for the player to hop over a ledge at the apex of a climb rather than climb over, a behavior typically seen in retro 3D platformers such as Banjo Kazooie. To enable the ledge jumping feature, set the Allow Ledge Climb parameter to false.

The ledge jumping animation will be used when this feature is enabled, using the Ledge Jumping animation node rather than the Ledge Climbing animation node.

### Climbing Guard Rails

Climbing guard rails are a feature that can be enabled by setting the Apply Climbing Guard Rails parameter to true, which will stop the player from climbing off of the sides of a climbable surface. This feature can be configured to set a distance on both sides of the player where guard rails will be applied to fit your specific climbing needs.

| 
#### Climbing Gallery

 |
| --- |
| ![](attachments/thumbnails/5963778/6160475) | ![](attachments/thumbnails/5963778/6127641) |
| 

 | 

 |