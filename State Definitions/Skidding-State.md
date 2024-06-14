
*   [State Details](#SkiddingState-StateDetails)
    *   [State Overview](#SkiddingState-StateOverview)
    *   [Entry Requirements](#SkiddingState-EntryRequirements)
*   [Parameters](#SkiddingState-Parameters)
    *   [Base State Parameters](#SkiddingState-BaseStateParameters)
    *   [State Specific Parameters](#SkiddingState-StateSpecificParameters)

State Details
=============

State Overview
--------------

This state is used to supply a buffer for players who are moving quickly and change directions abruptly. This behavior may not be desired and can be disabled by setting the Allow Skidding State parameter to false.

Entry Requirements
------------------

This state can be entered only from a Running state. To enter this state from a Running state, the players current speed must meet or exceed the Skidding Speed Threshold set in the Running state as well as the Skidding Directional Distance Threshold which looks for abrupt changes in directional movement.

Parameters
==========

All parameters listed below have detailed Tooltips in the Unity Editor.

### Base State Parameters

This state does not contain any state specific base state parameters.

### State Specific Parameters

This table defines configurable parameters that are utilized solely by this state.

<table data-table-width="1382" data-layout="default" data-local-id="42844ded-fd04-45a2-9151-655070fb6892" class="confluenceTable"><colgroup><col style="width: 220.0px;"><col style="width: 100.0px;"><col style="width: 198.0px;"><col style="width: 864.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Data Type</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The movement smoothing speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Directional Smooth Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Movement Variables</p></td><td class="confluenceTd"><p>The speed at which the players direction is smoothed.</p></td></tr><tr><td class="confluenceTd"><p>Rotation Speed</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Rotation Variables</p></td><td class="confluenceTd"><p>The rotation speed applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Gravity Multiplier</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Gravity Variables</p></td><td class="confluenceTd"><p>The gravity multiplier applied in this state.</p></td></tr><tr><td class="confluenceTd"><p>Skid Cooldown</p></td><td class="confluenceTd"><p>float</p></td><td class="confluenceTd"><p>Skidding Settings</p></td><td class="confluenceTd"><p>The wait time between skids. This variable is used as away to ensure that skid states do not constantly become triggered. If this is the behavior that is desired, configuring this parameter to 0 will achieve this.</p></td></tr></tbody></table>