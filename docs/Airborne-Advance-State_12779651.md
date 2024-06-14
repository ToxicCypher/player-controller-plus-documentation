/\*<!\[CDATA\[\*/ div.rbtoc1718320070263 {padding: 0px;} div.rbtoc1718320070263 ul {list-style: none;margin-left: 0px;} div.rbtoc1718320070263 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [State Details](#AirborneAdvanceState-StateDetails)
    *   [State Overview](#AirborneAdvanceState-StateOverview)
    *   [Entry Requirements](#AirborneAdvanceState-EntryRequirements)
*   [Parameters](#AirborneAdvanceState-Parameters)
    *   [Base State Parameters](#AirborneAdvanceState-BaseStateParameters)
    *   [State Specific Parameters](#AirborneAdvanceState-StateSpecificParameters)
*   [General Usage](#AirborneAdvanceState-GeneralUsage)
    *   [Adjusting Airborne Advance Behavior](#AirborneAdvanceState-AdjustingAirborneAdvanceBehavior)
        *   [Airborne Advance Duration](#AirborneAdvanceState-AirborneAdvanceDuration)
        *   [Ramp Down Percentage](#AirborneAdvanceState-RampDownPercentage)
        *   [Ramp Down Smooth Speed](#AirborneAdvanceState-RampDownSmoothSpeed)

State Details
=============

State Overview
--------------

The Airborne Advance state can be interpreted in many ways. The general idea of the name “Airborne Advance” is to be as action agnostic as possible as this state has the potential to do any number of things regarding airborne dashing, flying, dodging in air, or just doing cool moves while suspended in mid-air for a time.

Entry Requirements
------------------

To enter an Airborne Advance state, the player must press the Airborne Advance input while in an Airborne state. The input that must be pressed can be configured in the Player Input System definition.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

This state does not contain any state specific base state parameters.

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 144.0px;"><col style="width: 311.0px;"><col style="width: 707.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Airborne Advance Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Adjust Speed On Exit</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Airborne Advance Settings</p></td><td class="confluenceTd"><p>When true, the players current speed will be manipulated when the current state is exited. This depends on Target Speed On Exit.</p></td></tr><tr><td class="confluenceTd"><p>Target Speed On Exit</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Airborne Advance Settings</p></td><td class="confluenceTd"><p>The players current speed that should be set as this state is exited. Adjust Speed On Exit must be true.</p></td></tr><tr><td class="confluenceTd"><p>Bypass Speed Adjustment On Exit States</p></td><td class="confluenceTd"><p>List&lt;PlayerState&gt;</p></td><td class="confluenceTd"><p>Airborne Advance Settings</p></td><td class="confluenceTd"><p>A list of PlayerState definitions. When a particular state is provided to this list, when exiting the current state, any configuration regarding speed adjustment will be ignored.</p></td></tr><tr><td class="confluenceTd"><p>Can Slide From Airborne Advance</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Airborne Advance Settings</p></td><td class="confluenceTd"><p>Flags the ability to enter a Sliding state directly from an Airborne Advance state.</p></td></tr><tr><td class="confluenceTd"><p>Airborne Advance Duration</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Airborne Advance Ramp Speed Settings</p></td><td class="confluenceTd"><p>The length of the state, in seconds.</p></td></tr><tr><td class="confluenceTd"><p>Ramp Down Percentage</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Airborne Advance Ramp Speed Settings</p></td><td class="confluenceTd"><p>The percentage at which the airborne advance speed should begin to ramp down where 0 is immediately and 1 is never.</p></td></tr><tr><td class="confluenceTd"><p>Ramp Down Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Airborne Advance Ramp Speed Settings</p></td><td class="confluenceTd"><p>The speed at which the airborne advance slows down.</p></td></tr><tr><td class="confluenceTd"><p>Perform Initial Airborne Advance Rotation</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Airborne Advance Initial Rotation Settings</p></td><td class="confluenceTd"><p>Snap the players direction to the target direction when the AirborneAdvance state is entered.</p></td></tr></tbody></table>

General Usage
=============

This section covers some general usage topics for this state.

Adjusting Airborne Advance Behavior
-----------------------------------

This Airborne Advance state can be configured to perform actions with the look and feel that fit your project needs by tweaking a few parameters under the Airborne Advance Ramp Speed Settings header.

### Airborne Advance Duration

This parameter is used to set the length of time that this state should be active. Allowing this state to live for a configurable length of time allows for the end-user to use animations that are not looped or looped providing a wider range of possibilities for this state.

### Ramp Down Percentage

This parameter tells the the AirborneAdvance state when to start slowing the movement of the player during this state, providing the option for the player to slowly come to a stop or simply stop abruptly before transitioning states.

### Ramp Down Smooth Speed

This parameter correlates with the Ramp Down Percentage parameter. When the ramp down takes place, this parameter is taken into account to determine how quickly the players movement should be slowed.