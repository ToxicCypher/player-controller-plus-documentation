
*   [State Details](#RunningState-StateDetails)
    *   [State Overview](#RunningState-StateOverview)
    *   [Entry Requirements](#RunningState-EntryRequirements)
*   [Parameters](#RunningState-Parameters)
    *   [Base State Parameters](#RunningState-BaseStateParameters)
    *   [State Specific Parameters](#RunningState-StateSpecificParameters)
*   [General Usage](#RunningState-GeneralUsage)
    *   [Grounded Advancing Entry](#RunningState-GroundedAdvancingEntry)
    *   [Skidding Entry](#RunningState-SkiddingEntry)

State Details
=============

State Overview
--------------

This state is a general grounded state, supplying faster movement speed over the Walking state. This state is a particularly unique grounded state as this state is the only state that can transition to a Grounded Advance state as well as a Skidding state if so configured.

Entry Requirements
------------------

This state can be entered only when grounded and when the players input is within the input thresholds required to enter the running state, provided in the Player Input System.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

This state does not contain any state specific base state parameters.

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 100.0px;"><col style="width: 198.0px;"><col style="width: 864.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Run Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Directional Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The speed at which the players direction is smoothed.</p></td></tr><tr><td class="confluenceTd"><p>Jump Height From Running</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Jump Variables</p></td><td class="confluenceTd"><p>The jump height applied from this state.</p></td></tr><tr><td class="confluenceTd"><p>Jump Time From Running</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Jump Variables</p></td><td class="confluenceTd"><p>The jump duration applied from this state.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Grounded Advance Threshold</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Running Settings</p></td><td class="confluenceTd"><p>The speed at which the player must be moving for grounded advance to activate.</p></td></tr><tr><td class="confluenceTd"><p>Moderate Slope Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Running Settings</p></td><td class="confluenceTd"><p>The speed at which movement speed will be slowed while traveling up a moderate slope.</p></td></tr><tr><td class="confluenceTd"><p>Skidding Directional Distance Threshold</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Running Settings</p></td><td class="confluenceTd"><p>The minimum distance between the target and current direction needed to enter a Skidding state.</p></td></tr><tr><td class="confluenceTd"><p>Skidding Speed Threshold</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Running Settings</p></td><td class="confluenceTd"><p>The minimum speed needed to enter a Skidding state.</p></td></tr></tbody></table>

General Usage
=============

This section covers some general usage topics for this state.

Grounded Advancing Entry
------------------------

The Grounded Advance state can only be entered from a Running state. To enter a the Grounded Advance state the player must provide Grounded Advance input to trigger the state, only when the players current speed meets or exceeds the Grounded Advance Threshold parameter.

Grounded Advance state transitions can be disabled by setting the Allow Grounded Advance parameter to false in the base state under the General Settings header.

Skidding Entry
--------------

The Skidding state can only be entered from a Running state. To enter a the Skidding state the players current speed must meets or exceed the Skidding Speed Threshold parameter, additionally, the player input while running must radically shift into a different direction, meeting or exceeding the Skidding Directional Distance Threshold parameter.

Skidding state transitions can be disabled by setting the Allow Skidding parameter to false in the base state under the General Settings header.