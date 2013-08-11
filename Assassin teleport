package me.yuzko.mc.base;

import java.util.List;

import org.bukkit.Bukkit;
import org.bukkit.ChatColor;
import org.bukkit.Location;
import org.bukkit.block.Block;
import org.bukkit.entity.Entity;
import org.bukkit.entity.EntityType;
import org.bukkit.entity.Item;
import org.bukkit.entity.LivingEntity;
import org.bukkit.entity.Player;
import org.bukkit.event.Listener;
import org.bukkit.event.block.Action;
import org.bukkit.event.player.PlayerInteractEvent;
import org.bukkit.inventory.PlayerInventory;
import org.bukkit.potion.PotionEffect;
import org.bukkit.potion.PotionEffectType;

public class Assassin implements Listener
{
	public void onInteract(PlayerInteractEvent e, Player player)
	{
		Player p = e.getPlayer();
		Location l = p.getLocation();
		PlayerInventory pi = p.getInventory();
		if(pi.getHelmet().getTypeId() == 302 && pi.getChestplate().getTypeId() == 303 
				&& pi.getLeggings().getTypeId() == 304 && pi.getBoots().getTypeId() == 305)
		{
			p.setSneaking(true);
			if(e.getAction() == Action.RIGHT_CLICK_AIR)
			{

				if(p.getInventory().getItemInHand().getTypeId() == 258 || 
						p.getInventory().getItemInHand().getTypeId() == 271 ||
						p.getInventory().getItemInHand().getTypeId() == 275 ||
						p.getInventory().getItemInHand().getTypeId() == 279 ||
						p.getInventory().getItemInHand().getTypeId() == 286){

					Block targetBlock = p.getTargetBlock(null, 50);
					Location blockLoc = targetBlock.getLocation();
					double bx = blockLoc.getX(); 
					double by = blockLoc.getY();
					double bz = blockLoc.getZ();
					List<Entity> nearby = p.getNearbyEntities(100, 100, 100);
					for (Entity entity : nearby)
					{
						if(entity instanceof LivingEntity)
						{
							Location loc = entity.getLocation();
							double ex = loc.getX();
							double ey = loc.getY();
							double ez = loc.getZ();

							if((bx - 1.5 <= ex && ex <= bx + 2) && (bz - 1.5 <= ez && ez <= bz + 2))
							{
								p.teleport(entity);
							}
						}

					}
				}
			}
			else 
				if(e.getAction() == Action.RIGHT_CLICK_AIR)
				{
					if(p.getInventory().getItemInHand().getTypeId() == 290 || 
							p.getInventory().getItemInHand().getTypeId() == 291 ||
							p.getInventory().getItemInHand().getTypeId() == 292 ||
							p.getInventory().getItemInHand().getTypeId() == 293 ||
							p.getInventory().getItemInHand().getTypeId() == 294){
						p.addPotionEffect(new PotionEffect(PotionEffectType.SPEED, 120, 3));
						p.sendMessage(ChatColor.BLUE + "#Ability: " + ChatColor.YELLOW + "You used " + ChatColor.GOLD + "Rush");

					}
				}
				else
					if(e.getAction() == Action.RIGHT_CLICK_AIR)
					{
						if(p.getInventory().getItemInHand().getTypeId() == 267 || 
								p.getInventory().getItemInHand().getTypeId() == 268 ||
								p.getInventory().getItemInHand().getTypeId() == 272 ||
								p.getInventory().getItemInHand().getTypeId() == 276 ||
								p.getInventory().getItemInHand().getTypeId() == 283)
						{
							for (Player players : Bukkit.getOnlinePlayers())
                            {
                                p.addPotionEffect(new PotionEffect(PotionEffectType.INVISIBILITY, 60, 3));
                                p.sendMessage(ChatColor.BLUE + "#Ability:" + ChatColor.YELLOW + " You used " + ChatColor.GOLD + "Hidden");
                            }
						}
					}

		}
	}

}
