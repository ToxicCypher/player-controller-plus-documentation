
*   [State Details](#FallingToSplatState-StateDetails)
    *   [State Overview](#FallingToSplatState-StateOverview)
    *   [Entry Requirements](#FallingToSplatState-EntryRequirements)
*   [Parameters](#FallingToSplatState-Parameters)
    *   [Base State Parameters](#FallingToSplatState-BaseStateParameters)
    *   [State Specific Parameters](#FallingToSplatState-StateSpecificParameters)

State Details
=============

State Overview
--------------

This state is nearly identical to the Falling state, the only difference is that when the player becomes grounded, the player enters a Splatting state rather than just simply becoming grounded or entering a soft/hard landing state.

Breaking this FallingToSplat state out into its own state also provides an avenue for supplying a unique animation for this state as well as configurable locomotion parameters that may differ from the Falling state.

Entry Requirements
------------------

This state can be entered only when the player has been in a Falling state for a configured period of time without becoming grounded.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

This state does not contain any state specific base state parameters.

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 100.0px;"><col style="width: 198.0px;"><col style="width: 864.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Falling To Splat Movement Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Movement Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Falling To Splat Settings</p></td><td class="confluenceTd"><p>The speed at which the player should be able to redirect the character while in mid-air.</p></td></tr></tbody></table>