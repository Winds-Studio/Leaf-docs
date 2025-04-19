# Leaf global config

!!! info "Info"

    The YAML config below shows the structure and default config values of Leaf's global config (==config/leaf-global.yml==)

    The config bases on the latest 1.21.1 branch of Leaf

    Click arrow button behind the config node to show description of it

```yaml title="leaf-global.yml"
# Leaf Global Config
config-version: 3.0

###########
#  ASYNC  #
###########
async: #(1)!
  async-entity-tracker: #(2)!
    enabled: false
    compat-mode: false #(3)!
    max-threads: 0 #(4)!
    keepalive: 60 #(5)!
  # **Experimental feature, may cause data lost in some circumstances!**
  async-playerdata-save: #(6)!
    enabled: false
  async-pathfinding: #(7)!
    enabled: false
    max-threads: 0 #(8)!
    keepalive: 60 #(9)!
  async-mob-spawning: #(10)!
    enabled: true
  async-locator: #(11)!
    enabled: false
    threads: 0 #(12)!
    keepalive: 60 #(13)!

##########
#  PERF  #
##########
performance: #(14)!
  use-virtual-thread-for-async-chat-executor: true #(15)!
  use-virtual-thread-for-async-scheduler: true #(16)!
  create-snapshot-on-retrieving-blockstate: true #(17)!
  inactive-goal-selector-throttle: true #(18)!
  throttle-hopper-when-full: #(19)!
    enabled: false
    skip-ticks: 0 #(20)!
  skip-map-item-data-updates-if-map-does-not-have-craftmaprenderer: true #(21)!
  skip-ai-for-non-aware-mob: true #(22)!
  reduce-packets: #(23)!
    reduce-entity-move-packets: false #(24)!
  optimized-powered-rails: true #(25)!
  optimize-minecart: #(26)!
    enabled: false
    skip-tick-count: 30 #(27)!
  # This may cause the inconsistent order of future compose tasks.
  faster-structure-gen-future-sequencing: true #(28)!
  # Requires a JVM that supports RandomGenerator.
  # Some JREs don't support this.
  faster-random-generator: #(29)!
    enabled: false
    random-generator: Xoroshiro128PlusPlus #(30)!
    enable-for-worldgen: false #(31)!
    warn-for-slime-chunk: true #(32)!
    use-legacy-random-for-slime-chunk: false #(33)!
  entity-timeouts: #(34)!
    ALLAY: -1
    AREA_EFFECT_CLOUD: -1
    ARMADILLO: -1
    ARMOR_STAND: -1
    ARROW: -1
    AXOLOTL: -1
    BAT: -1
    BEE: -1
    BLAZE: -1
    BOAT: -1
    BOGGED: -1
    BREEZE: -1
    BREEZE_WIND_CHARGE: -1
    CAMEL: -1
    CAT: -1
    CAVE_SPIDER: -1
    CHEST_BOAT: -1
    CHEST_MINECART: -1
    CHICKEN: -1
    COD: -1
    COMMAND_BLOCK_MINECART: -1
    COW: -1
    CREEPER: -1
    DOLPHIN: -1
    DONKEY: -1
    DRAGON_FIREBALL: -1
    DROWNED: -1
    EGG: -1
    ELDER_GUARDIAN: -1
    ENDER_DRAGON: -1
    ENDER_PEARL: -1
    ENDERMAN: -1
    ENDERMITE: -1
    EVOKER: -1
    EVOKER_FANGS: -1
    EXPERIENCE_BOTTLE: -1
    EXPERIENCE_ORB: -1
    EYE_OF_ENDER: -1
    FIREWORK_ROCKET: -1
    FOX: -1
    FROG: -1
    FURNACE_MINECART: -1
    GHAST: -1
    GIANT: -1
    GLOW_SQUID: -1
    GOAT: -1
    GUARDIAN: -1
    HOGLIN: -1
    HOPPER_MINECART: -1
    HORSE: -1
    HUSK: -1
    ILLUSIONER: -1
    IRON_GOLEM: -1
    ITEM: -1
    OMINOUS_ITEM_SPAWNER: -1
    FIREBALL: -1
    LIGHTNING_BOLT: -1
    LLAMA: -1
    LLAMA_SPIT: -1
    MAGMA_CUBE: -1
    MOOSHROOM: -1
    MULE: -1
    OCELOT: -1
    PANDA: -1
    PARROT: -1
    PHANTOM: -1
    PIG: -1
    PIGLIN: -1
    PIGLIN_BRUTE: -1
    PILLAGER: -1
    POLAR_BEAR: -1
    POTION: -1
    PUFFERFISH: -1
    RABBIT: -1
    RAVAGER: -1
    SALMON: -1
    SHEEP: -1
    SHULKER: -1
    SHULKER_BULLET: -1
    SILVERFISH: -1
    SKELETON: -1
    SKELETON_HORSE: -1
    SLIME: -1
    SMALL_FIREBALL: -1
    SNIFFER: -1
    SNOW_GOLEM: -1
    SNOWBALL: -1
    SPAWNER_MINECART: -1
    SPECTRAL_ARROW: -1
    SPIDER: -1
    SQUID: -1
    STRAY: -1
    STRIDER: -1
    TADPOLE: -1
    TNT_MINECART: -1
    TRADER_LLAMA: -1
    TRIDENT: -1
    TROPICAL_FISH: -1
    TURTLE: -1
    VEX: -1
    VILLAGER: -1
    VINDICATOR: -1
    WANDERING_TRADER: -1
    WARDEN: -1
    WIND_CHARGE: -1
    WITCH: -1
    WITHER: -1
    WITHER_SKELETON: -1
    WITHER_SKULL: -1
    WOLF: -1
    ZOGLIN: -1
    ZOMBIE: -1
    ZOMBIE_HORSE: -1
    ZOMBIE_VILLAGER: -1
    ZOMBIFIED_PIGLIN: -1
    FISHING_BOBBER: -1
  enable-cached-minecraft-to-bukkit-entitytype-convert: true #(35)!
  dab: #(36)!
    enabled: true
    dont-enable-if-in-water: false #(37)!
    start-distance: 12 #(38)! # Recommended: 8
    max-tick-freq: 20 #(39)!
    activation-dist-mod: 8 #(40)!
    blacklisted-entities: [] #(41)!
  dont-save-entity:
    dont-save-primed-tnt: false #(42)!
    dont-save-falling-block: false #(43)!

###########
#  FIXES  #
###########
fixes: #(44)!
  dont-place-player-if-server-full: false #(45)!

##############
#  GAMEPLAY  #
##############
gameplay-mechanisms: #(46)!
  use-spigot-item-merging-mechanism: true #(47)!
  # **Experimental feature, report any bugs you encounter!**
  smooth-teleport: false #(48)!
  # Don't touch this unless you know what you are doing!
  max-item-stack-count: #(49)!
    max-dropped-items-stack-count: 0 #(50)!
    max-container-destroy-count: 0 #(51)!
  knockback: #(52)!
    snowball-knockback-players: false #(53)!
    egg-knockback-players: false #(54)!
    can-player-knockback-zombie: true #(55)!
  player:
    disable-moved-wrongly-threshold: false #(56)!
    max-use-item-distance: 1.0000001 #(57)!

#############
#  NETWORK  #
#############
network: #(58)!
  protocol-support: #(59)!
    jade-protocol: false #(60)!
    appleskin-protocol: false #(61)!
    asteorbar-protocol: false #(62)!
    chatimage-protocol: false #(63)!
    xaero-map-protocol: false #(64)!
    xaero-map-server-id: 513317 #(65)!
    syncmatica-protocol: false #(66)!
    syncmatica-quota: false #(67)!
    syncmatica-quota-limit: 40000000 #(68)!
  chat-message-signature: true #(69)!

##########
#  MISC  #
##########
misc: #(70)!
  message:
    unknown-command: <red><lang:command.unknown.command><newline><detail> #(71)!
  rebrand:
    server-mod-name: Leaf #(72)!
    server-gui-name: Leaf Console #(73)!
  sentry: #(74)!
    # Obtain DSN key from https://sentry.io/
    dsn: '' #(75)!
    log-level: WARN #(76)!
    only-log-thrown: true #(77)!
  secure-seed: #(78)!
    enabled: false
  remove-vanilla-username-check: true #(79)!
  remove-spigot-check-bungee-config: true #(80)!
  remove-change-non-editable-sign-warning: false #(81)!
  region-format-settings: #(82)!
    region-format: MCA #(83)!
    linear-compress-level: 1 #(84)!
    throw-on-unknown-extension-detected: false #(85)!
    flush-interval-seconds: 5 #(86)!
  lag-compensation: #(87)!
    enabled: false
    enable-for-water: false #(88)!
    enable-for-lava: false #(89)!
  including-5s-in-get-tps: true #(90)!
  # NOTICE: You must know what you're filling in and how it works! It handles all item stacks!
  hidden-item-components: [] #(91)!
  connection-message: #(92)!
    join:
      enabled: true
      message: default #(93)!
    quit:
      enabled: true
      message: default #(94)!
  cache:
    cache-player-profile-result: true #(95)!
    cache-player-profile-result-timeout: 1440 #(96)!
```

