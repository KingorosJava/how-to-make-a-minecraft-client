## Tutorial

### Prerequisites

Before getting started, make sure you have the following sources downloaded:

- MCP: [Download MCP 918](http://www.modcoderpack.com/files/mcp918.zip)
- Optifine: [Download Optifine 1.8.9 HD U M5](https://optifinesource.co.uk/downloads/1.8)
- JDK 8: [Download JDK 8](https://www.oracle.com/uk/java/technologies/javase/javase8-archive-downloads.html)
- Eclipse IDE: [Download Eclipse IDE](https://www.eclipse.org/downloads/)
- My discordRP class: [Download DiscordRP.java](https://cdn.discordapp.com/attachments/1095390541778276434/1116091907450339439/DiscordRP.java)

### Instructions

- Once all sources are downloaded, make a folder on your Desktop called "<name>-client".
- Extract "mcp918.zip" into that folder, and run decompile.bat to decompile Minecraft.
- Once the decompile process is done, open Eclipse and select the "eclipse" folder inside the client's folder (<name>-client).
- Delete the "Server" package and open the client package.
- Try starting Minecraft by pressing the run button.
- If it starts, make a new package called "me.<your-name>.<client-name>".
- Then create a class in that package named <client-name>, and go into that class.
- Add the following basic startup and shutdown code:

```java
package me.name.example; // change this

import example.Discord.DiscordRP;
import example.gui.SplashProgress;
import net.minecraft.client.Minecraft;

public class Pluto {
	public String name = "example";
	public int version = (int) 0.1;
	public Minecraft mc = Minecraft.getMinecraft();
	public static final Pluto INSTANCE = new Pluto();
	public static final Pluto getInstance() { return INSTANCE; }
	private DiscordRP DiscordRP = new DiscordRP();
	
	public void init() {
		DiscordRP.start();
	}
	
	public void shutdown() {
		DiscordRP.shutdown();
	}
	
	public DiscordRP getDiscordRP() {
		return DiscordRP;
	}
}```
- Call the startup of your client in the file "Minecraft.java" where the game is started (find it with Ctrl + Shift + R).
- Add the following code in different places where you want DiscordRP to update:
```java
  Pluto.getInstance().getDiscordRP().update("Playing Singleplayer", "In Game");
```
