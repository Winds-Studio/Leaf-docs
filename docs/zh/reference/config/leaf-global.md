# Leaf 全局配置

!!! info "信息"

    以下 YAML 配置展示了 Leaf 全局配置 (==config/leaf-global.yml==) 的结构及其默认的值

    此配置文件基于最新的 Leaf 1.21.1 分支

    点击配置项后面的箭头按钮以显示其描述

```yaml title="leaf-global.yml"
# Leaf Global Config
config-version: 3.0

###########
#  异步   #
###########
async: #(1)!
  async-entity-tracker: #(2)!
    enabled: false
    compat-mode: false #(3)!
    max-threads: 0 #(4)!
    keepalive: 60 #(5)!
  # **实验性功能, 在某些情况下可能导致玩家数据丢失!**
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
#  性能  #
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
  # 此配置项可能导致结构生成任务的合并顺序不一致.
  faster-structure-gen-future-sequencing: true #(28)!
  # 需要使用支持 RandomGenerator 的 JVM 来运行服务器.
  # 一些 JRE 可能不支持此功能.
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
#  修复   #
###########
fixes: #(44)!
  dont-place-player-if-server-full: false #(45)!

##############
#  游戏机制   #
##############
gameplay-mechanisms: #(46)!
  use-spigot-item-merging-mechanism: true #(47)!
  # **实验性功能, 请及时反馈你遇到的问题!**
  smooth-teleport: false #(48)!
  # 请勿修改此配置, 除非你知道自己在做什么!
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
#   网络    #
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
#  杂项  #
##########
misc: #(70)!
  message:
    unknown-command: <red><lang:command.unknown.command><newline><detail> #(71)!
  rebrand:
    server-mod-name: Leaf #(72)!
    server-gui-name: Leaf Console #(73)!
  sentry: #(74)!
    # 在 https://sentry.io/ 上获取 DSN key
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
  # 注意: 你必须知道你填进去的是什么, 有什么用！此功能会处理所有的物品!
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

1. 本节包含异步相关的特性, 旨在通过异步执行任务来减少主线程 (Server Thread) 的负载.
2. 是否使用异步实体追踪, 可以显著提高性能, 特别是在小范围内拥有大量密集实体的场景中.<br>
  <br>
  __推荐值: `true` (将下方的 `enabled` 设为 true)__

    !!! note "注意"

        如果你安装了类似 Citizens, 使用真实实体或玩家类型的实体作为 "NPC" 的插件, 请参阅下文的 `async-entity-tracker.compat-mode` 以获取更多信息.

3. 是否开启兼容模式, 以兼容类似 Citizens 或其他使用真实实体或玩家类型的实体作为 "NPC" 的插件.<br>
  如果设为 `true`, 可以修复玩家类型的 NPC 有时消失的可见性问题.<br>
  <br>
  ==仅当== 安装了 Citizens 或其他任意类似的基于真实实体的 NPC 插件时, 才需开启 `compat-mode` 来使用异步实体追踪功能.<br>
  <br>
  我们仍然推荐使用基于发包 / 虚拟实体的 NPC 插件以获得更好的性能, 例如: [ZNPC Plus](https://github.com/Pyrbu/ZNPCsPlus), [Adyeshach](https://github.com/TabooLib/Adyeshach), [Fancy NPC](https://modrinth.com/plugin/fancynpcs), 等, 使用这类插件后可以禁用 `compat-mode`.
4. 异步实体追踪可使用的最大线程数.<br>
   如果设为 `0`, 默认使用 CPU 核心数 1/4 的线程数, 且不少于 1.<br>
  <br>
  __推荐值: CPU 核心数的 1/2__
5. 空闲线程的超时时间, 超过该时间并且无任务的线程将被销毁.<br>
  (以 秒 为单位)
6. 是否开启异步玩家数据保存 (I/O 操作都很耗时).

    !!! warning "警告"

        实验性功能, 在某些情况下可能导致玩家数据丢失!

7. 是否使用异步生物寻路.<br>
  <br>
  __推荐值: `true` (将下方的 `enabled` 设为 true)__
8. 异步生物寻路可使用的最大线程数.<br>
   如果设为 `0`, 默认使用 CPU 核心数 1/4 的线程数, 且不少于 1.<br>
  <br>
  __推荐值: CPU 核心数的 1/3__
9. 空闲线程的超时时间, 超过该时间并且无任务的线程将被销毁.<br>
  (以 秒 为单位)
10. 是否使用异步生物生成.<br>
  对于拥有大量实体的服务器, 开启此功能可以带来近 15% 的性能提升. 并且你必须将 Paper 的 `per-player-mob-spawns` 设为 `true`, 此功能才能生效.<br>
  需要注意的是: 此功能并不会将生物生成的所有逻辑完全异步 (这样做非常不安全). 它只是将生物生成的一些耗时计算分担到其他线程上.<br>
  <br>
  __推荐值: `true`__
11. 是否使用异步定位.<br>
  此功能将结构定位任务的负载分担到其他线程.<br>
  目前仅可用于:
    * `/locate` 命令
    * 海豚寻找附近的沉船, 海底废墟或埋葬的宝藏
    * 末影之眼定位要塞
  <br><br>
  __推荐值: `true` (将下方的 `enabled` 设为 true)__
12. 异步定位可使用的最大线程数.<br>
   如果设为 &leq; `0`, 默认使用 1 个线程.<br>
  <br>
  __推荐值: `1` 或 `2`__
13. 空闲线程的超时时间, 超过该时间并且无任务的线程将被销毁.<br>
  (以 秒 为单位)



14. 本节包含性能调优相关的配置, 旨在通过减少不必要地计算, 或采用更高效的逻辑 / 算法优化服务器.
15. 是否为异步聊天使用 JDK 21 引入的 [虚拟线程 (Virtual Thread)](https://javaguide.cn/java/concurrent/virtual-thread.html).<br>
  <br>
  __推荐值: `true`__
16. 是否为异步任务调度器使用 JDK 21 引入的 [虚拟线程 (Virtual Thread)](https://javaguide.cn/java/concurrent/virtual-thread.html), 这可以提高使用异步调度器的插件的性能.<br>
  <br>
  __推荐值: `true`__
17. 是否在获取 TileEntity / BlockState 时创建并使用其快照.<br>
  <br>
  一些插件可能会使用 `getHolder` 方法来获取物品栏的所有者, 这涉及获取 BlockState 的副本. 而创建 BlockState 的副本或解析物品数据相当耗时, 其中涉及 NBT 的解析.<br>
  例如, 在拥有大量密集漏斗的场景中, 如果插件在监听某些事件 (例如与漏斗相关的事件) 时调用此类方法, 频繁地调用将会显著影响性能.<br>
  参阅 Paper 的 [API-to-get-a-BlockState-without-a-snapshot.patch#L6](https://github.com/PaperMC/Paper-archive/blob/b48403bd69f534ffd43fe2afb4e8e1f1ffa95fe1/patches/server/0160-API-to-get-a-BlockState-without-a-snapshot.patch#L6) 补丁以获取更多信息.
    * 如果设为 `true`, 每次插件调用相关方法时, 都会创建 BlockState 的快照 (副本).
    * 如果设为 `false`, 每次插件调用相关方法时将, 直接获取目标 BlockState 本身, 除非插件指定要求使用其快照.
  <br><br>
  __推荐值: (推荐仅在遇到上述卡顿时设为 `false`)__
18. 当实体处在 *inactive tick* 时, 是否将 *goal selector* 的 tick 计算限制为每秒一次. 这可以略微提高性能, 但会对游戏机制有略微影响.<br>
  <br>
  __推荐值: `true`__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

19. 是否当目标容器已满时冷却漏斗, 以避免其尝试移动物品.<br>
  <br>
  __推荐值: `true` (将下方的 `enabled` 设为 true)__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

20. 当漏斗冷却时, 等待多长时间再次将再次尝试移动物品的操作.<br>
  (以 tick 为单位)<br>
  如果设为 &leq; `0`, 将禁用此冷却功能.<br>
  <br>
  __推荐值: `8`__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>8</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>0</code></td></tr>
    </table>

21. 如果地图没有渲染器, 是否跳过地图内容的更新.<br>
  这可以提高使用 ImageMap 之类插件时的性能.<br>
  <br>
  __推荐值: `true`__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

    !!! note "注意"

        开启此配置项可能会导致原版地图的内容停止更新.

22. 当生物处在 *不活跃* 且 *无感知* 的状态时, 是否跳过其 AI tick 的计算. *无感知* 的生物会像呆子一样, 不会自主活动, 也不会在与其交互时作出反应.<br>
  <br>
  __推荐值: `true`__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

23. 本节包含减少发送无用数据包的配置.
24. 是否减少发送给玩家的无用实体移动数据包.<br>
  <br>
  __推荐值: `true`__
25. 是否优化动力铁轨的逻辑. 将使用完全重写的动力铁轨迭代逻辑, 可提升近 4 倍 的性能.<br>
  <br>
  __推荐值: `true`__
26. 是否优化矿车的 tick 计算. 通过跳过部分碰撞计算的方式, 以减少 `getEntities()` 调用和一些 Bukkit 事件调用的耗时.<br>
  这可以更好地承载大量的堆叠矿车, 特别适用于 [无政府服](https://minecraftservers.org/type/anarchy).<br>
  <br>
  __推荐值: `true`__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

27. 每隔多少 tick 计算一次矿车碰撞.<br>
  (以 tick 为单位)<br>
  <br>
  __推荐值: `30`__
28. 是否为世界结构生成使用更快的任务排序.

    !!! note "注意"

        此配置项可能导致结构生成任务的合并顺序不一致.

29. 是否使用更快的随机数生成器.<br>
  随机数生成在 Minecraft 中几乎无处不在, 此功能可以显著提升性能.<br>
  <br>
  __推荐值: `true` (将下方的 `enabled` 设为 true)__

    !!! note "注意"

        需要使用支持 `RandomGenerator` 的 JVM 来运行服务器. 一些 JRE 不支持此功能.

30. 需要使用哪种随机数生成器?<br>
  可参阅 [Java 随机数生成器](https://www.baeldung.com/java-17-random-number-generators#1-api-design-1), 了解所有可用的随机数生成器.<br>
  <br>
  __推荐值: `Xoroshiro128PlusPlus`__
31. 是否为世界生成使用更快的随机数生成器.<br>
    * 如果设为 `true`, 与世界生成相关的 `Random` 调用将使用上述 `random-generator` 指定的随机数生成器, 世界生成将会与原版略有不同.
    * 如果设为 `false`, 与世界生成相关的 `Random` 调用将使用原版随机数生成器.
  <br><br>
  __推荐值: `true`__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

32. 在使用快速随机数生成器生成史莱姆区块时, 是否在服务器启动时输出警告消息到控制台.
33. 是否使用原版随机数生成器来生成史莱姆区块, 以保持原版行为.<br>
  如果服务器中已存在史莱姆农场或相关依赖史莱姆区块的红石机器, 请开启此配置项; 否则, 史莱姆区块的坐标将会偏移.<br>
  <br>
  __推荐值:__ (取决于你服务器的类型, 参阅下方的 `基于目标的推荐值` 了解更多.)

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>false</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>true</code></td></tr>
    </table>

34. 实体的最长存活时间 (又称 Entity TTL).<br>
  (以 tick 为单位)<br>
  如果下列列表中某实体的存活时间超过此值, 将清除该实体. 🛈<br>
  如果设为 `-1`, 则禁用此功能.<br>
  <br>
  __推荐值:__

    | 实体                 | 最长存活时间 |
    |--------------------|--------|
    | SNOWBALL           | 200    |
    | LLAMA_SPIT         | 150    |
    | DRAGON_FIREBALL    | 150    |
    | EGG                | 300    |
    | FIREBALL           | 600    |
    | SMALL_FIREBALL     | 400    |
    | WIND_CHARGE        | 200    |
    | BREEZE_WIND_CHARGE | 200    |
    | WITHER_SKULL       | 200    |

    > 🛈 = 在此处, 实体存活的时间指的是实体存在的总时间, 该时间不会因区块的卸载或加载而重置.

35. 是否缓存 *Minecraft EntityType* 到 *Bukkit EntityType* 的类型转换结果, 这可以获得微小的性能提升.<br>
  <br>
  __推荐值: `true`__
36. 根据距离优化生物 AI (又称 DAB), 在生物远离玩家时减少大脑 AI tick 计算的频率.<br>
  <br>
  __推荐值: `true` (将下方的 `enabled` 设为 true)__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code> (或参阅下方的 <code>dab.blacklisted-entities</code> 获取更多信息)</td></tr>
    </table>

37. 非水生生物在水中时, 是否不受 DAB 的影响.<br>
  如果设为 `true`, 可以修复实体远离玩家时在水中溺死的问题. 修复了 [Pufferfish 的 issue#58](https://github.com/pufferfish-gg/Pufferfish/issues/58).<br>
  <br>
  __推荐值: `true`__
38. 距离玩家多少格 DAB 开始生效.<br>
  <br>
  __推荐值: `8`__
39. 最远处的实体每隔多长时间进行一次寻路和 AI 相关行为的 tick 计算.<br>
  (以 tick 为单位, 默认的 20 tick = 1 秒)<br>
40. 该配置项定义了距离对实体 tick 计算频率的影响程度 `tick 频率 = (生物到玩家距离 ^2) / (2^ 此 activation-dist-mod 值)`.
    * 如果希望距离较远的实体 __少__ tick 计算 一些, 设为 `7`.
    * 如果希望距离较远的实体 __多__ tick 计算 一些, 设为 `9`.
  <br><br>
  __推荐值: `7`__
41. DAB 黑名单, 名单内的生物将不受 DAB 的影响.<br>
  <br>
  例如, 一些生存服拥有很多怪物农场或者刷怪塔. 而某些寻路式刷怪塔需要怪物拥有目标来吸引仇恨, 这类刷怪塔可能会因 DAB 而无法正常工作. 通过将对应生物添加到此黑名单, 来解决刷怪塔无法工作的问题.<br>
  如果遇到这类刷怪塔的生物像被冻结了一样停在原地, 不移动. 并且你不确定是否由 DAB 造成的, 可以尝试将对应生物添加到此黑名单, 然后重启服务器并检查此问题是否修复.<br>
  <br>
  黑名单格式: `[VILLAGER]` 或者 `[VILLAGER, ZOMBIFIED_PIGLIN]`, 填入你想添加的实体类型 (你可以在 [Paper 的 Javadoc](https://jd.papermc.io/paper/1.21.1/org/bukkit/entity/EntityType.html) 里找到所有的实体类型).

    ??? note "再深入一些?"

        事实上,  `dab.blacklisted-entities` 接受所有 YAML 允许的列表 (list) 格式.<br>
        <br>
        如果你只添加一种实体类型到 DAB 黑名单, 可以使用以下任一格式:
        ```yaml
        dab:
          blacklisted-entities: [VILLAGER]
        ```
        或者
        ```yaml
        dab:
          blacklisted-entities:
            - VILLAGER
        ```
        如果你需要添加多个实体类型到 DAB 黑名单, 可以使用以下任一格式:
        ```yaml
        dab:
          blacklisted-entities: [VILLAGER, ZOMBIFIED_PIGLIN]
        ```
        或者
        ```yaml
        dab:
          blacklisted-entities:
            - VILLAGER
            - ZOMBIFIED_PIGLIN
        ```
        如果你仍然不确定你所写的格式是否正确, 可以使用 [YAML Checker](https://yamlchecker.org/), 或者任何在线 YAML 格式效验工具来验证你的配置是否正确.

42. 区块卸载时不保存激活的TNT.<br>
  当玩家意外掉线或者玩家远离导致区块被卸载时, 此功能可防止机器被 TNT 炸毁. 适用于拥有较多 TNT 相关机器的生存服.<br>
  <br>
  __推荐值: `true`__
43. 区块卸载时不保存掉落的方块.<br>
  <br>
  __推荐值: `true`__



44. 本节包含对特定问题的修复.
45. 是否禁止玩家进入已满服务器.<br>
  如果设为 `true`, 应给予玩家 `purpur.joinfullserver` 权限以允许玩家进入满人的服务器, 而不是使用 `PlayerLoginEvent#allow` 方法.



