# Hack-clientpackage com.example.helloworldmod;

import net.minecraftforge.api.distmarker.Dist;
import net.minecraftforge.client.event.ClientChatEvent;
import net.minecraftforge.event.entity.player.PlayerEvent;
import net.minecraftforge.eventbus.api.SubscribeEvent;
import net.minecraftforge.fml.common.Mod;
import net.minecraftforge.fml.event.lifecycle.FMLClientSetupEvent;
import net.minecraftforge.fml.event.lifecycle.FMLCommonSetupEvent;

@Mod("helloworldmod")
public class HelloWorldMod {

    public HelloWorldMod() {
        // Register setup events
    }

    @Mod.EventBusSubscriber(modid = "helloworldmod", bus = Mod.EventBusSubscriber.Bus.FORGE, value = Dist.CLIENT)
    public static class ForgeEventHandlers {
        @SubscribeEvent
        public static void onPlayerLoggedIn(PlayerEvent.PlayerLoggedInEvent event) {
            event.getPlayer().sendMessage(new net.minecraft.network.chat.TextComponent("Hello, Minecraft modding!"), event.getPlayer().getUUID());
        }
    }
}
