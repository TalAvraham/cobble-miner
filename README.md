# CobbleMiner
Plug & Play minecraft bot for Hypixel Skyblock server, to generate in-game currency with a cobblestone generator.  
Uses 'Macro/Keybinds' mod for minecraft, mod configuration is below.

## KeyBinds Configuration:

###### Start / stop:
$${ SET(@#store_delay,0) }$$ $${ UNSET(@auto_return) }$$ $${ EXEC("CobbleMiner.txt","CobbleMiner") }$$

###### Print stats:
$${ @#print_stats = 1 }$$ $${$$<CobbleStats.txt>}$$ $${ @#print_stats = 0 }$$

###### Stats reset:
$${EXEC("StatsReset.txt","StatsReset")}$$

###### Refresh:
$${SET(@auto_return)}$$ $${SET(@running)}$$ $${EXEC("Refresh.txt","Refresh")}$$

###### Config:
$${EXEC("Config.txt","Config")}$$


## Events KeyBinds Configuration:

###### OnJoinGame:
$${LOG("Joined server.")}$$ $${EXEC("Config.txt","Config")}$$ $${SET(@auto_return)}$$ $${EXEC("ReturnToWork.txt","ReturnToWork")}$$

###### OnChat:
$${$$<ScanChat.txt>}$$

###### OnWorldChange:
$${EXEC("ReturnToWork.txt","ReturnToWork")}$$
