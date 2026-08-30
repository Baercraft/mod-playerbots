# Baercraft custom race support

This Playerbots build adds compatibility with `mod-worgoblin-high-elf` v5.9 custom races.

## Race mapping

- Race 13: High Elf - Alliance - Blood Elf-derived Playerbots fallback behavior.
- Race 14: Mag'har Orc - Horde - Orc-derived Playerbots fallback behavior.

## Covered Playerbots systems

- Random bot race/class creation through the existing `RaceMgr` / `PlayerInfo` validation.
- Correct Alliance/Horde classification.
- High Elf names use the Blood Elf name pool.
- Mag'har names use the Orc name pool.
- Ground mounts inherit the corresponding parent race.
- Revive/start-race fallback handling includes both custom races.
- Travel start nodes have explicit custom-race names.
- Playerbots chat race names include both custom races.
- Mag'har inherits Orc-specific emote behavior where Playerbots has race-specific handling.
- `playerbots_rpg_races` clones Blood Elf entries to High Elf and Orc entries to Mag'har.

The Baercraft race module/core patch remains responsible for `ChrRaces`, `CharSections`, valid race/class `PlayerInfo`, start data, race masks and custom racial spells. Playerbots will only create a race/class combination when `sObjectMgr->GetPlayerInfo(race, class)` exists.
