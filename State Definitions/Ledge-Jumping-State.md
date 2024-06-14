*   [State Details](#LedgeJumpingState-StateDetails)
    *   [State Overview](#LedgeJumpingState-StateOverview)
    *   [Entry Requirements](#LedgeJumpingState-EntryRequirements)
*   [Parameters](#LedgeJumpingState-Parameters)
    *   [Base State Parameters](#LedgeJumpingState-BaseStateParameters)
    *   [State Specific Parameters](#LedgeJumpingState-StateSpecificParameters)

State Details
=============

State Overview
--------------

The LedgeJumping state is one of the two available states that can be entered when reaching the apex of a climb while in a Climbing state. This state is a more simplified version of the ledge scaling states, allowing players to essentially vault themselves over the ledge of a climb. The ledge vault can be characterized as a jump.

Entry Requirements
------------------

To enter the LedgeJumping state, that player must currently be in a Climbing state while detecting the apex of a climb.

To specify whether or not the player enters a LedgeJumping state rather than a LedgeClimbing state, the Allow Ledge Climb parameter in the Climbing state settings must be set to false.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

These state does not contain any state specific base state parameters.

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 100.0px;"><col style="width: 198.0px;"><col style="width: 864.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Ledge Jump Strength</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Ledge Variables</p></td><td class="confluenceTd"><p>The jump strength when jumping over a ledge.</p></td></tr><tr><td class="confluenceTd"><p>Ledge Jump Height</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Ledge Variables</p></td><td class="confluenceTd"><p>The jump height when jumping over a ledge.</p></td></tr><tr><td class="confluenceTd"><p>Ledge Jump Time</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Ledge Variables</p></td><td class="confluenceTd"><p>The jump duration when jumping over a ledge.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr></tbody></table>