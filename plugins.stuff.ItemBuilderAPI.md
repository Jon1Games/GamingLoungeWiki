---
title: ItemBuilder
layout: default
permalink: plugins/stuff/itembuilderapi/
parent: Stuff
grand_parent: Plugins
nav_order: 1
---

# Stuff API: ClickEvent
```java
public class ClassName implements InventoryHolder{

    static ClickEvent event = ClassName::eventI;

    Inventory inventory;
	
    public ClassName() {
	
        this.inventory = Bukkit.createInventory(this, (row * 9), Component.Text(); // row = anzahl der reihen des Inventars (1-6)

        Stuff.INSTANCE.itemBuilderManager.addClickEvent(changeName, "Plugin:EventName");
		
        telepadGui.setItem(
            1, // Item index
            new ItemBuilder()
                // Weitere Argumente
                .build()
        );

    }

    private static void event(InventoryClickEvent e) {
        // event Code
    }

}
```
