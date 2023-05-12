此配置由Dg32z_ {779664169} 所制作

后续的版本发布于Releases
本次的反作弊配置搭配:
GrimAC V2.3.35
+
Matrix 7.0.36A [不提供,需要购买]
+
Vulcan 2.7.2 [不提供,需要购买]

此配置适用于1.8x-1.19x
在使用前请查看3个反作弊的配置中的部分注释,可以在误判时帮您的忙

QQ群: 716213919
QQ: 779664169
Discord: Simpleeeee#2174

ProtocolLib：https://ci.dmulloy2.net/job/ProtocolLib/lastSuccessfulBuild/
Matrix: http://matrix.rip/
Vulcan: https://www.spigotmc.org/resources/vulcan-anti-cheat-advanced-cheat-detection-1-7-1-19-3.83626/
Grim: https://www.spigotmc.org/resources/grim-anticheat.99923/
license: ""
# Use this if you live in China
force-fallback: true

messages:
  main-color: "&f"
  second-color: "&c"

  prefix: "%main-color%LPX >>"

  kick: "&c数据异常"
  kick-alert: "%prefix% %second-color%%player% &7was kicked"

  no-permission: "%prefix% &cInsufficient permissions &7(%permission%)"
  invalid-arguments: "%prefix% &cInvalid arguments!"
  injection-failure: "%prefix% &cInjection failure!"
  update-found: "%prefix% &aAn update was found!"
  null-address: "%prefix% &cYou are joining with an invalid address!"

  alerts:
    permission: "lpx.alerts"
    format: "%prefix% %second-color%%player% &7failed %main-color%%check% %type% &7(%vl%/%max-vl%)"
    hover:
      - "%main-color%Description:"
      - "%second-color%%description%"
      - ""
      - "%main-color%Infos: %infos%"
      - ""
    enabled: ""
    disabled: "%prefix% &cAlerts disabled"

options:
  # Enable this only if you have fake players who cause errors during the injection
  # WARNING: Enabling this will allow players to join even during injection failures
  silent-failures: false

  # For some reasons packets could be still received even if the player is not online
  # Enable this if you are having crashes even if the player is kicked
  discard-offline-packets: false

  # If this option is set to true, players won't be able to see the output of /lpx
  hidden-command: false

  # If activated, players with "lpx.bypass" permission will ignore checks
  bypass-permission: false

  # Add support for Geyser players (Bedrock Edition)
  geyser: false

  # Check if the plugin can be updated.
  # Permission: "lpx.update"
  check-updates: true

  # Whether bStats should be loaded (https://bstats.org/plugin/bukkit/LPX/9156)
  bstats: true

  # Whether task that resets VL should be enabled
  clear-task:
    enabled: false
    # Repeat delay in seconds
    delay: 300

  printer:
    # Enable this if your server allows the use of printer/schematic mod, and you are not using our Printer's APIs
    automatic: false
    # Lower this value if players don't enter in printer mode correctly
    place-threshold: 10
    # Idle time after exiting printer mode
    disable-delay: 3000
    # Whether players with the permission should receive printer's alerts
    alerts: true
    # Permission to receive printer's alerts
    permission: "lpx.alerts.printer"
    join: "%prefix% %second-color%%player% &7joined printer mode (%mode%)"
    leave: "%prefix% %second-color%%player% &7left printer mode"

  mechanics:
    # Sets a minimum time to reuse the nether portal. You can set it to -1 to disable.
    # WARNING: If you are using Intave put this to -1 to disable
    nether-portal-delay: 1000
    # Prevents the oneshot bow. -1 to disable
    max-arrow-velocity: 15
    # Prevents sheep extinction. -1 to disable
    shears-cooldown: 500
    # Prevents players to interact with the inventory on block break
    break-close-inventory: false

  # Server name, used for API integrations
  server: unnamed

  # Delay in milliseconds to wait before sending new alerts after a punishment
  punish-delay: 1000

  debug: false

  # If set to true LPX will look for the config.yml in ../config/config.yml
  external-config: false

packet-logger:
  enabled: false

  # Players ignored
  whitelist:
    - Ytnoos

  # List of packets to ignore
  # To find out correct names, open spigot's jar and find class' names
  # Path: net.minecraft.server
  ignore:
    - PacketPlayInFlying
    - PacketPlayInKeepAlive
    - PacketPlayInArmAnimation
    - PacketPlayInTransaction

  # Max files which can be created in a run (newer files will replace older once reached this limit)
  max-files: 50
  # Max packets to log on each file
  max-ppfs: 3000
  # Days before old folders can be automatically deleted
  old-folders: 3

