*   [State Details](#LedgeClimbingState-StateDetails)
    *   [State Overview](#LedgeClimbingState-StateOverview)
    *   [Entry Requirements](#LedgeClimbingState-EntryRequirements)
*   [Parameters](#LedgeClimbingState-Parameters)
    *   [Base State Parameters](#LedgeClimbingState-BaseStateParameters)
    *   [State Specific Parameters](#LedgeClimbingState-StateSpecificParameters)

State Details
=============

State Overview
--------------

The LedgeClimbing state is one of the two available states that can be entered when reaching the apex of a climb while in a Climbing state. This state is a more complex version of the ledge scaling states, allowing players to seemingly climb over the apex of a climbable surface, providing the illusion that player has scaled over the ledge.

This state will require parameter tweaking as well as careful animation design in-order to get the look and feel of this state just right for your project.

Entry Requirements
------------------

To enter the LedgeClimbing state, that player must currently be in a Climbing state while detecting the apex of a climb.

To specify whether or not the player enters a LedgeClimbing state rather than a LedgeJumping state, the Allow Ledge Climb parameter in the Climbing state settings must be set to true.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

These state does not contain any state specific base state parameters.

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 100.0px;"><col style="width: 198.0px;"><col style="width: 864.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Ledge Climb Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The speed at which the ledge climb is executed.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr></tbody></table>