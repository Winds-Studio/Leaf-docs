# Globale Leaf Konfiguration

!!! info "Info"

    Diese YAML Konfiguration zeigt die standardmäßige Struktur der Konfigurationswerte der globalen Konfiguration von Leaf (==config/leaf-global.yml==)

    Diese Konfiguration basiert auf der neusten 1.21.1 Version von Leaf

    Klicke auf die Pfeile hinter den Konfigurationswerten um die entsprechende Beschreibung anzusehen

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
  # **Experimentelle Funktionen, die unter Umständen zu Datenverlust führen können!**
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
  # Dies könnte zu einer inkonsistenten Reihenfolge zukünftiger Kompositionsaufgaben führen.
  faster-structure-gen-future-sequencing: true #(28)!
  # Erfordert eine JVM, die RandomGenerator.
  # Manche JREs unterstützten dies nicht.
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
  # **Experimentelle Funktion, bitte melde jegliche Fehler!**
  smooth-teleport: false #(48)!
  # Dies sollte nur mit äußerster Vorsicht geändert werden!
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
    # Erhalte einen DSN Schlüssel bei https://sentry.io/
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
  # INFO: Bei dieser Option ist Kenntnis darüber erforderlich, was eingegeben werden soll und wie es funktioniert! Dies betrifft alle ItemStacks!
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

1. Dieser Abschnitt beinhaltet asynchrone Funktionen, die die Last auf dem Hauptthread (Server Thread) reduzieren sollen, indem Aufgaben asynchron bearbeitet werden.
2. Macht Entity-Tracking asynchron. Kann die Leistung deutlich verbessern, vor allem wenn viele Entities in kleinen Bereichen sind.<br>
  <br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__

    !!! note "Achtung"

        Wenn Plugins wie Citizens vorhanden sind, die echte, NPCs vom Typ Spieler nutzen, muss `async-entity-tracker.compat-mode` unten für weitere Informationen beachtet werden.

