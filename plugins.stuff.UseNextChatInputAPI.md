---
title: ChatInput API
layout: default
permalink: plugins/stuff/chatinput/
parent: Stuff
grand_parent: Plugins
nav_order: 2
---

# Stuff API: NextChatInput
```java
new UseNextChatInput((Player) e.getWhoClicked())
    .sendMessage("Schreibe den Neuen Namen für das Telepad in den Chat.<br>Schreibe \"exit\" zum abzubrechen.")
    .setChatEvent((player, message) -> {
    if (message.equalsIgnoreCase("exit")) {
        player.sendMessage("Vorgang abgebrochen");
        return;
    }
    Pattern ptm = Pattern.compile("[a-zA-Z0-9_ ]{3,32}");
    if(ptm.matcher(message).matches()) {
      // folgt dem formate
    } else {
      // folgt nicht dem format
    }
    })
    .capture();
```
Diese methode kan auch innerhalb von PlaceBlock- und ClickEvents´s genutz werden.<br>
Beispiel.:
```java
private static void changeNameI(InventoryClickEvent e) {
    MiniMessage mm = MiniMessage.miniMessage();
    Telepads telepads = Telepads.INSTANCE;
    DataBasePool db = telepads.basePool;
    e.getWhoClicked().closeInventory();
    TelepadGui gui = (TelepadGui) e.getInventory().getHolder(false);
    new UseNextChatInput((Player) e.getWhoClicked())
        .sendMessage("Schreibe den Neuen Namen für das Telepad in den Chat.<br>Schreibe \"exit\" zum abzubrechen.")
        .setChatEvent((player, message) -> {
            if (message.equalsIgnoreCase("exit")) {
              player.sendMessage("Abgebrochen");
              return;
             }
            
            Pattern ptm = Pattern.compile("[a-zA-Z0-9_ ]{3,32}");
            if(ptm.matcher(message).matches()) {
                DataBasePool.setName(db, gui.id, message);
                player.sendMessage(mm.deserialize("Der name \"<green><name></green>\" wurde für dieses Telepad gesetzt.",
                Placeholder.component("name", Component.text(message))));
            } else {
                player.sendMessage(mm.deserialize("<red>Ungültiger Name.<br>Dein Name muss [a-zA-Z0-9_ ] folgen und muss zwischen 3 und 32 Zeichen lang sein.</red>"));
            }
        })
        .capture();
}
```