46. 本节包含修改游戏机制的功能.
47. 是否使用 Spigot 默认的掉落物合并机制.
48. 是否在玩家切换维度时尝试使用 "平滑传送".<br>
  此功能需要源世界和目标世界具有相同的逻辑高度才能生效.

    !!! warning "警告"

        实验性功能, 请及时反馈你遇到的问题!

49. 每组掉落物的最大堆叠大小.

    !!! warning "警告"

        __不推荐__ 使用此功能. 此功能仍在开发中, 存在已知问题.<br>
        且可能在未来被移除. __请勿__ 修改此配置, 除非你知道自己做什么!

50. 每组掉落物可以堆叠的最大数量.
51. 容器被破坏时允许掉落的最大物品堆叠数量.
52. 本节包含调整击退相关行为的功能.
53. 是否允许雪球击退玩家.
54. 是否允许鸡蛋击退玩家.
55. 是否允许玩家击退僵尸.
56. 是否禁用 Spigot 内置的 "moved too quickly / wrongly" 移动速度检查. (针对玩家和载具的移速).<br>
  如果设为 `true`, 玩家可以高速移动或使用载具 (例如矿车) 以异常速度移动.<br>
  <br>
  __推荐值: `true`__
57. 玩家允许用物品进行交互的最远距离.<br>
  <br>
  一些 [无政府服](https://minecraftservers.org/type/anarchy) 或类似服务器可能允许玩家使用黑客端作弊. 如果你希望这些玩家能够使用 基于发包的, 与水晶相关的 功能 (例如 CEV Breaker、BedAura等), 可能需要调整该配置项.<br>
  建议设为 `10.0000001`, 以允许玩家使用相关的黑客端功能.
  <br>
  如果设为 `-1`, 将禁用此最远交互距离检查.<br>
  <br>
  __推荐值: `10.0000001` (适用于无政府服)__

    !!! note "注意"

        如果设为 `-1`, 玩家将可以使用黑客端的一些发包功能, 也能够使用 [Nocom 漏洞](https://github.com/nerdsinspace/nocom-explanation)!



58. 本节包含与网络相关的功能.
59. 熙熙攘攘, 我们的协议.<br>
  本部分包含为一些提升游戏体验 (QoL) 的实用模组提供额外的协议支持.<br>
  <br>
  这些额外的协议支持仅在客户端安装了相应模组时才会生效. 这意味着, 如果开启了特定的协议支持, 并且玩家在客户端安装了该模组, 他们可以获得下方配置中描述的额外功能. 但对于没有安装相应模组的玩家, 一切都和之前一样.

    !!! note "注意"

        开启协议支持后, 可能导致和 [ViaVersion](https://modrinth.com/plugin/viaversion) 不兼容.<br>
        并且我们建议玩家使用与服务器核心相同版本的客户端, 并安装对应模组的最新版本, 否则将会无法进入服务器.

60. 是否开启对 [Jade](https://modrinth.com/mod/jade) 的协议支持.<br>
  如果设为 `true`, 安装了 Jade 模组的玩家可以在客户端显示储存容器中的物品信息, 熔炉燃烧进度, 酿造台进度, 篝火上的食物, 蜂巢中的蜜蜂数据等更多贴合原版的功能.
61. 是否开启对 [AppleSkin](https://modrinth.com/mod/appleskin) 的协议支持.<br>
  如果设为 `true`, 安装了 AppleSkin 模组的玩家可以在客户端显示准确的饱和度 / 疲劳值.
62. 是否开启对 [AsteorBar](https://modrinth.com/mod/asteorbar) 的协议支持.<br>
  如果设为 `true`, 安装了 AsteorBar 模组的玩家可以在客户端显示准确的饱和度 / 疲劳值.
63. 是否开启对 [ChatImage](https://modrinth.com/mod/chatimage) 的协议支持.<br>
  如果设为 `true`, 安装了 ChatImage 模组的玩家可以看到使用 CICode 格式发送的图片.
64. 是否开启对 [XaeroMap](https://modrinth.com/mod/xaeros-minimap) 的协议支持.<br>
  如果设为 `true`, 安装了 Xaero's MiniMap 或 Xaero's WorldMap 模组的客户端将根据下方的 `protocol-support.xaero-map-server-id` 存储和服务器挂钩的玩家坐标点和死亡点, 防止服务器名称或 IP 更改时数据被删除或刷新.
65. XaeroMap 用于标识服务器的唯一数字 ID. 首次启动服务器时自动随机生成.
66. 是否开启对 [Syncmatica](https://modrinth.com/mod/syncmatica) 的协议支持.<br>
  如果设为 `true`, 安装了 Syncmatica 模组的玩家可以上传其 [投影](https://modrinth.com/mod/litematica) 文件或从服务器下载共享的投影. 所有安装了 Syncmatica 模组的玩家都可以查看并使用其他玩家共享的投影.
67. 是否限制每个共享投影的文件大小.
68. 上传至服务器的共享投影的最大文件大小.<br>
  (以 字节 为单位, 默认的 40,000,000 字节 ≈ 38 MB)
69. 是否开启 MC 1.19.1 引入的聊天消息签名.<br>
  如果设为 `false`, 将无法举报玩家的聊天消息, 并且玩家进服时不会显示不安全警告弹窗.<br>
  <br>
  __推荐值: `false`__



70. 本节包含一些杂项功能.
71. 未知指令提示, 在执行未知的指令时将向其发送.<br>
  需要使用 [MiniMessage](https://docs.advntr.dev/minimessage/format) 格式.<br>
  如果设为 `default` 或保留默认值, 将使用原版默认的未知指令提示.<br>
  <br>
  可用占位符:
    * __`<detail>`__ - 未知指令的详细信息.

    !!! note "API / 插件 友好"

        此功能对 API / 插件 友好.
        这意味着插件可以使用 `UnknownCommandEvent#message` 或 `UnknownCommandEvent#setMessage` 方法覆盖此配置项.

72. 服务端核心名字. 在 F3 菜单和服务器 MOTD 中显示.
73. 服务端 GUI 控制台名字. 如果启动服务器时未添加 `--nogui` 选项, 将在核心自带的 GUI 控制台中显示.
74. [Sentry](https://sentry.io/welcome/) 是一个应用程序监控服务, 皆在更好地收集, 记录, 跟踪错误日志和相关信息, 协助运维人员更好的定位并修复问题.<br>
  <br>
  开启 Sentry 集成后, 你无需再手动审计冗长的日志以寻找错误. Sentry 可以收集服务器运行时发生的错误, 允许你通过 Sentry 的 Web 面板跟踪, 帮助你更轻松, 快速地定位问题并修复错误.<br>
  <br>
  参阅 __[配置 Sentry](../../how-to/setup-sentry.md)__ 以了解如何配置 Sentry 并获取下方 `sentry.dsn` 所需的 DSN 密匙.<br>
75. Sentry 的 DSN 密匙.<br>
  如果设为空 `''`, 则禁用 Sentry.
76. 等于或高于此等级的日志将被记录.
77. 是否仅记录带有 Throwable 的日志. 
78. 是否使用安全种子功能.<br>
  所有矿石和结构将使用 1024 位的种子生成, 而不是原版中的 64 位种子, 从而使破解种子变得不可能.<br>
  如果在已经存在的世界中使用安全种子, 则只会应用在新生成的区块.<br>
  <br>
  __推荐值: `true` (将下方的 `enabled` 设为 true)__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td>-</td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

79. 是否移除原版的用户名检查, 让 __所有字符__ 都可作为用户名, 包括中文等 (仅适用于离线服务器).<br>
  如果设为 `true`, 允许非英文名玩家进服.
80. 在 `spigot.yml` 中没有开启 bungeecord 模式的情况下, 是否允许玩家通过代理端进入后端服务器.
81. 当玩家尝试编辑其无法编辑的告示牌时, 是否在控制台打印警告信息.<br>
  如果设为 `true`, 可以防止某些情况下玩家使用某些方法在控制台刷屏.<br>
  <br>
  __推荐值: `true`__

82. Linear 是一种区块文件格式, 使用 [ZSTD 压缩](https://facebook.github.io/zstd/) 代替 MC 原版的 ZLIB 压缩算法. 此格式可以节省约 ~50% 的磁盘空间.<br>
  在使用 Linear 区块格式前，请确保你已 __阅读 [Linear 文档](https://github.com/xymb-endcrystalme/LinearRegionFileFormatTools)__ 并完成所有必需步骤, 然后将下方的 `region-format-settings.region-format` 改为 `LINEAR`.

    !!! warning "警告"

        实验性功能, 存在丢失区块数据的潜在风险. 在切换到 Linear 格式之前请备份你的服务端.<br>
        并且我们不推荐使用 Linear 区块格式, 用原版的 ANVIL 格式 (.mca) 就足够了. Leaf 用了重构版的 Linear 保存系统, 可以更安全的保存区块大大减小丢数据的可能性, 虽然比原版的 Linear 更慢. 但是无论如何, 这个重构的改动是值得的, 毕竟数据无价.

83. 可用区块格式: `"MCA"`, `"LINEAR"`.
84. Linear 区块格式文件的压缩等级.
85. 当检测到未知的区块文件格式时, 是否在控制台抛出异常并崩溃服务器.
86. Linear 区块格式数据保存到磁盘的频率.<br>
  (以 秒 为单位)
87. 卡顿滞后补偿, 这可以在服务器卡顿或低 TPS 时确保玩家的基本游戏体验.<br>
  <br>
  __推荐值: `true` (将下方的 `enabled` 设为 true)__
88. 是否开启水流动的滞后补偿.<br>
  <br>
  __推荐值: `true`__
89. 是否开启岩浆流动的滞后补偿.<br>
  <br>
  __推荐值: `true`__
90. 是否在 `Bukkit#getTPS` 和 `Server#getTPS` API 方法的结果中包含5秒 TPS 数据.<br>
    * 如果设为 `true`, 可以通过 `getTPS` 方法获取包含4个元素的 TPS 数组 (`5s, 1m, 5m, 15m`).
    * 如果设为 `false`, 可以通过 `getTPS` 方法获取包含3个元素的 TPS 数组 (`1m, 5m, 15m`).

    ??? note "再深入一些?"

        如果你的插件基于 Gale API 或 Leaf API, 或者运行在 Leaf 上并使用反射来获取 TPS, 可以调用 `Bukkit#getTPSIncluding5SecondAverage` 方法来获取包含5秒 TPS 的 TPS 数组 (`5s, 1m, 5m, 15m`).<br>
        同时, 你也可以调用 `Bukkit#get5SecondTPSAverage` 来获取5秒 TPS 的平均值 (`double` 类型).

91. 是否不发送指定的物品组件信息给客户端. 这可能会破坏依赖该组件信息的资源包和客户端模组. 需要一个组件类型列表, 填写错误将会导致此功能无法正常工作.<br>
  例如, 你可以填入 `["custom_data"]` 来隐藏物品中 *CUSTOM_DATA* 组件的内容. 同时, 此功能也能避免某些频繁的客户端动画.

    !!! note "注意"

        你必须知道你填进去的是什么, 有什么用！此功能会处理所有的物品!

92. 玩家连接提示, 当玩家加入或退出服务器时广播发送给所有在线玩家.<br>
  需要使用 [MiniMessage](https://docs.advntr.dev/minimessage/format) 格式.<br>
  如果设为 `default` 或保留默认值, 将使用原版默认的进服和退服提示.<br>
  <br>
  可用占位符:
    * __`%player_name%`__ - 玩家名.
    * __`%player_displayname%`__ - 玩家显示名称.

    !!! note "API / 插件友好"

        此功能对 API / 插件 友好.
        这意味着插件可以使用 `PlayerJoinEvent` 或 `PlayerQuitEvent`, 的相关方法覆盖此配置项.

93. 玩家进服提示.
94. 玩家退服提示.
95. 是否在玩家进服时缓存 PlayerProfile 数据.<br>
  当 Mojang 的认证服务器宕机时, 此功能可以避免玩家验证失败导致无法进服.
96. 玩家 PlayerProfile 数据的缓存时间.<br>
  (以 分钟 为单位)<br>
  如果超时, 将在玩家下次加入时重新请求 Mojang 的认证服务器获取 PlayerProfile 数据.<br>
