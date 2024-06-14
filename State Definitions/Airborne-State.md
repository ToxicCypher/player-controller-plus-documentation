*   [State Details](#AirborneState-StateDetails)
    *   [State Overview](#AirborneState-StateOverview)
    *   [Entry Requirements](#AirborneState-EntryRequirements)
*   [Parameters](#AirborneState-Parameters)
    *   [Base State Parameters](#AirborneState-BaseStateParameters)
    *   [State Specific Parameters](#AirborneState-StateSpecificParameters)
*   [General Usage](#AirborneState-GeneralUsage)
    *   [Deterministic State Transitions](#AirborneState-DeterministicStateTransitions)

State Details
=============

State Overview
--------------

The Airborne state is a transitional airborne state that is typically entered when the player has been in the air for a configurable period of time. This state is considered transitional as while this state is active, the length of time the player remains in this state can determine the next state. For example, if the player were to remain in the Airborne state for long enough, the player could enter a Falling state or the player could simply just become grounded.

Entry Requirements
------------------

To enter an Airborne state, the player must begin the airborne decline after a Jumping state or simply walk off of a ledge.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

This table defines configurable parameters that are related to this state but are shared between multiple states.

<table data-table-width="1382" data-layout="default" data-local-id="91bc1842-2562-4fbe-9df1-a0d91a60282b" class="confluenceTable"><colgroup><col style="width: 219.0px;"><col style="width: 202.0px;"><col style="width: 214.0px;"><col style="width: 747.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data / Component Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Maximum Downward Velocity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Constants</p></td><td class="confluenceTd"><p>The maximum downward force that can be applied to the player.</p></td></tr></tbody></table>

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 144.0px;"><col style="width: 200.0px;"><col style="width: 818.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Airborne Movement Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Movement Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Airborne Settings</p></td><td class="confluenceTd"><p>Movement smoothing speed while airborne.</p></td></tr><tr><td class="confluenceTd"><p>Adjust Speed On Exit</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Airborne Settings</p></td><td class="confluenceTd"><p>When true, the players current speed will be manipulated when the current state is exited.</p></td></tr><tr><td class="confluenceTd"><p>Target Speed On Exit</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Airborne Settings</p></td><td class="confluenceTd"><p>The players current speed that should be set as this state is exited.</p></td></tr><tr><td class="confluenceTd"><p>Bypass Speed Adjustment On Exit States</p></td><td class="confluenceTd"><p>List&lt;PlayerState&gt;</p></td><td class="confluenceTd"><p>Airborne Settings</p></td><td class="confluenceTd"><p>If the state that is being entered from the Airborne state is supplied to this list, movement momentum will remain untouched when exiting this state.</p></td></tr><tr><td class="confluenceTd"><p>Allow Double jump</p></td><td class="confluenceTd"><p>bool</p></td><td class="confluenceTd"><p>Secondary Jump Settings</p></td><td class="confluenceTd"><p>Allow the state manager to enter the following states: [SecondaryJump]</p></td></tr><tr><td class="confluenceTd"><p>Double Jump Threshold</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Secondary Jump Settings</p></td><td class="confluenceTd"><p>The required downward velocity in-order to enter the SecondaryJump state.</p></td></tr><tr><td class="confluenceTd"><p>Secondary Jump Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Secondary Jump Settings</p></td><td class="confluenceTd"><p>The jump speed applied from this state.</p></td></tr><tr><td class="confluenceTd"><p>Secondary Jump Height</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Secondary Jump Settings</p></td><td class="confluenceTd"><p>The jump height applied from this state.</p></td></tr><tr><td class="confluenceTd"><p>Secondary Jump Time</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Secondary Jump Settings</p></td><td class="confluenceTd"><p>The jump duration applied from this state.</p></td></tr><tr><td class="confluenceTd"><p>Allow Airborne Advance From Previous States</p></td><td class="confluenceTd"><p>List&lt;PlayerState&gt;</p></td><td class="confluenceTd"><p>Airborne Advance Settings</p></td><td class="confluenceTd"><p>Disables the ability to Airborne Advance from the previous states supplied to this list.</p></td></tr></tbody></table>

General Usage
=============

This section covers some general usage topics for this state.

### Deterministic State Transitions

This state is used as a conduit between a series of available states. Each available state is provided in the table below as well as its entry conditions.

<table data-table-width="760" data-layout="default" data-local-id="5fbb2fba-8a42-407d-bb0f-d9dba059f435" class="confluenceTable"><colgroup><col style="width: 190.0px;"><col style="width: 568.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>State</strong></p></th><th class="confluenceTh"><p><strong>Entry Condition</strong></p></th></tr><tr><td class="confluenceTd"><p>SecondaryJump</p></td><td class="confluenceTd"><p>If allowed, press jump input.</p></td></tr><tr><td class="confluenceTd"><p>Falling</p></td><td class="confluenceTd"><p>Fall long enough for the players downward velocity to reach the Maximum Downward Velocity value set in the base state configuration.</p></td></tr><tr><td class="confluenceTd"><p>Idle | Walking | Running</p></td><td class="confluenceTd"><p>Become grounded before the Falling state is triggered.</p></td></tr></tbody></table>