checks:
  netty:
    a:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        # If this is set to automatic, then the max value below will assume one of these values based on your server version
        # 1.8 = 6144
        # 1.12 = 16384
        # 1.13 = 65536
        automatic: true
        # You can put this value to lower numbers (4096, 8192, 12228) to have much stricter protections
        max: 65536
    b:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        resolved: true
        min-length: 96
        max: 15
        max-characters: 255
        resize: true
  window:
    a:
      enabled: true
      punish: true
      max-vl: 5
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      buffer:
        max: 3
        multiply: 0.25
        decay: 1
    b:
      enabled: true
      punish: true
      max-vl: 5
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      buffer:
        max: 3
        multiply: 0.25
        decay: 1
    c:
      enabled: true
      punish: true
      max-vl: 5
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
    d:
      enabled: true
      punish: true
      max-vl: 2
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
  creative:
    a:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
    b:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        max: 127
        min: 0
    c:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        max: 256
    d:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        max: 2048
    e:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        blacklist:
          - "run_command"
          - "translation.test.invalid"
    f:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        max: 64
    g:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
  place:
    a:
      enabled: true
      punish: true
      max-vl: 30
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      buffer:
        max: 5
        multiply: 0.5
        decay: 1
      options:
        max: 100
    b:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        max: 70
  flood:
    a:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &cYou are sending too many packets. :<'
      options:
        max: 1000
    b:
      enabled: true
      punish: true
      max-vl: 15
      min-vl: 10
      punish-commands:
        - 'lpx kick %player% &cYou are sending too many packets. >:'
      options:
        # The following strings are represented by 2 or 3 parameters:
        # PacketName | PPS | Interval(ms)
        # "PacketPlayInArmAnimation,10,100" Means this check will flag when a player sends 10 PacketPlayInArmAnimation packets in an interval of 100ms
        limits:
          - "PacketPlayInArmAnimation,50,500"
          - "PacketPlayInUseItem,60,1000"
          - "PacketPlayInBlockPlace,14,100"
          - "PacketPlayInWindowClick,55,100"
          - "PacketPlayInSetSlot,50,1000"
          - "PacketPlayInPosition,20,100"
          - "PacketPlayInAutoRecipe,15,1000"
          - "PacketPlayInTabComplete,40,1000"
          - "PacketPlayInUseEntity,40,1000"
          - "PacketPlayInClientCommand,5,500"
          - "ServerboundChatCommandPacket,5,500"
          - "PacketPlayInBlockDig,60,500"
    c:
      enabled: true
      punish: true
      max-vl: 10
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &cYou are sending too many packets. :o'
      options:
        max: 80
    d:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &cYou are sending too many packets. o:'
      options:
        max: 13
    e:
      enabled: false
      punish: false
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &cYou are sending too many packets. $:'
      options:
        threshold: 4096
        max: 8
        reset: 1000
    f:
      enabled: true
      punish: true
      max-vl: 2
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &cYou are sending too many packets. :$'
      options:
        max: 8
  position:
    a:
      enabled: true
      punish: true
      max-vl: 1
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
    b:
      enabled: true
      punish: true
      max-vl: 6
      min-vl: 1
      buffer:
        max: 2
        multiply: 0.5
        decay: 0.05
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        delay: 2000
        hard: false
        ignore-fly: true
    c:
      enabled: true
      punish: false
      max-vl: 1
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        max: 2048
    d:
      enabled: true
      punish: true
      max-vl: 1
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        max: 100000
  payload:
    a:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
    b:
      enabled: true
      punish: true
      max-vl: 2
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        delay: 1000
        max: 15
    c:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
    d:
      enabled: true
      punish: true
      max-vl: 5
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
    e:
      enabled: true
      punish: true
      max-vl: 1
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
  tab:
    a:
      enabled: true
      punish: true
      max-vl: 10
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        starts:
          - "/to "
          - "//to"
          - "/calc "
          - "//calc"
        contains:
          - "while"
          - "targetoffset"
          - "for("
          - "^(."
          - "*."
  command:
    a:
      enabled: true
      punish: true
      max-vl: 3
      min-vl: 1
      punish-commands:
        - 'lpx kick %player% &f数据异常'
      options:
        commands: #CREDITS TO: https://github.com/2lstudios-mc/ExploitFixer
          # WorldEdit exploit
          - "//calc"
          - "//calculate"
          - "//eval"
          - "//evaluate"
          - "//solve"
          # HolographicDisplays exploit
          - "/hd readtext"
          - "/holo readtext"
          - "/hologram readtext"
          - "/holograms readtext"
          - "/holographicdisplays readtext"
          # PermissionsEx exploit
          - "/pex promote"
          - "/pex demote"
          - "/promote"
          - "/demote"
          - "/execute"
          # Multiverse exploit
          - "/mv ^"
          - "/mv help ^"
          - "/mvhelp ^"
          - "/$"
