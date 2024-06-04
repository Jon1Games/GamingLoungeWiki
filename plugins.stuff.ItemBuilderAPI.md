---
title: ItemBuilder API
layout: default
permalink: plugins/stuff/itembuilderapi/
parent: Stuff
grand_parent: Plugins
nav_order: 1
---

# Stuff API: ClickEvent
```java
public class ClassName implements InventoryHolder{

	public static final ClickEvent event = ClassName::eventI;

	Inventory inventory;
	
	public ClassName() {
	
		this.inventory = Bukkit.createInventory(this, (row * 9), Component.Text();
							    // row = anzahl der reihen des Inventars (1-6)
	
		Stuff.INSTANCE.itemBuilderManager.addClickEvent(changeName, "Plugin:EventName");
			
		telepadGui.setItem(
			1, // Item index
			new ItemBuilder()
				// Weitere Argumente
				.whenClicked("Plugin:EventName")
				.build()
		);

	}

	private static void eventI(InventoryClickEvent e) {
		// event Code
	}
	
	@Override
	public @NotNull Inventory getInventory() {
		return inventory;
	}

}
```
# Stuff API: PlaceEvent
```java
public class ClassName implements InventoryHolder{
	
	public static final PlaceEvent event = ClassName::eventI;
	
	Inventory inventory;
	
	public ClassName() {
	
		this.inventory = Bukkit.createInventory(this, (row * 9), Component.Text();
							    // row = anzahl der reihen des Inventars (1-6)

		Stuff.INSTANCE.itemBuilderManager.addPlaceEvent(changeName, "Plugin:EventName");
		
		telepadGui.setItem(
			1, // Item index
			new ItemBuilder()
				// Weitere Argumente
				.whenClicked("Plugin:EventName")
				.build()
			);
		
		}

	private static void eventI(BlockPlaceEvent e) {
		// event Code
	}
	
	@Override
	public @NotNull Inventory getInventory() {
		return inventory;
	}

}
```
## Argumente

**Wichtig** Setze das Material des Items, wird das Item Material nicht gesetzt wird ein Error ausgegeben. 
```java
.setMaterial(Material.Item_Material)
```
set Name nimmt einen Minimessage Component oder einen String,<br>
Der string wird zu einem Minimessage Component wobei dieser Text nicht wie normal Schräg geschrieben ist.
```java
.setName(String)
```
```java
.setName(Component)
```
Gibt dem Item ein Endchantment welches normaler weiße in Vanilla nicht möglich ist und versteckt alle Atribute.
```java
.setGlint(boolean)
```
### Lore
Diese methode nimmt einen Component Liste und setzt diese als Lore.
```java
List<Component> lore = new ArrayList<>();
lore.add(Component);
.setLore(lore)
```
Bei dieser Methode kan ein String oder ein Component,<br>
Der string wird zu einem Minimessage Component wobei dieser Text nicht wie normal Schräg geschrieben ist.
```java
.addLore(String)
```
```java
.addLore(Component)
```
