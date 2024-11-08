# TryingToOptimizeMC_1.20.1

You read the title, so here are some tips on how to optimize performance in Minecraft 1.20.1

Results
=

My specs are

 - GPU: Intel uhd 600 (integrated gpu)
 - CPU: Intel celeron N4020
 - RAM: 4gb 2400mhz

As you can see my pc is very bad, but with these tweaks i got around 100 FPS

![2024-01-26_21 16 42](https://github.com/BlooCantCodeBruh/TryingToOptimizeMC/assets/139488947/6c5d627c-4e9f-4c2f-a659-8a45679a42ea)

Optimizing Java
=
### Allocating RAM

For modern versions, 2-8gb seems to be enough, keep in mind to have some memory left over for your OS

To add more ram in Minecraft launcher:
 1. Go to installations
 2. Hover over your installations and click on the three dots
 3. Click on edit
 4. Click on more options
 5. Find -Xmx2G
 6. Change the number to how much ram you want to allocate

Most clients or launchers have memory allocation in settings or installation settings

### How much should I allocate with how many mods i have?

 If you have elss than 4 gb of ram, if you have more than that refrain from going above 4-6 gb since setting it really high doesn't really do anything because most of it is unused

### Choosing a Java Runtime 

**This will only work with launchers like Prism and MultiMC, This doesnt work on vanilla launcher or clients(lunar already does it for you)**

This tweak will reduce stutters, but also will increase RAM + CPU usage, and small fps gain at best.

For 1.12.2 below require java 8, above require Java 17

Here are 2 runtimes you can choose from, both are Java 17

### Oracle GraalVM Enterprise Edition

[Download](https://www.oracle.com/java/technologies/downloads/#graalvmjava17-windows)

### Azul's Prime OpenJDK (linux only and incompatible with some mods)

[Download](https://www.azul.com/downloads/#prime)

For more info go to [Here](https://github.com/brucethemoose/Minecraft-Performance-Flags-Benchmarks)

### Flags

These Flags run with any Java 11+ build

```-XX:+UnlockExperimentalVMOptions -XX:+UnlockDiagnosticVMOptions -XX:+AlwaysActAsServerClassMachine -XX:+AlwaysPreTouch -XX:+DisableExplicitGC -XX:+UseNUMA -XX:NmethodSweepActivity=1 -XX:ReservedCodeCacheSize=400M -XX:NonNMethodCodeHeapSize=12M -XX:ProfiledCodeHeapSize=194M -XX:NonProfiledCodeHeapSize=194M -XX:-DontCompileHugeMethods -XX:MaxNodeLimit=240000 -XX:NodeLimitFudgeFactor=8000 -XX:+UseVectorCmov -XX:+PerfDisableSharedMem -XX:+UseFastUnorderedTimeStamps -XX:+UseCriticalJavaThreadPriority -XX:ThreadPriorityPolicy=1 -XX:AllocatePrefetchStyle=3 -XX:+UseZGC -XX:AllocatePrefetchStyle=1 -XX:-ZProactive```

For more info go to this repository: https://github.com/brucethemoose/Minecraft-Performance-Flags-Benchmarks

### Process priority

Process priority feature is intended for managing what processes have a higher priority for resources

Here's how to do it:

 1. Launch Minecraft
 2. Open task manager
 3. go to details
 4. Find javaw.exe
 5. go to "Set priority", and set to it to above normal

![image1.png](https://github.com/BlooCantCodeBruh/TryingToOptimizeMC/blob/main/image1/Image1.png)

Choosing a mod Loader
=

There are 3 popular modloaders to choose from:

 - Forge
 - Fabric
 - Quilt

Fabric and quilt is recommended since most newer performance mods only work on Fabric or Quilt, and works faster for most people

Forge is way older so it has more mods or modpacks, but most of the mods are on older versions

Mods
=

Mods can change how the game works, here are performance mods that can reduce lagspikes and increase FPS

**These mods only work with the Fabric and Quilt NOT forge**

Here's a download with a zipped folder with all of the mods (and libraries)

[Download](https://github.com/BlooCantCodeBruh/TryingToOptimizeMC/releases/download/v1/mcmods1.20.1.fabric.zip)

### List with all the mods

 - [BadOptimizations](https://modrinth.com/mod/badoptimizations) by Thosea
 - [betterfpsdist mod](https://www.curseforge.com/minecraft/mc-mods/better-fps-render-distance-fabric) by Someaddon
 - [C2ME](https://modrinth.com/mod/c2me-fabric) by ishland and duplexsystem
 - [Enchanced block entities](https://modrinth.com/mod/ebe) by FoundationGames
 - [EntityCulling](https://modrinth.com/mod/entityculling) by tr7zw
 - [Exordium](https://modrinth.com/mod/exordium) by tr7zw
 - [FerriteCore](https://modrinth.com/mod/ferrite-core) by malte0811
 - [FPS reducer](https://modrinth.com/mod/fps-reducer) by bre2el
 - [ImmediatelyFast](https://modrinth.com/mod/immediatelyfast) by RaphiMC
 - [kennytv's epic force close loading screen](https://modrinth.com/mod/forcecloseworldloadingscreen) by kennytv
 - [LazyDFU](https://modrinth.com/mod/lazydfu) by astei
 - [MemoryLeakFix](https://modrinth.com/mod/memoryleakfix) by FX and KingContaria
 - [Methane](https://modrinth.com/mod/methane) by AnOpenSauceDev
 - [ModernFix](https://modrinth.com/mod/modernfix) by embeddedt
 - [More Culling](https://modrinth.com/mod/moreculling) by FX
 - [Reese's Sodium options](https://modrinth.com/mod/reeses-sodium-options) by FlashyReese
 - [Sodium](https://modrinth.com/mod/sodium) by jellysquid3
 - [Sodium extra](https://modrinth.com/mod/sodium-extra) by FlashyReese

### Libraries

 - [Cloth config](https://modrinth.com/mod/cloth-config) by shedaniel
 - [Fabric API](https://modrinth.com/mod/fabric-api) by modmuss50 and sfPlayer1
 - [Fabric Language Kotlin](https://modrinth.com/mod/fabric-language-kotlin) by modmuss50 and sfPlayer1
 - [cupboard](https://www.curseforge.com/minecraft/mc-mods/cupboard) by someaddon
 - [CompleteConfig](https://www.curseforge.com/minecraft/mc-mods/completeconfig) by Lortseam_


Notes
=

Launchers like Prism and Multimc have a "update mods option", by the time you see this repository, most of the mods are outdated.

Disable sodium's entity culling in graphics settings, the mod is better than sodium's enity culling

![image](https://github.com/BlooCantCodeBruh/TryingToOptimizeMC/assets/139488947/a24d107a-b4d8-4a5d-b85c-7bec4d69aca2)