3. Aktiviere den Kompatibilitätsmodus um mit Plugins wie Citizens oder anderen Plugins, die reale NPCs vom Typ Spieler nutzen, kompatibel zu sein.<br>
  Bei `true`, können Sichtbarkeitsprobleme von NPCs des Typ Spieler manchmal behoben werden.<br>
  <br>
  `compat-mode` sollte nur aktiviert werden, wenn tatsächlich Citizens oder andere Plugins, die reale NPCs vom Typ Spieler nutzen, vorhanden sind.<br>
  <br>
  Wie empfehlen trotzdem die Nutzung von Paket-basierten oder virtuellen Entity NPC Plugins für eine bessere Leistung, z.B. [ZNPC Plus](https://github.com/Pyrbu/ZNPCsPlus), [Adyeshach](https://github.com/TabooLib/Adyeshach), [Fancy NPC](https://modrinth.com/plugin/fancynpcs), oder andere. Dann kann `compat-mode` deaktiviert bleiben.
4. Die maximale Anzahl an Threads, die für das asynchrone Entity-Tracking genutzt werden.<br>
   Wenn dieser Wert `0` ist, werden automatisch 1/4 der Anzahl an CPU Kernen genutzt, allerdings niemals weniger als 1.<br>
  <br>
  __Empfohlener Wert: 1/2 der CPU Kerne__
5. Thread Keepalive Zeit. Threads ohne Aufgabe werden nach dieser Zeit beendet.<br>
  (Einheit: Sekunden)
6. Macht das Speichern von Spielerdaten asynchron.

    !!! warning "Warnung"

        Experimentelle Funktion, die in manchen Fällen zu Datenverlust führen kann!

7. Macht Mob-Pathfinding Berechnungen asynchron.<br>
  <br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__
8. Die maximale Anzahl an Threads, die für das asynchrone Entity-Pathfinding genutzt werden.<br>
   Wenn dieser Wert `0` ist, werden automatisch 1/4 der Anzahl an CPU Kernen genutzt, allerdings niemals weniger als 1.<br>
  <br>
  __Empfohlener Wert: 1/3 der CPU Kerne__
9. Thread Keepalive Zeit. Threads ohne Aufgabe werden nach dieser Zeit beendet.<br>
  (Einheit: Sekunden)
10. Gibt an, ob asynchrones Mob-Spawning aktiviert sein soll.<br>
  Auf Servern mit vielen Entities, kann dies die Leistung um bis zu 15% steigern. Hierfür muss `per-player-mob-spawns` der Paper Konfiguration auf `true` gestellt sein.<br>
  Anmerkung: Hierdurch werden Mobs nicht wirklich asynchron gespawnt (Das wäre sehr unsicher). Hierdurch werden nur einige aufwändige Berechnungen ausgelagert, die für das Mob-Spawning erforderlich sind.<br>
  <br>
  __Empfohlener Wert: `true`__
11. Gibt an, ob der asynchrone Locator aktiviert sein soll.<br>
  Hierdurch wird das Lokalisieren von Strukturen auf andere Threads ausgelagert.<br>
  Aktuell verfügbar für:
    * `/locate` Befehl
    * Delfin Schatzsuche
    * Enderauge Festung Suche
  <br><br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__
12. Die maximale Anzahl an Threads, die für den asynchronen Locator genutzt werden.<br>
   Wenn dieser Wert &leq; `0` ist, wird immer 1 Thread genutzt.<br>
  <br>
  __Empfohlener Wert: `1` oder `2`__
13. Thread Keepalive Zeit. Threads ohne Aufgabe werden nach dieser Zeit beendet.<br>
  (Einheit: Sekunden)



14. Dieser Abschnitt beinhaltet Performance-Einstellungen um unnötige Berechnungen zu reduzieren oder effizientere Methoden zu nutzen um den Server zu optimieren.
15. Gibt an, ob [virtuelle Threads](https://docs.oracle.com/en/java/javase/21/core/virtual-threads.html) ab JDK 21 für den Aync Chat Executer genutzt werden sollen.<br>
  <br>
  __Empfohlener Wert: `true`__
16. Gibt an, ob [virtuelle Threads](https://docs.oracle.com/en/java/javase/21/core/virtual-threads.html) ab JDK 21 für den CraftAsyncScheduler genutzt werden sollen. Dies kann die Leistung von Plugins verbessern, die den asynchronen Scheduler nutzen.<br>
  <br>
  __Empfohlener Wert: `true`__
17. Gibt an, ob ein Snapshot von TileEntity / BlockState erstellt werden soll, wenn diese empfangen werden.<br>
  <br>
  Manche Plugins könnten `getHolder` nutzen, um den Halter eines Inventars zu erhalten, der das holen des BlockStates involvierte.<br>
  Wenn es zum Beispiel sehr viele Trichter gibt und Plugins diese Methode aufrufen während sie auf manche Events hören (z.B. Trichter Events), ist es sehr aufwändig den BlockState neu zu erstellen und den ItemStack in häufigen Aufrufen zu parsen.<br>
  Siehe [API-to-get-a-BlockState-without-a-snapshot.patch#L6](https://github.com/PaperMC/Paper-archive/blob/b48403bd69f534ffd43fe2afb4e8e1f1ffa95fe1/patches/server/0160-API-to-get-a-BlockState-without-a-snapshot.patch#L6) von Paper für weitere Informationen.
    * Bei `true`, wird ein Snapshot (Kopie) des BlockStates jedes Mal erstellt, wenn ein Plugin die Methoden aufruft.
    * Bei `false`, wird der echte BlockState geholt beim Aufruf er Methoden, außer das Plugin gibt an, den Snapshot zu nutzen.
  <br><br>
  __Empfohlener Wert: `false` (Nur wenn der oben beschriebene Lag auftritt)__
18. Verlangsamt die *AI Zielauswahl* Berechnung, die jeden *inaktiven Tick* durchgeführt wird. Dies kann die Performance um ein paar Prozent verbessern, hat aber leichte Einflüsse auf das Gameplay.<br>
  <br>
  __Empfohlener Wert: `true`__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

19. Gibt an, ob Versuche eines Trichters, Items in einen vollen Container zu bewegen, verlangsamt werden sollen.<br>
  <br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

20. Wie viele Ticks gewartet wird, bevor das nächste Mal versucht wird Items zu bewegen, wenn der Trichter verlangsamt ist.<br>
  Wenn der Wert &leq; `0` ist, ist dieses Feature deaktiviert.<br>
  <br>
  __Empfohlener Wert: `8`__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>8</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>0</code></td></tr>
    </table>

21. Gibt an, ob Updates für Itemdaten von Karten übersprungen werden sollen, wenn die Karte keinen Renderer hat.<br>
  Dies kann die Leistung verbessern, wenn Plugins genutzt werden, die mit Karten zu tun haben.<br>
  <br>
  __Empfohlener Wert: `true`__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

    !!! note "Achtung"

        Hierdurch könnten Vanilla Karten sich nicht mehr richtig aktuallisieren.

22. Gibt an, ob AI Ticks übersprungen werden sollen, falls das Entity *inaktiv* und *unaufmerksam*. Unaufmerksame Entities führen keine Aktionen bei sich selbst aus oder wenn mit ihnen interagiert wird.<br>
  <br>
  __Empfohlener Wert: `true`__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

23. Dieser Abschnitt ist für die Reduktion von unnötigen Paketen.
24. Gibt an, ob das unnötige Entity Bewegungspaket reduziert werden soll, welches an Spieler gesendet wird.<br>
  <br>
  __Empfohlener Wert: `true`__
25. Gibt an, ob optimierte Aktivierungsschienen genutzt werden sollen. Nutzt eine vollständig neu geschriebene Iterationslogik für Aktivierungsschienen, die bis zu 4x schneller sein kann.<br>
  <br>
  __Empfohlener Wert: `true`__
26. Gibt an, ob Minecart Ticking optimiert werden soll. Durch das Überspringen von Tick Kollisionen, werden aufwändige `getEntities()` Aufrufe und Bukkit Eventaufrufe reduziert.<br>
  Dadurch können große Mengen an gestapelten Minecarts besser gehandhabt werden, was nützlich für [Anarchy Server](https://minecraftservers.org/type/anarchy) ist.<br>
  <br>
  __Empfohlener Wert: `true`__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

27. Wie viele Ticks übersprungen werden sollen, bevor die nächste Minecart Kollision überprüft wird.<br>
  <br>
  __Empfohlener Wert: `30`__
28. Gibt an, ob eine schnellere Aufgabensequenzierung für das Generieren von Strukturen genutzt werden soll.

    !!! note "Achtung"

        Dadurch kann die Reihenfolge von zukünftigen Compose-Aufgaben inkonsistent werden.

29. Gibt an, ob der schnellere Zufallsgenerator genutzt werden soll.<br>
  Zufalls wird fast überall in Minecraft genutzt. Diese Einstellung kann eine gute Performanceverbesserung zur Folge haben.<br>
  <br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__

    !!! note "Achtung"

        Erfordert eine JVM, die `RandomGenerator`. Manche JREs unterstützen dies nicht.

30. Welcher Zufallsgenerator soll genutzt werden?<br>
  Verfügbare Zufallsgeneratoren können hier gefunden werden [Zufallsgeneratoren in Java](https://www.baeldung.com/java-17-random-number-generators#1-api-design-1).<br>
  <br>
  __Empfohlener Wert: `Xoroshiro128PlusPlus`__
31. Gibt an, ob der schnellere Zufallsgenerator für Weltgenerierung genutzt werden soll.<br>
    * Bei `true` werden `Random` Aufrufe, die mit Weltgenerierung zu tun haben, den schnelleren Zufallsgenerator nutzen, der oben in `random-generator` angegeben ist. Die Weltgenerierung wird sich leicht von Vanilla unterscheiden.
    * Bei `false` werden `Random` Aufrufe, die mit Weltgenerierung zu tun haben, den normalen Vanilla Generator nutzen.
  <br><br>
  __Empfohlener Wert: `true`__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

32. Gibt an, ob der Server eine Warnung beim Start ausgibt, wenn der schnellere Zufallsgenerator für Schleimchunk Generierung genutzt wird.
33. Gibt an, ob der Vanilla Generator für die Schleimchunk Generierung genutzt werden soll.<br>
  Wenn es bereits Schleimfarms oder andere Bauwerke, die Schleimchunks benötigen auf dem Server gibt, sollte dies aktiviert werden, da sonst der Standort der Schleimchunks verändert wird.<br>
  <br>
  __Empfohlener Wert:__ (Hängt vom Server ab, siehe `Werte für Ziele` unten.)

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>false</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>true</code></td></tr>
    </table>

34. Diese Werte geben in Ticks die maximale Lebensspanne eines Entites an (Wie eine Art TTL).<br>
  Wenn ein Entity in dieser Liste ist und länger als diese Zeit überlebt hat, wird es entfernt. 🛈<br>
  Wenn ein Wert `-1` ist, wird die Überprüfung für dieses Entity deaktiviert.<br>
  <br>
  __Empfohlene Werte:__

    | Entity             | Wert |
    |--------------------|------|
    | SNOWBALL           | 200  |
    | LLAMA_SPIT         | 150  |
    | DRAGON_FIREBALL    | 150  |
    | EGG                | 300  |
    | FIREBALL           | 600  |
    | SMALL_FIREBALL     | 400  |
    | WIND_CHARGE        | 200  |
    | BREEZE_WIND_CHARGE | 200  |
    | WITHER_SKULL       | 200  |

    > 🛈 = Die Zeit, die ein Entity lebt, wird nicht durch das Laden und Entladen eines Chunks zurückgesetzt.

35. Gibt an, ob das Ergebnis von Konversionen von *Minecraft EntityType* zu *Bukkit EntityType* zwischengespeichert werden soll. Dies gibt eine winzige Verbesserung.<br>
  <br>
  __Empfohlener Wert: `true`__
36. Dynamische Aktivierung von Mob AIs. Optimiert die AI von Entites um die Tick-Frequenz zu reduzieren, wenn sie weit von Spielern entfernt sind.<br>
  <br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code> (oder siehe <code>dab.blacklisted-entities</code> unten für mehr)</td></tr>
    </table>

37. Gibt an, ob Entites im Wasser, die dort eigentlich nicht hingehören, von DAB beeinflusst werden sollen.<br>
  Falls `true`, könnte dies beheben, dass Entites im Wasser ertrinken, die weit vom Spieler entfernt sind. Dies behebt [Issue#58 von Pufferfish](https://github.com/pufferfish-gg/Pufferfish/issues/58).<br>
  <br>
  __Empfohlener Wert: `true`__
38. Dieser Wert gibt an, wie weit Entites vom Spieler entfernt sein müssen, um von DAB beeinflusst zu werden.<br>
  <br>
  __Empfohlener Wert: `8`__
39. Dieser Wert gibt an, wie oft in Ticks das Pathfinding und Verhalten von dem am weitesten entfernten Entity getickt wird. (Beachte: 20 Ticks = 1s).
40. Dieser Wert gibt an, wie stark die Entfernt die Tickfrequenz des Entites beeinflusst. `freq = (distanceToPlayer^2) / (2^value)`.
    * Wenn weit entfernte Entites __weniger__ häufig getickt werden sollen, nutze `7`.
    * Wenn weit entfernte Entites __häufiger__ getickt werden sollen, nutze `9`.
  <br><br>
  __Empfohlener Wert: `7`__
41. Eine Liste an Entites, die nicht von DAB beeinflusst werden.<br>
  <br>
  Mache Survival-Server haben Mobfarms, wie erfordern, dass Mobs ein Ziel haben. Diese Arten von "Pathfinding" Mobfarmen könnten durch DAB kaputt gehen. Dies kann behoben werden, indem entsprechende Mobs in diese DAB Blackliste eingetragen werden.<br>
  Wenn einige, bestimmte Mobfarms nicht funktionieren, die Mobs sich nicht bewegen und du nicht sicher bist, ob DAB der Grund ist, kannst du versuchen sie zu dieser Blackliste hinzuzufügen.<br>
  <br>
  Format: `[VILLAGER]` oder `[VILLAGER, ZOMBIFIED_PIGLIN]` (Alle Entity Typen finden sich hier: [Paper Javadoc](https://jd.papermc.io/paper/1.21.1/org/bukkit/entity/EntityType.html)).

    ??? note "Tiefgehendere Informationen gefällig?"

        Das Format von `dab.blacklisted-entities` akzeptiert alles, das eine gültige YAML Liste ist.<br>
        <br>
        Wenn nur ein Entity zur Blackliste hinzugefügt werden soll, sind diese Formate erlaubt:
        ```yaml
        dab:
          blacklisted-entities: [VILLAGER]
        ```
        oder
        ```yaml
        dab:
          blacklisted-entities:
            - VILLAGER
        ```
        Wenn mehrere Entites zur Blackliste hinzugefügt werden sollen, sind diese Formate erlaubt:
        ```yaml
        dab:
          blacklisted-entities: [VILLAGER, ZOMBIFIED_PIGLIN]
        ```
        oder
        ```yaml
        dab:
          blacklisted-entities:
            - VILLAGER
            - ZOMBIFIED_PIGLIN
        ```
        Der [YAML Checker](https://yamlchecker.org/) kann helfen, den Syntax oder die Konfiguration zu überprüfen.

42. Deaktiviert das Speichern von gezündetem TNT, wenn Chunks entladen werden.<br>
  Dies kann verhindern, dass Maschinen durch TNT explodieren, wenn der Spieler aus Versehen den Server verlässt oder der Chunk entladen wird denn der Spieler weit entfernt ist. Nützlich für Survival Server, die Maschinen mit TNT haben.<br>
  <br>
  __Empfohlener Wert: `true`__
43. Deaktiviert das Speichern von fallenden Blöcken (falling_sand), wenn Chunks entladen werden.<br>
  <br>
  __Empfohlener Wert: `true`__



44. Dieser Abschnitt beinhaltet Fehlerbehebungen für spezifische Probleme.
45. Gibt an, ob das Joinen auf den Server verboten werden soll, wenn der Server voll ist.<br>
  Bei `true`, sollten die Spieler die Permission `purpur.joinfullserver` erhalten, anstatt `PlayerLoginEvent#allow` zu nutzen, um Spielern das Joinen auf einen vollen Server zu erlauben.



46. Dieser Abschnitt beinhaltet Funktionen, die das Spielverhalten beeinflussen.
47. Gibt an, ob der Zusammenfügungsmechanismus von gedroppten Items von Spigot genutzt werden soll.
48. Gibt an, ob ein "smooth teleport" durchgeführt werden soll, wenn ein Spieler die Dimension wechselt.<br>
  Dies erfordert, dass die Ursprungs- und Zielwelt die gleiche logische Höhe haben.

    !!! warning "Warnung"

        Experimentelle Funktion, bitte melde jegliche Bugs!

49. Konfigurierbare maximale Stapelgröße von gedroppten Items.

    !!! warning "Warnung"

        Wir empfehlen diese Funktion __nicht__. Es wird daran gearbeitet und gibt bekannte Probleme<br>
        Möglicherweise wird die Funktion auf in Zukunft entfernt. Diese Option sollte mit __höchster Vorsicht__ benutzt werden!

50. Maximale Anzahl an gedroppten Items, die gestapelt werden sollen.
51. Maximale Anzahl an Items, die gedroppt werden sollen, wenn ein Container zerstört wird.
52. Dieser Abschnitt beinhaltet Optionen, um Verhalten bezüglich Rückstoß anzupassen.
53. Gibt an, ob Schneebälle Spieler zurückstoßen können.
54. Gibt an, ob Eier Spieler zurückstoßen können.
55. Gibt an, ob Spieler Zombies zurückstoßen können.
56. Gibt an, ob die "moved too quickly" / "moved wrongly" Überprüfungen von Spigot für Spieler und Fahrzeuge deaktiviert werden sollen.<br>
  Bei `true`, können sich Spieler oder ihre Fahrzeuge mit extremen Geschwindigkeiten bewegen.<br>
  <br>
  __Empfohlener Wert: `true`__
57. Die maximale Distanz über die ein Spieler mit einem Item interagieren darf.<br>
  <br>
  Manche [Anarchy Server](https://minecraftservers.org/type/anarchy) oder ähnliche Server könnten Spielern das Hacken / Cheaten erlauben. Wenn Spieler Endkristall-Cheats nutzen können sollen, die Paket-basiert sind (z.B. CEV Breaker, BedAura), sollte dieser Wert eventuell angepasst werden.<br>
  Es ist besser diesen Wert auf `10.0000001` zu setzen, damit die Hack-Module genutzt werden können.
  <br>
  Wenn der Wert `-1` ist, wird die Überprüfung der maximal erlaubten Distanz ein Item zu nutzen deaktiviert.<br>
  <br>
  __Empfohlener Wert: `10.0000001` (Für Anarchy Server)__

    !!! note "Achtung"

        Wenn der Wert `-1` ist, können Spieler manche Paket-basierte Cheats nutzen und außerdem den [Nocom Exploit](https://github.com/nerdsinspace/nocom-explanation)!



58. Dieser Abschnitt beinhaltet Funktionen, die mit dem Server Netzwerk zu tun haben.
59. Dieser Abschnitt beinhaltet Funktionen, die Protokollunterstützung für manche QoL oder Utility mods bieten.<br>
  <br>
  Die Protokollunterstützung funktioniert nur, wenn der entsprechende Mod auf dem Client installiert ist. Das bedeutet, dass wenn eine spezifische Protokollunterstützung aktiviert ist und der Spieler den Mod auf seinem Client installiert hat, der Spieler zusätzliche Funktionen erhalten kann, die in den einzelnen Optionen unten beschrieben werden. Für Spieler, die den entsprechenden Mod nicht installiert haben, ändert sich nichts.

    !!! note "Achtung"

        Die Protokollunterstützungen könnten Inkompatibilitäten mit [ViaVersion](https://modrinth.com/plugin/viaversion) zur Folge haben.<br>
        Wir empfehlen, dass die Spieler einen Client mit der selben Version wie der Server nutzen und die neuste Version des entsprechenden Mods installieren. Sonst könnten sie nicht in der Lage sein den Server beizutreten.

60. Gibt an, ob die [Jade](https://modrinth.com/mod/jade) Protokollunterstützung aktiviert werden soll.<br>
  Bei `true` können Spieler, die die Jade Mod installiert haben, zusätzliche Informationen wie Items in Containern, Fortschritte von Öfen, Brauständen, Essen auf Lagerfeuern, Bienen in Bienenstöcken und weitere Vanilla funktionen erhalten.
61. Gibt an, ob die [AppleSkin](https://modrinth.com/mod/appleskin) Protokollunterstützung aktiviert werden soll.<br>
  Bei `true` können Spieler, die die AppleSkin Mod installiert haben, genaue Sättigungs- und Erschöpfungswerte auf dem Client anzeigen.
62. Gibt an, ob die [AsteorBar](https://modrinth.com/mod/asteorbar) Protokollunterstützung aktiviert werden soll.<br>
  Bei `true` können Spieler, die die AsteorBar Mod installiert haben, genaue Sättigungs- und Erschöpfungswerte auf dem Client anzeigen.
63. Gibt an, ob die [ChatImage](https://modrinth.com/mod/chatimage) Protokollunterstützung aktiviert werden soll.<br>
  Bei `true` können Spieler, die die ChatImage Mod installiert haben, Bilder sehen, die andere durch das CICode Format gesendet haben.
64. Gibt an, ob die [XaeroMap](https://modrinth.com/mod/xaeros-minimap) Protokollunterstützung aktiviert werden soll.<br>
  Bei `true` können Spieler, die die Xaero's MiniMap oder Xaero's WorldMap Mod installiert haben, die Koordinaten und Todespunkte anderer Spieler basierend auf der `protocol-support.xaero-map-server-id` des Servers unten speichern, um zu verhindern, dass diese Daten gelöscht oder verändert werden, wenn sich der Servername oder die IP Adresse änert.
65. Numerische ID für XaeroMap um den Server zu identifizieren. Die ID wird beim ersten Start zufällig generiert.
66. Gibt an, ob die [Syncmatica](https://modrinth.com/mod/syncmatica) Protokollunterstützung aktiviert werden soll.<br>
  Bei `true` können Spieler, die die Syncmatica Mod installiert haben, ihre [Litematica](https://modrinth.com/mod/litematica) Schematics Dateien hochladen oder andere Schematics vom Server herunterladen. Jeder Spieler mit der Mod kann auf geteilte Schematics anderer zugreifen.
67. Gibt an, ob das Limit für die maximale Dateigroße von geteilten Schematics Dateien der Litematica Mod aktiviert sein soll.
68. Die maximale Dateigröße in Bytes für jede geteilte Schematics Datei, die auf den Server hochgeladen wird. (40.000.000 Bytes ≈ 38 MB)
69. Gibt an, ob die Signatur von Chatnachrichten aktiviert sein soll, die es seit Minecraft 1.19.1 gibt.<br>
  Bei `false` ist es nicht mehr möglich die Chatnachrichten von Spielern zu melden. Außerdem wird das Pop-Up deaktiviert, Spieler beim Joinen vor unsicheren Nachrichten warnt.<br>
  <br>
  __Empfohlener Wert: `false`__



70. Dieser Abschnitt beinhaltet einige verschiedene, andere Funktionen.
71. Nachricht für unbekannte Befehle. Wird gesendet, wenn ein Spieler einen unbekannten Befehl ausführt.<br>
  Die Nachricht muss das [MiniMessage](https://docs.advntr.dev/minimessage/format) Format verwenden.<br>
  Wenn die Nachricht auf `default` oder den Standardwert gesetzt wird, wird die Vanilla Nachricht für unbekannte Befehle genutzt.<br>
  <br>
  Verfügbare Platzhalter:
    * __`<detail>`__ - Detaillierte Informationen über den unbekannten Befehl.

    !!! note "API / Plugin Kompatibilität"

        Diese Funktion ist gut mit der API / Plugins kompatibel.
        Das bedeutet, dass die Nachricht von Plugins durch `UnknownCommandEvent#message` oder `UnknownCommandEvent#setMessage` überschrieben werden kann.

72. Der Server Markenname, der im F3 Menü und in der MOTD angezeigt wird.
73. Der Server GUI Fenstername, falls der Server ohne die `--nogui` Option gestartet wurde.
74. [Sentry](https://sentry.io/welcome/) ist ein Service für das Monitoring von Anwendung um das Loggen und Nachverfolgen von Fehlern zu verbessern. Es kann dem Entwicklungsteam des Servers bei der Verwaltung helfen.<br>
  <br>
  Nachdem Sentry auf dem Server eingerichtet wurde, ist es nicht mehr notwendig Fehler manuell in den Logs zu untersuchen. Sentry kann die Fehler sammeln, wodurch es einfacher wird diese auf dem Webpanel von Sentry nachzuverfolgen, zu lokalisieren und schließlich einfacher und schneller zu beheben.<br>
  <br>
  Siehe __[Einrichten von Sentry](../../how-to/setup-sentry.md)__ um zu erfahren, wie der DSN Schlüssel eingerichtet und für `sentry.dsn` unten erhalten werden kann.<br>
75. Dein DSN Schlüssel für Sentry.<br>
  Wenn ein leerer Wert `''` angegeben ist, wird Sentry deaktiviert.
76. Logs mit einem Level gleich oder höher als dieser Wert werden aufgezeichnet.
77. Wenn dies aktiv ist, werden nur `Throwables` (z.B. Exceptions und Errors) aufgezeichnet.
78. Gibt an, ob der Seed geschützt werden soll.<br>
  Alle Erze und Strukturen werden mit einem 1024-bit Seed anstelle einem 64-bit Seed generiert, was es nahezu unmöglich macht den Seed herauszufinden.<br>
  Wenn dies in einer bestehenden Welt aktiviert wird, sind nur neu generierte Chunks hiervon betroffen.<br>
  <br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

79. Gibt an, ob die Vanilla Überprüfung der Nutzernamen entfernt werden soll, um __alle Buchstaben__ wie z.B. Chinesische Zeichen zu erlauben. (Ist nur für Server im Offline-Modus nützlich).<br>
  Bei `true` können Spieler den Server betreten, deren Name nicht dem [lateinischen Alphabet](https://de.wikipedia.org/wiki/Lateinisches_Alphabet) entspricht.
80. Gibt an, ob Spieler einen Backendserver durch den Proxy betreten können, ohne auf dem Backendserver den Bungeecord Modus in der `spigot.yml` zu aktivieren.
81. Gibt an, ob der Server Warnungen ausgeben soll, wenn ein Spieler versucht ein Schild zu bearbeiten, wofür er keine Berechtigung hat.<br>
  Dies sollte aktiviert werden, um zu verhindern, dass die Konsole in manchen Fällen überflutet wird.<br>
  <br>
  __Empfohlener Wert: `true`__

82. Linear ist ein Region-Dateiformat, das [ZSTD Kompression](https://facebook.github.io/zstd/) anstelle von ZLIB wie in Vanilla Minecraft nutzt. Dieses Format spart etwa ~50% an Speicherplatz.<br>
  Um das Linear Regionsformat zu nutzen __ließ zuerst die [Linear Dokumentation](https://github.com/xymb-endcrystalme/LinearRegionFileFormatTools)__ um die nötigen Schritte auszuführen. Dann kann `region-format-settings.region-format` unten auf `LINEAR` gesetzt werden.

    !!! warning "Warnung"

        Experimentelle Funktion, die zu Datenverlust führen kann. Vor der Nutzung ist ein Backup des Servers notwendig.<br>
        Wir empfehlen die Nutzung von Linear nicht, da das ANVIL Format von Vanilla (.mca) ausreichend ist. Leaf nutzt eine angepasst Version des Linear Speichersystems, welches sicherer aber etwas langsamer beim Speichern von Chunks ist, um Datenvertlust unwahrscheinlicher zu machen. Obwohl die Vorteile gut ist, ist der Wert von den Daten höher.

83. Verfügbare Regionsformate: `"MCA"`, `"LINEAR"`.
84. Das Level der Kompression für das Linear Regionsformat.
85. Gibt an, ob ein Fehler geworfen soll, um den Server abzustürzen, wenn ein unbekanntes Regionsformat erkannt wird.
86. Das Speicherintervall in Sekunden für die Dateien des Linear Regionsformat.
87. Lag-Kompensation, die sicherstellen könnte, dass die grundlegende Spielerfahrung erhalten bleibt, wenn der Server laggt oder die TPS gering sind.<br>
  <br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__
88. Gibt an, ob die Lag-Kompensation für fließendes Wasser aktiviert sein soll.<br>
  <br>
  __Empfohlener Wert: `true`__
89. Gibt an, ob die Lag-Kompensation für fließende Lava aktiviert sein soll.<br>
  <br>
  __Empfohlener Wert: `true`__
90. Gibt an, ob die 5-Sekunden TPS in den Ergebnissen von `Bukkit#getTPS` und `Server#getTPS` enthalten sein soll.<br>
    * Bei `true` liefert die `getTPS` Methode ein Long-Array mit 4 TPS Werten (`5s, 1m, 5m, 15m`).
    * Bei `false` liefert die `getTPS` Methode ein Long-Array mit 3 TPS Werten (`1m, 5m, 15m`).

    ??? note "Tiefgehendere Informationen gefällig?"

        Wenn du die Gale API oder Leaf API für deine Plugins verwendest oder Reflektion auf einem Leaf Server nutzt, um die TPS zu erhalten, kann `Bukkit#getTPSIncluding5SecondAverage` verwendet werden, um ein TPS Array mit der 5-Sekunden TPS zu erhalten (`5s, 1m, 5m, 15m`).<br>
        Außerdem kann `Bukkit#get5SecondTPSAverage` verwendet werden, um den Durchschnittswert der 5-Sekunden TPS als `double` zu erhalten.

91. Steuert, ob die angegebene Komponenten-Informationen an die Clients gesendet werden. Dadurch könnten Resource Packs oder Client Mods nicht mehr funktionieren, die diese Informationen benötigen. Es wird eine Liste an Komponententypen erfordert, falsche Dinge funktionieren nicht.<br>
  Die Liste kann zum Beispiel mit `["custom_data"]` gefüllt werden, um Komponenten von *CUSTOM_DATA* zu verstecken. Außerdem kann es einige häufige Clientanimationen verhindern.

    !!! note "Achtung"

        Kenntnis darüber ist erforderlich, was eingegeben werden soll und wie es funktioniert! Dies betrifft alle ItemStacks!

92. Verbindungsnachrichten, werden an alle Spieler auf dem Server gesendet, wenn jemand dem Server beitritt oder ihn verlässt.
  Diese Nachricht muss das [MiniMessage](https://docs.advntr.dev/minimessage/format) Format nutzen.<br>
  Wenn die Nachricht `default` oder der Standardwert ist, werden die Vanilla Nachrichten genutzt.<br>
  <br>
  Verfügbare Platzhalter:
    * __`%player_name%`__ - Name des Spielers.
    * __`%player_displayname%`__ - Anzeigename des Spielers.

    !!! note "API / Plugin Kompatibilität"

        Diese Funktion ist gut mit der API / Plugins kompatibel.
        Das bedeutet, dass die Nachrichten von Plugins durch das `PlayerJoinEvent` oder `PlayerQuitEvent` überschrieben werden können.

93. Die Nachricht beim Beitreten eines Spielers.
94. Die Nachricht beim Verlassen eines Spielers.
95. Gibt an, ob das Ergebnis für das Spielerprofil beim Joinen auf den Server zwischengespeichert werden soll.<br>
  Dies ist nützlich, falls die Authentifizierungsserver von Mojang offline sind.
96. Der Timeout des Zwischenspeichers für Spielerprofile.<br>
  (Einheit: Minuten)<br>
  Wenn der gegebene Timeout abläuft, wird eine weitere Anfrage an die Authentifizierungsserver von Mojang gesendet, um die Profildaten des Spielers beim nächsten Joinen zu holen.<br>
