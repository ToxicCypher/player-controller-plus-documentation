*   [State Details](#GroundedAdvanceState-StateDetails)
    *   [State Overview](#GroundedAdvanceState-StateOverview)
    *   [Entry Requirements](#GroundedAdvanceState-EntryRequirements)
*   [Parameters](#GroundedAdvanceState-Parameters)
    *   [Base State Parameters](#GroundedAdvanceState-BaseStateParameters)
    *   [State Specific Parameters](#GroundedAdvanceState-StateSpecificParameters)
*   [General Usage](#GroundedAdvanceState-GeneralUsage)
    *   [Adjusting Grounded Advance Behavior](#GroundedAdvanceState-AdjustingGroundedAdvanceBehavior)
        *   [State Duration](#GroundedAdvanceState-StateDuration)
        *   [Ramp Down Percentage](#GroundedAdvanceState-RampDownPercentage)
        *   [Ramp Down Smooth Speed](#GroundedAdvanceState-RampDownSmoothSpeed)

State Details
=============

State Overview
--------------

The GroundedAdvance state can be interpreted in many ways. The general idea of the name “GroundedAdvance” is to be as action agnostic as possible as this state has the potential to do any number of things regarding rolling, dashing, dodging or just doing cool dance moves!

Entry Requirements
------------------

To enter an GroundedAdvance state, the player must press the GroundedAdvance input while in a Running state while the players current speed meets or exceeds the Grounded Advance Threshold value.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

This state does not contain any state specific base state parameters.

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 144.0px;"><col style="width: 311.0px;"><col style="width: 707.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Grounded Advance Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Arc Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>Speed at which the curve of the arc, when grounded advancing off of a ledge will occur. (0.0 indicates that no adjustments will be made to gravity.)</p></td></tr><tr><td class="confluenceTd"><p>Additive Arc Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>Additive gravity to be applied to the arc, each frame.</p></td></tr><tr><td class="confluenceTd"><p>Adjust Speed On Exit</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Grounded Advance Settings</p></td><td class="confluenceTd"><p>When true, the players current speed will be manipulated when the current state is exited. This depends on Target Speed On Exit.</p></td></tr><tr><td class="confluenceTd"><p>Target Speed On Exit</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Grounded Advance Settings</p></td><td class="confluenceTd"><p>The players current speed that should be set as this state is exited. Adjust Speed On Exit must be true.</p></td></tr><tr><td class="confluenceTd"><p>Bypass Speed Adjustment On Exit States</p></td><td class="confluenceTd"><p>List&lt;PlayerState&gt;</p></td><td class="confluenceTd"><p>Grounded Advance Settings</p></td><td class="confluenceTd"><p>A list of PlayerState definitions. When a particular state is provided to this list, when exiting the current state, any configuration regarding speed adjustment will be ignored.</p></td></tr><tr><td class="confluenceTd"><p>Can Slide From Grounded Advance</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Grounded Advance Settings</p></td><td class="confluenceTd"><p>Flags the ability to enter a Sliding state directly from an Grounded Advance state.</p></td></tr><tr><td class="confluenceTd"><p>Moderate Slope Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Grounded Advance Settings</p></td><td class="confluenceTd"><p>The speed at which movement speed will be slowed while traveling up a moderate slope.</p></td></tr><tr><td class="confluenceTd"><p>State Duration</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Grounded Advance Settings</p></td><td class="confluenceTd"><p>The length of time to stay in this state. (Typically the length of the given animation, taking into account the animation speed | clip length * animation speed)</p></td></tr><tr><td class="confluenceTd"><p>Ramp Down Percentage</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Grounded Advance Ramp Speed Settings</p></td><td class="confluenceTd"><p>The percentage at which the Grounded advance speed should begin to ramp down where 0 is immediately and 1 is never.</p></td></tr><tr><td class="confluenceTd"><p>Ramp Down Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Grounded Advance Ramp Speed Settings</p></td><td class="confluenceTd"><p>The speed at which the Grounded advance slows down.</p></td></tr><tr><td class="confluenceTd"><p>Perform Initial Grounded Advance Rotation</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Grounded Advance Initial Rotation Settings</p></td><td class="confluenceTd"><p>Snap the players direction to the target direction when the GroundedAdvance state is entered.</p></td></tr></tbody></table>

General Usage
=============

This section covers some general usage topics for this state.

Adjusting Grounded Advance Behavior
-----------------------------------

This Grounded Advance state can be configured to perform actions with the look and feel that fit your project needs by tweaking a few parameters under the Grounded Advance Ramp Speed Settings header.

### State Duration

This parameter is used to set the length of time that this state should be active. Allowing this state to live for a configurable length of time allows for the end-user to use animations that are not looped or looped providing a wider range of possibilities for this state.

### Ramp Down Percentage

This parameter tells the the GroundedAdvance state when to start slowing the movement of the player during this state, providing the option for the player to slowly come to a stop or simply stop abruptly before transitioning states.

### Ramp Down Smooth Speed

This parameter correlates with the Ramp Down Percentage parameter. When the ramp down takes place, this parameter is taken into account to determine how quickly the players movement should be slowed.