# Beast Shinobi — Spirit Ascendant (revision 1)

Open index.html to play locally, or upload these files together to GitHub Pages. Keep index.html at the site root. The existing installable app files are included.

## Changes
- Animal attacks and specials gain a 65% damage multiplier, independent of existing upgrades. Basic attacks are 12% faster with 15% more reach. Heavy beasts move 16% faster.
- Every beast resists at least 15% damage; the existing heavy armor remains stronger. Transformation costs 8 energy before upgrades, specials cost 20% less, drain is reduced, and successful beast melee attacks restore more energy.
- Original sprite art is preserved. Beasts gain colored spirit outlines, orbiting sigils, auras, and moving energy ribbons.
- Golden grapple rings are removed from every stage. The chain remains an enemy-binding weapon. Former ring sections become defended courtyards with low and high routes, treasure and spirit pickups.
- First realm extended; later realms gain two additional exploration blocks, accessible upper caches and more shrines. Map capacity increased so larger stages fit.
- Ordinary enemies have 22% more health and 10% faster pursuit. Incoming combat damage is increased by 15% before difficulty and armor.
- Boss body contact hurts the player during recovery and binding too. Passive wolf spin and thunder dash contact no longer damage bosses. Deliberate attacks and offensive specials still work. Dash invulnerability remains intentional.
- HUD now labels health, jutsu and beast energy, separates boss health from resources, moves route progress out of the resource panel, and hides locked beast shortcut clutter.
- Save slots and upgrade/progression keys are preserved. Service worker cache version updated.

## Verification
Executed the real game JavaScript in a Node VM with a minimal DOM shim and native Canvas image rendering:
- Generated all six maps: 616, 795, 768, 808, 854 and 754 tiles; zero rings; all fit within map storage.
- Checked base damage for all forms and ran each special through simulation.
- Verified all six bosses damage an overlapping player, take no passive wolf contact damage, and can be defeated to unlock stage-clear transitions.
- Simulated each boss for 2,400 steps through all three phases with invulnerability enabled for the test player.
- Completed all 18 arena wave sequences using scripted enemy kills, confirming gates release.
- Checked movement/jump/attack simulation, death/respawn, save serialization/reload, and menu construction.
- Rendered desktop, landscape and portrait viewport calculations. Inspected native Canvas renders and corrected a narrow-width HUD overlap.

## Verification limits / known issues
Browser launch was blocked by this execution environment. This is not a full manual browser playthrough. Browser DOM layout, actual multitouch, controller hardware, sound playback, installation and offline service worker behavior were not tested. No physical phone testing was performed. The existing landscape-oriented presentation remains letterboxed in portrait. Game balance still benefits from human playtesting. The VM checks do not prove every platforming route is traversable in ordinary play.

## Hidden development tools
Tap the title subtitle (or PAUSED heading) five times, then enter 2057. Existing debug tools and original-save backup/restore are retained. Use a spare save slot for experiments; restore the debug backup before returning to a normal slot. No test saves are bundled.
