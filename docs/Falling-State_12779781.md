/\*<!\[CDATA\[\*/ div.rbtoc1718320072754 {padding: 0px;} div.rbtoc1718320072754 ul {list-style: none;margin-left: 0px;} div.rbtoc1718320072754 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [State Details](#FallingState-StateDetails)
    *   [State Overview](#FallingState-StateOverview)
    *   [Entry Requirements](#FallingState-EntryRequirements)
*   [Parameters](#FallingState-Parameters)
    *   [Base State Parameters](#FallingState-BaseStateParameters)
    *   [State Specific Parameters](#FallingState-StateSpecificParameters)
*   [General Usage](#FallingState-GeneralUsage)
    *   [Notable Transitions](#FallingState-NotableTransitions)
        *   [Soft Landing](#FallingState-SoftLanding)
            *   [Behavior](#FallingState-Behavior)
            *   [Transition Requirements](#FallingState-TransitionRequirements)
        *   [Hard Landing](#FallingState-HardLanding)
            *   [Behavior](#FallingState-Behavior.1)
            *   [Transition Requirements](#FallingState-TransitionRequirements.1)
        *   [Falling To Splat](#FallingState-FallingToSplat)
            *   [Behavior](#FallingState-Behavior.2)
            *   [Transition Requirements](#FallingState-TransitionRequirements.2)

State Details
=============

State Overview
--------------

This state is similar to an Airborne state, the key difference being that this state has a multitude of state transitions that are entirely dependent on the length of time that the player remains in this state. Some of the states include different forms of Landing, Splatting and simply just becoming grounded given the proper conditions and configuration.

Entry Requirements
------------------

To enter a Falling state, the player must be in an Airborne state until the player has reached the configured Maximum Downward Velocity value which is set in the base state parameters.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

This table defines configurable parameters that are related to this state but are shared between multiple states.

<table data-table-width="1382" data-layout="default" data-local-id="91bc1842-2562-4fbe-9df1-a0d91a60282b" class="confluenceTable"><colgroup><col style="width: 219.0px;"><col style="width: 202.0px;"><col style="width: 214.0px;"><col style="width: 747.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data / Component Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Maximum Downward Velocity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Constants</p></td><td class="confluenceTd"><p>The maximum downward force that can be applied to the player.</p></td></tr></tbody></table>

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 143.0px;"><col style="width: 169.0px;"><col style="width: 850.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Falling Movement Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Time Until Soft Landing</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Landing State Timers</p></td><td class="confluenceTd"><p>The duration the player must fall until the Soft Landing state is accessible.</p></td></tr><tr><td class="confluenceTd"><p>Time Until Hard Landing</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Landing State Timers</p></td><td class="confluenceTd"><p>The duration the player must fall until the Hard Landing state is accessible.</p></td></tr><tr><td class="confluenceTd"><p>Time Until Falling To Splat</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Landing State Timers</p></td><td class="confluenceTd"><p>The duration the player must fall until the Falling to Splat state is accessible.</p></td></tr><tr><td class="confluenceTd"><p>Can Climb From Falling</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Falling Settings</p></td><td class="confluenceTd"><p>Allow the player to enter a Climbing state when Falling.</p></td></tr><tr><td class="confluenceTd"><p>Movement Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Falling Settings</p></td><td class="confluenceTd"><p>The speed at which the player should be able to redirect the character while in mid-air.</p></td></tr><tr><td class="confluenceTd"><p>Adjust Speed On Exit</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Falling Settings</p></td><td class="confluenceTd"><p>When true, the players current speed will be manipulated when the current state is exited.</p></td></tr><tr><td class="confluenceTd"><p>Target Speed On Exit</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Falling Settings</p></td><td class="confluenceTd"><p>The players current speed that should be set as this state is exited.</p></td></tr><tr><td class="confluenceTd"><p>Bypass Speed Adjustment On Exit States</p></td><td class="confluenceTd"><p>List&lt;PlayerState&gt;</p></td><td class="confluenceTd"><p>Falling Settings</p></td><td class="confluenceTd"><p>If the state that is being entered from the Falling state is supplied to this list, movement momentum will remain untouched when exiting this state.</p></td></tr></tbody></table>

General Usage
=============

This section covers some general usage topics for this state.

Notable Transitions
-------------------

In this section, each notable state transition that is unique to the Falling state is explored.

### Soft Landing

#### Behavior

The player will transition into the SoftLanding state when becoming grounded, causing the player to be unable to move for a short time.

#### Transition Requirements

The amount of time the player has been in the Falling state must have surpassed the configured duration of the Time Until Soft Landing parameter.

### Hard Landing

#### Behavior

The player will transition into the HardLanding state when becoming grounded, causing the player to be unable to move for a short time.

#### Transition Requirements

The amount of time the player has been in the Falling state must have surpassed the configured duration of the Time Until Hard Landing parameter.

### Falling To Splat

#### Behavior

The player will transition into the FallingToSplat state where once grounded the player will transition into the Splatting state once grounded.

#### Transition Requirements

The amount of time the player has been in the Falling state must have surpassed the configured duration of the Time Until Falling To Splat parameter.