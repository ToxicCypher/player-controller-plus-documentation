*   [State Details](#SlidingState-StateDetails)
    *   [State Overview](#SlidingState-StateOverview)
    *   [Entry Requirements](#SlidingState-EntryRequirements)
*   [Parameters](#SlidingState-Parameters)
    *   [Base State Parameters](#SlidingState-BaseStateParameters)
    *   [State Specific Parameters](#SlidingState-StateSpecificParameters)
*   [General Usage](#SlidingState-GeneralUsage)
    *   [Slope Types](#SlidingState-SlopeTypes)
        *   [SlopeType.None](#SlidingState-SlopeType.None)
            *   [Characteristics](#SlidingState-Characteristics)
            *   [Behavior](#SlidingState-Behavior)
        *   [SlopeType.Minor](#SlidingState-SlopeType.Minor)
            *   [Characteristics](#SlidingState-Characteristics.1)
            *   [Behavior](#SlidingState-Behavior.1)
        *   [SlopeType.Moderate](#SlidingState-SlopeType.Moderate)
            *   [Characteristics](#SlidingState-Characteristics.2)
            *   [Behavior](#SlidingState-Behavior.2)
        *   [SlopeType.Major](#SlidingState-SlopeType.Major)
            *   [Characteristics](#SlidingState-Characteristics.3)
            *   [Behavior](#SlidingState-Behavior.3)
        *   [SlopeType.Exceeded](#SlidingState-SlopeType.Exceeded)
            *   [Characteristics](#SlidingState-Characteristics.4)
            *   [Behavior](#SlidingState-Behavior.4)

State Details
=============

State Overview
--------------

This state is used to slide down surfaces that are so configured to be slidable surfaces by setting slope detection settings that suit the needs for your project. Players will smoothly tilt on the surfaces that the player is sliding on and gain speed as the player continues to slide until the threshold is met.

Players can slide from one slide to another, arcing downward until the player either lands on an arbitrary surface or another slope. In the case of landing on another slope, the player will continue to slide whether the slope is Moderate Slope Type or greater.

Developers can define an allowance of directional control that the player will have over the character while sliding. This feature makes this state a perfect candidate for Snowboarding gameplay!

Entry Requirements
------------------

Slopes are continuously checked for at run-time when the transition is available. The checks consist of a series of Slope Type detection which is explained further in the General Usage > Slope Types section.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

This table defines configurable parameters that are related to this state but are shared between multiple states.

<table data-table-width="1382" data-layout="default" data-local-id="ba3f828a-f7ee-489c-87b3-cc7749cdfdcd" class="confluenceTable"><colgroup><col style="width: 219.0px;"><col style="width: 105.0px;"><col style="width: 198.0px;"><col style="width: 860.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Slope Check Layer Mask</p></td><td class="confluenceTd"><p>LayerMask</p></td><td class="confluenceTd"><p>Slope Check Settings</p></td><td class="confluenceTd"><p>Detect a slope belonging to the supplied layers.</p></td></tr><tr><td class="confluenceTd"><p>Maximum Slope</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Slope Check Settings</p></td><td class="confluenceTd"><p>The maximum angle that can be slid upon.</p></td></tr><tr><td class="confluenceTd"><p>Moderate Slope Limit</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Slope Check Settings</p></td><td class="confluenceTd"><p>The maximum angle a slope can be to be considered a moderate slope.</p></td></tr><tr><td class="confluenceTd"><p>Slope Check Distance</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Slope Check Settings</p></td><td class="confluenceTd"><p>The downward distance from the players origin that checks the slope the player may be standing on.</p></td></tr><tr><td class="confluenceTd"><p>Time Until Slope Slide</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Slope Check Settings</p></td><td class="confluenceTd"><p>The amount of time the player must wait before sliding from a Moderate slope. The wait time is tracked until the player has landed on a surface that is of a slope type that is less than the magnitude of a moderate slope.</p></td></tr><tr><td class="confluenceTd"><p>Slide Check Buffer</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Slope Check Settings</p></td><td class="confluenceTd"><p>The distance from the players negative forward that detects slopes. Calculated as: -transform.forward + (controller.radius * slideCheckBuffer). The buffer will be flipped depending on whether the player is sliding in a downward position or upward position.</p></td></tr></tbody></table>

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 226.0px;"><col style="width: 140.0px;"><col style="width: 255.0px;"><col style="width: 761.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Major Sliding Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement speed applied in this state while the current slope that is stood on, is considered a Major slope.</p></td></tr><tr><td class="confluenceTd"><p>Moderate Sliding Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement speed applied in this state while the current slope that is stood on, is considered a Moderate slope.</p></td></tr><tr><td class="confluenceTd"><p>Sliding Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state while currently sliding.</p></td></tr><tr><td class="confluenceTd"><p>Not Sliding Grounded Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state while the player is no longer considered to be sliding.</p></td></tr><tr><td class="confluenceTd"><p>Slope Velocity Orientation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The speed at which the player is rotated to face up/down slope.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Slide Control</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Sliding Settings</p></td><td class="confluenceTd"><p>The level of directional control that the player has over the character while sliding.</p></td></tr><tr><td class="confluenceTd"><p>Slope Slide Smoothing Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Sliding Settings</p></td><td class="confluenceTd"><p>The speed at which the slope slide velocity is interpolated.</p></td></tr><tr><td class="confluenceTd"><p>Maximum Sliding Downward Velocity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Sliding Settings</p></td><td class="confluenceTd"><p>The unique maximum gravity that can be reached while the player is sliding.</p></td></tr><tr><td class="confluenceTd"><p>Sliding Tilt Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Slide Position &amp; Rotation Settings</p></td><td class="confluenceTd"><p>The speed at which the player will tilt based on the current slope angle.</p></td></tr><tr><td class="confluenceTd"><p>Only Face Down Slope</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Slide Position &amp; Rotation Settings</p></td><td class="confluenceTd"><p>If true, the player will always face down the slope when sliding.</p></td></tr><tr><td class="confluenceTd"><p>Reset Gravity On Enter States</p></td><td class="confluenceTd"><p>List&lt;PlayerState&gt;</p></td><td class="confluenceTd"><p>State Settings</p></td><td class="confluenceTd"><p>If entering from a state in this list, zero out the gravity (set the movement vector.y to 0.0f).</p></td></tr><tr><td class="confluenceTd"><p>Reduce Gravity On Enter States</p></td><td class="confluenceTd"><p>List&lt;PlayerState&gt;</p></td><td class="confluenceTd"><p>State Settings</p></td><td class="confluenceTd"><p>If entering from a state in this list, reduce the gravity (set the movement vector.y to vector.y / 4.0f).</p></td></tr><tr><td class="confluenceTd"><p>Reset Speed On Enter States</p></td><td class="confluenceTd"><p>List&lt;PlayerState&gt;</p></td><td class="confluenceTd"><p>State Settings</p></td><td class="confluenceTd"><p>If entering to a state in this list, reduce the movement speed upon state exit.</p></td></tr></tbody></table>

General Usage
=============

This section covers some general usage topics for this state.

Slope Types
-----------

SlopeType is an enum type that is used to configure the behavior of a particular slope depending on the detected slopes angle. Depending on configuration provided by the end-user, different slope angles will align to the bounds of different slope types, resulting in different behavior.

Below is an explanation of each of the available slope types, how players can interact with them and configure them.

### SlopeType.None

#### Characteristics

The None Slope Type is defined as any surface that is not an angle or any surface that is not ground. For example, jumping from a slope into water will reset the moderate slope timer due to the type of slope being detected is SlopeType.None.

#### Behavior

This slope type behaves as a typical surface, not influencing any tilt on the player.

### SlopeType.Minor

#### Characteristics

Minor Slope Types are any slopes that between the configured Moderate Slope Type Limit and the None Slope Type limit.

#### Behavior

This slope type will cause the player to tilt towards the angle of the slope at a magnitude that is controlled by the Tilt Magnitude setting in the base states General Settings section.

### SlopeType.Moderate

Developers should exercise caution when setting any of the available slope limit parameters, as overlapping slope limit values may lead to undesirable behavior.

#### Characteristics

Moderate Slope Types are any slopes that fall between the Moderate Slope Type Limit and the Character Controller components Slope Limit parameter.

#### Behavior

This slope type will cause the player to tilt towards the angle of the slope at a magnitude that is controlled by the Tilt Magnitude setting in the base states General Settings section.

This slope type will also cause the layer to begin sliding down a slope. The amount of time at which a player will need to stand on a Moderate Slope Type depends on the Time Until Slope Slide parameter, which can be set to 0 which causes an immediate slope slide, forcing moderate slopes to behave similarly to the Major Slope Type.

Within various grounded states including Idle, Walking, Running, Grounded Advance and others, a Moderate Slope Type will cause directional speed damping, ultimately bringing the player to a slow pace or halting movement entirely depending on the parameters configured in said grounded states.

### SlopeType.Major

#### Characteristics

Major Slope Types are any slopes that exceed the Character Controller components Slope Limit parameter and the Maximum Slope parameter.

#### Behavior

This slope type will cause the player to immediately enter a sliding state.

### SlopeType.Exceeded

#### Characteristics

Exceeded Slope Types are and slopes that exceed the Maximum Slope parameter.

#### Behavior

Exceeded Slope Types will not send the player into a sliding state, instead this slope type is solely used to force players off of very steep angles as to stop the player from standing on walls that are not desired.