1. This section contains asynchronous features intended to reduce the load on the main thread (Server Thread) by processing tasks asynchronously.
2. Make entity tracking asynchronously, can improve performance significantly, especially in some massive entities in small area situations.<br>
  <br>
  __Recommended value: `true` (set `enabled` below to true)__

    !!! note "Attention"

        If you installed plugins like Citizens, which uses real, and player type entity as "NPC", also read `async-entity-tracker.compat-mode` below for more infomration.

3. Enable compat mode to be compatible with plugins like Citizens or NPC plugins that use real, and player-type entity.<br>
  If `true`,  visibility issue that player-type NPCs may disappear sometimes can be fixed.<br>
  <br>
  You should enable `compat-mode` to use async entity tracker feature ==ONLY IF== you installed Citizens or any other kind of real entity NPC plugins.<br>
  <br>
  But we still recommend to use packet-based / virtual entity NPC plugin to gain better performance, e.g. [ZNPC Plus](https://github.com/Pyrbu/ZNPCsPlus), [Adyeshach](https://github.com/TabooLib/Adyeshach), [Fancy NPC](https://modrinth.com/plugin/fancynpcs), or else, and then `compat-mode` can be disabled.
4. Maximum number of threads for async entity tracker to use.<br>
   If the value is set to `0`, it automatically uses 1/4 of the number of CPU cores and no less than 1.<br>
  <br>
  __Recommended value: 1/2 of CPU cores__
5. Thread keepalive time, threads with no tasks will be terminated if they exceed the time.<br>
  (Unit: seconds)
6. Make PlayerData saving asynchronously.

    !!! warning "Warning"

        Experimental feature, may cause data lost in some circumstances!

7. Make mob pathfinding calculation asynchronously.<br>
  <br>
  __Recommended value: `true` (set `enabled` below to true)__
8. Maximum number of threads for async entity pathfinding to use.<br>
   If the value is set to `0`, it automatically uses 1/4 of the number of CPU cores and no less than 1.<br>
  <br>
  __Recommended value: 1/3 of CPU cores__
9. Thread keepalive time, threads with no tasks will be terminated if they exceed the time.<br>
  (Unit: seconds)
10. Whether asynchronous mob spawning should be enabled.<br>
  On servers with many entities, this can improve performance by up to 15%. You must have Paper's `per-player-mob-spawns` config set to `true` for this to work.<br>
  One quick note: this does not actually spawn mobs async (that would be very unsafe). This just offloads some expensive calculations that are required for mob spawning.<br>
  <br>
  __Recommended value: `true`__
11. Whether asynchronous locator should be enabled.<br>
  This offloads structure locating to other threads.<br>
  Currently available for:
    * `/locate` command
    * Dolphin treasure finding
    * Eye of ender stronghold finding
  <br><br>
  __Recommended value: `true` (set `enabled` below to true)__
12. Maximum number of threads for async locator to use.<br>
   If a value &leq; `0` is given, it automatically uses 1 thread.<br>
  <br>
  __Recommended value: `1` or `2`__
13. Thread keepalive time, threads with no tasks will be terminated if they exceed the time.<br>
  (Unit: seconds)



14. This section contains performance tuning intended to reduce unnecessary calculations or use more efficient methods to optimize the server.
15. Whether to use the [Virtual Thread](https://docs.oracle.com/en/java/javase/21/core/virtual-threads.html) introduced in JDK 21 for Async Chat Executor.<br>
  <br>
  __Recommended value: `true`__
16. Whether to use the [Virtual Thread](https://docs.oracle.com/en/java/javase/21/core/virtual-threads.html) introduced in JDK 21 for CraftAsyncScheduler, which could improve performance of plugin that uses async scheduler.<br>
  <br>
  __Recommended value: `true`__
17. Whether to create the snapshot of TileEntity / BlockState when retrieving them.<br>
  <br>
  Some plugins may use `getHolder` to get the holder for an inventory, which involved getting the BlockState.<br>
  For example, if there are tons of hoppers and plugins call this method when listening to some events (e.g. hopper related events). It is very expensive to re-create BlockState and parse item stack in massive and frequent calls.<br>
  See Paper's [API-to-get-a-BlockState-without-a-snapshot.patch#L6](https://github.com/PaperMC/Paper-archive/blob/b48403bd69f534ffd43fe2afb4e8e1f1ffa95fe1/patches/server/0160-API-to-get-a-BlockState-without-a-snapshot.patch#L6) for more information.
    * If `true`, it will create snapshot (copy) of BlockState everytime when the plugin call related methods.
    * If `false`, it will get real BlockState itself when plugins call related methods, unless the plugin defines to use snapshot.
  <br><br>
  __Recommended value: `false` (Only if you encounter specific lag described above)__
18. Throttles the *AI goal selector* calculation in entity's *inactive tick* to every second. This can improve performance by a few percent, but has minor gameplay implications.<br>
  <br>
  __Recommended value: `true`__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

19. Whether to throttle attempts on moving items for hopper if the target container is full.<br>
  <br>
  __Recommended value: `true` (set `enabled` below to true)__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

20. How many ticks to wait before the next move item attempt when the hopper is throttled.<br>
  If a value &leq; `0` is given, this throttling feature is disabled.<br>
  <br>
  __Recommended value: `8`__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>8</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>0</code></td></tr>
    </table>

21. Whether to skip map item data update if the map doesn't have a renderer.<br>
  This can improve performance if using image map kind of plugins.<br>
  <br>
  __Recommended value: `true`__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

    !!! note "Attention"

        This may cause vanilla map item data to stop be updated.

22. Whether to skip AI ticks if the mob is *inactive* and *unaware*. Unaware mobs are nerd and will not make actions themselves or when interacted with them.<br>
  <br>
  __Recommended value: `true`__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

23. This section is for the useless packet reducing features.
24. Whether to reduce the useless entity movement packets sent to players.<br>
  <br>
  __Recommended value: `true`__
25. Whether to use optimized powered rails. Uses fully rewritten version of powered rail iteration logic, can achieve 4x faster performance.<br>
  <br>
  __Recommended value: `true`__
26. Whether to optimize minecart ticking. By skipping tick collisions to reduce expensive `getEntities()` calls and bukkit event calls.<br>
  This can handle a large amount of stacked minecarts better which is useful for [Anarchy servers](https://minecraftservers.org/type/anarchy).<br>
  <br>
  __Recommended value: `true`__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

27. How many ticks to skip before checking for the next minecart collisions.<br>
  <br>
  __Recommended value: `30`__
28. Whether to use faster task sequencing for generating structures.

    !!! note "Attention"

        This may cause the inconsistent order of future compose tasks.

29. Whether to use the faster random generator.<br>
  Random is used almost everywhere in Minecraft, enable this can get a decent performance improvement.<br>
  <br>
  __Recommended value: `true` (set `enabled` below to true)__

    !!! note "Attention"

        Requires a JVM that supports `RandomGenerator`. Some JREs don't support this.

30. Which random generator will be used?<br>
  Available random generators can be found in [Random Number Generators in Java](https://www.baeldung.com/java-17-random-number-generators#1-api-design-1).<br>
  <br>
  __Recommended value: `Xoroshiro128PlusPlus`__
31. Whether to use the faster random generator for world generation.<br>
    * If `true`, `Random` calls involved in world generation will use faster random generator you chose in `random-generator` above. The world generation will be slightly different from vanilla.
    * If `false`, `Random` calls involved in world generation will use legacy random generator of vanilla.
  <br><br>
  __Recommended value: `true`__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

32. Whether server prints a warning message on startup if you are using faster random generator for slime chunk generation.
33. Whether to use legacy random source for slime chunk generation to follow the vanilla behavior.<br>
  If your server has existing slime farms or related facilities need slime chunk, enable this, otherwise the location of slime chunk will offset.<br>
  <br>
  __Recommended value:__ (Depends on your server type, see `Values for goals` below for more.)

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>false</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>true</code></td></tr>
    </table>

34. These values, in ticks, define an entity's maximum lifespan (i.e. Entity TTL).<br>
  If an entity is in this list, and it has survived for longer than that number of ticks, then it will be removed. 🛈<br>
  If a value `-1` is given, the Entity TTL check will disable for specific entity.<br>
  <br>
  __Recommended values:__

    | Entity             | Value |
    |--------------------|-------|
    | SNOWBALL           | 200   |
    | LLAMA_SPIT         | 150   |
    | DRAGON_FIREBALL    | 150   |
    | EGG                | 300   |
    | FIREBALL           | 600   |
    | SMALL_FIREBALL     | 400   |
    | WIND_CHARGE        | 200   |
    | BREEZE_WIND_CHARGE | 200   |
    | WITHER_SKULL       | 200   |

    > 🛈 = In here, the time that the entity survived means the total living time of entity, and will not be reset by chunk unloading or loading.

35. Whether to cache the result of *Minecraft EntityType* to *Bukkit EntityType* conversion. It can get a tiny improvement.<br>
  <br>
  __Recommended value: `true`__
36. Dynamic Activation of Brain, optimizes entity's brain to decrease the frequency of their brain ticking when they are far away from players.<br>
  <br>
  __Recommended value: `true` (set `enabled` below to true)__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code> (or see <code>dab.blacklisted-entities</code> below for more)</td></tr>
    </table>

37. Whether non-aquatic entities in the water will not be affected by DAB.<br>
  If `true`, this could fix entities suffocate in the water if they are far from the player. This fixed [Pufferfish's issue#58](https://github.com/pufferfish-gg/Pufferfish/issues/58).<br>
  <br>
  __Recommended value: `true`__
38. This value determines how far away an entity has to be from the player to start being affected by DAB.<br>
  <br>
  __Recommended value: `8`__
39. This value defines how often in ticks, the furthest entity will get their pathfinders and behaviors ticked (Note: 20 ticks = 1s).
40. This value defines how much distance modifies an entity's tick frequency. `freq = (distanceToPlayer^2) / (2^value)`.
    * If you want entities further away to tick __less__ often, use `7`.
    * If you want entities further away to tick __more__ often, try `9`.
  <br><br>
  __Recommended value: `7`__
41. A list of entities that will not be affected by DAB.<br>
  <br>
  Some survival servers have mob farms which need mobs to have a target. This kind of "pathfinding" mob farm may break by DAB. This situation can be solved by adding specific mob of mob farm into this DAB blacklist.<br>
  If some specific mob farms are broken in your server, mobs freeze and don't move, and you are not sure whether it is caused by DAB. You can try to add them into this blacklist to see if it fixes the issue.<br>
  <br>
  Format: `[VILLAGER]` or `[VILLAGER, ZOMBIFIED_PIGLIN]` (You can find all entity types in [Paper's Javadoc](https://jd.papermc.io/paper/1.21.1/org/bukkit/entity/EntityType.html)).

    ??? note "Want to Go Deeper?"

        For the format of `dab.blacklisted-entities`, it accepts all valid format of a YAML list.<br>
        <br>
        If you only need to add one entity into blacklist, these formats below are allowed:
        ```yaml
        dab:
          blacklisted-entities: [VILLAGER]
        ```
        or
        ```yaml
        dab:
          blacklisted-entities:
            - VILLAGER
        ```
        And if you need to add multiple entities into blacklist, these formats below are allowed:
        ```yaml
        dab:
          blacklisted-entities: [VILLAGER, ZOMBIFIED_PIGLIN]
        ```
        or
        ```yaml
        dab:
          blacklisted-entities:
            - VILLAGER
            - ZOMBIFIED_PIGLIN
        ```
        If you are not sure, use [YAML Checker](https://yamlchecker.org/), or any online YAML syntax validator to check your config.

42. Disable save primed tnt on chunk unloads.<br>
  It can prevent machines from being exploded by TNT when the player accidentally disconnected or chunk unloads when the player is far away. Useful for survival servers which have machines involved TNT.<br>
  <br>
  __Recommended value: `true`__
43. Disable save falling block on chunk unloads.<br>
  <br>
  __Recommended value: `true`__



44. This section contains bugfixes for specific issues.
45. Whether to disallow player join a server if the server is full.<br>
  If `true`, you should give player `purpur.joinfullserver` permission instead of using `PlayerLoginEvent#allow` to enable player to join a full server.



46. This section contains the features that modify the game mechanics.
47. Whether to use Spigot's dropped item merging mechanism.
48. Whether to make a "smooth teleport" when players change dimension.<br>
  This requires original world and target world that have the same logical height to work.

    !!! warning "Warning"

        Experimental feature, report any bugs you encounter!

49. Configurable max stack size of dropped item.

    !!! warning "Warning"

        We __do not__ recommended to use this feature. It is working in progress and has known issues.<br>
        This feature also maybe remove in the future. __Do not__ touch this unless you know what you are doing!

50. Maximum number of dropped items to stack.
51. Maximum count of items to drop when container is destroyed.
52. This section contains options to adjust knockback related behaviors.
53. Whether the snowball can knockback players.
54. Whether the egg can knockback players.
55. Whether the player can knockback zombies.
56. Whether to disable the Spigot built-in moved too quickly / wrongly checks for players and vehicles.<br>
  If `true`, players can move or use vehicles to move with abnormal speed.<br>
  <br>
  __Recommended value: `true`__
57. The max distance that the player is allowed to interact with an item.<br>
  <br>
  Some [Anarchy servers](https://minecraftservers.org/type/anarchy) or similar type of servers may allow players to use hacks / cheats. If you want players able to use crystal related modules that are packet-based (e.g. CEV Breaker, BedAura), you may need to adjust this value.<br>
  It's better to set value to `10.0000001`, to allow using related hack modules.
  <br>
  If a value `-1` is given, the check of max allowed distance to use an item will be disabled.<br>
  <br>
  __Recommended value: `10.0000001` (For anarchy server)__

    !!! note "Attention"

        If set to `-1`, players are able to use some packet modules of hack clients, and also [Nocom Exploit](https://github.com/nerdsinspace/nocom-explanation)!



58. This section contains features for server networking related.
59. This section contains features that provide extra protocol support for some QoL / Utility mods.<br>
  <br>
  The extra protocol support is only functional if there is corresponding client-side mod installed. It means if a specific protocol support is enabled, and a player installed that mod on client, they can get the additional features described in each config below. But for players who have no corresponding mod installed, then everything is the same as before.

    !!! note "Attention"

        The protocol support may cause incompatibility with the [ViaVersion](https://modrinth.com/plugin/viaversion).<br>
        We recommend players to use client that has same version with the server core and install latest corresponding mod, otherwise they may unable to join the server.

60. Whether to enable [Jade](https://modrinth.com/mod/jade) protocol support.<br>
  If `true`, player who has Jade mod installed, can display item information inside the storage container, progress of furnace, brewing stand, foods on the campfire, bee data in beehive, and more vanilla-friendly features.
61. Whether to enable [AppleSkin](https://modrinth.com/mod/appleskin) protocol support.<br>
  If `true`, player who has AppleSkin mod installed, can display the accurate saturation / exhaustion values on the client.
62. Whether to enable [AsteorBar](https://modrinth.com/mod/asteorbar) protocol support.<br>
  If `true`, player who has AsteorBar mod installed, can display the accurate saturation / exhaustion values on the client.
63. Whether to enable [ChatImage](https://modrinth.com/mod/chatimage) protocol support.<br>
  If `true`, player who has ChatImage mod installed, can see the image sent by others using CICode format.
64. Whether to enable [XaeroMap](https://modrinth.com/mod/xaeros-minimap) protocol support.<br>
  If `true`, player who has Xaero's MiniMap mod or Xaero's WorldMap mod installed, can store players' coordinate points and death points based on server's `protocol-support.xaero-map-server-id` below, to prevent points from been deleted / refreshed if server name or IP address changed.
65. Numeric id for XaeroMap to identify the server. This will generate randomly on first start.
66. Whether to enable [Syncmatica](https://modrinth.com/mod/syncmatica) protocol support.<br>
  If `true`, player who has Syncmatica mod installed, can upload their [Litematica](https://modrinth.com/mod/litematica) schematics files or download shared schematics files from the server. Every player with Syncmatica mod installed can access shared schematics uploaded by others.
67. Whether to enable maximum file size limit for each shared schematics file of Litematica mod.
68. Maximum file size, in bytes, for each shared schematics file uploading to server. (40,000,000 bytes ≈ 38 MB)
69. Whether to enable chat message signature which introduced since Minecraft 1.19.1.<br>
  If `false`, players' chat messages become unable to report, and the insecure warning popup when player joined the server will be disabled.<br>
  <br>
  __Recommended value: `false`__



70. This section contains some miscellaneous features.
71. Unknown command message, will send to player if they execute an unknown command.<br>
  The message needs to use [MiniMessage](https://docs.advntr.dev/minimessage/format) format.<br>
  If set message to `default` or leave the default value, the vanilla unknown command message will be used.<br>
  <br>
  Available placeholders:
    * __`<detail>`__ - the detailed information of the unknown command.

    !!! note "API / Plugin Friendly"

        This feature is API / plugin friendly.
        It means that this message can be overrided by plugins using `UnknownCommandEvent#message` or `UnknownCommandEvent#setMessage`.

72. Server brand name that shows in F3 menu and server MOTD.
73. Server GUI window name, if you launched server without adding `--nogui` option in the startup flag.
74. [Sentry](https://sentry.io/welcome/) is an application monitor service for improved error logging, tracing. Helping the server dev team to maintain better.<br>
  <br>
  After enabled Sentry integration for your server, you don't need to audit long logs to find errors manually. Sentry can collect errors happened in your server, enable you to track errors on Sentry's web panel and help you to locate and fix them easier and faster.<br>
  <br>
  See __[How to Setup Sentry](../../how-to/setup-sentry.md)__ to know how to set up and get the DSN key for `sentry.dsn` below.<br>
75. The DSN key of your Sentry.<br>
  If an empty value `''` is given, the Sentry will be disabled.
76. Logs with a level higher than or equal to this level will be recorded.
77. Only to log with a Throwable will be recorded after enabling this. 
78. Whether to use secure seed.<br>
  All ores and structures are generated with 1024-bit seed instead of using 64-bit seed in vanilla, made seed cracker become impossible.<br>
  If used in the existing world, then the secure seed will only apply to new generating chunks.<br>
  <br>
  __Recommended value: `true` (set `enabled` below to true)__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td>-</td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

79. Whether to remove vanilla's username check to allow __all characters__ as username, including Chinese, etc. (It's only useful for offline servers).<br>
  If `true`, players are allowed to use non-English name to join the server.
80. Whether player can enter backend server via proxy, without the backend server to enable bungeecord mode in `spigot.yml`.
81. Whether the server prints warning when players tried to edit the sign that they are not allowed to edit.<br>
  Enable this to prevent console spam in some cases.<br>
  <br>
  __Recommended value: `true`__

82. Linear is a region file format that uses [ZSTD compression](https://facebook.github.io/zstd/) instead of ZLIB in vanilla Minecraft. This format saves about ~50% of disk space.<br>
  To use Linear region format, make sure you __Read [Linear Documentation](https://github.com/xymb-endcrystalme/LinearRegionFileFormatTools)__, and have done all steps required, then change `region-format-settings.region-format` below to `LINEAR`.

    !!! warning "Warning"

        Experimental feature, there is potential risk to lose chunk data. Backup your server before switching to Linear.<br>
        Also, we do not recommend using Linear, since vanilla's ANVIL format (.mca) is enough. Leaf uses the refactored version of the Linear flush system, which is safer but slower to save chunks to make data lost less possible. However this change is worth it, data is invaluable.

83. Available region formats: `"MCA"`, `"LINEAR"`.
84. The compression level for Linear region format file.
85. Whether to throw error to crash the server when unknown region format extension is detected.
86. The flush interval in seconds for Linear region format file data.
87. Lag compensation, which could ensure the basic game experience for players when server is lagging or low TPS situation.<br>
  <br>
  __Recommended value: `true` (set `enabled` below to true)__
88. Whether to enable lag compensation for water flowing.<br>
  <br>
  __Recommended value: `true`__
89. Whether to enable lag compensation for lava flowing.<br>
  <br>
  __Recommended value: `true`__
90. Whether to include 5-second TPS in the result of API `Bukkit#getTPS` and `Server#getTPS`.<br>
    * If `true`, you can use `getTPS` method to get a TPS long array with 4 elements (`5s, 1m, 5m, 15m`).
    * If `false`, you can use `getTPS` method to get a TPS long array with 3 elements (`1m, 5m, 15m`).

    ??? note "Want to Go Deeper?"

        If you are using Gale API or Leaf API for your plugins. Or runinng on Leaf and use reflection to get TPS, you can use `Bukkit#getTPSIncluding5SecondAverage`, to get the TPS array including 5-seconds TPS (`5s, 1m, 5m, 15m`).<br>
        Also, you can use `Bukkit#get5SecondTPSAverage` to get the average value of 5-seconds TPS in `double`.

91. Controls whether specified component information is sent to clients. This may break resource packs and client mods that rely on this information. It needs a component type list, incorrect things will not work.<br>
  For example, you can fill it with `["custom_data"]` to hide components of *CUSTOM_DATA*. Also, it can avoid some frequent client animations.

    !!! note "Attention"

        You must know what you're filling in and how it works! It handles all item stacks!

92. Connection message, broadcasts to all online players, when they join or quit the server.<br>
  The message needs to use [MiniMessage](https://docs.advntr.dev/minimessage/format) format.<br>
  If set message to `default` or leave the default value, the vanilla join / quit message will be used.<br>
  <br>
  Available placeholders:
    * __`%player_name%`__ - player name.
    * __`%player_displayname%`__ - player display name.

    !!! note "API / Plugin Friendly"

        This feature is API / plugin friendly.
        It means that the connection message can be overrided by plugins using `PlayerJoinEvent` or `PlayerQuitEvent`.

93. The join message of the player.
94. The quit message of the player.
95. Whether to cache the player profile result when they joined server.<br>
  It's useful if Mojang's authentication server is down.
96. The timeout of the player profile cache.<br>
  (Unit: minutes)<br>
  If the given timeout is exceeded, it will send another request to Mojang's authentication server to get profile data on player's next join.<br>
