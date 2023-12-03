_G.Config = false
_G.Settings = {

	Main = {
		["Auto Farm Level"] = false,
		["Auto Farm Quest"] = false,
		["Auto Farm Fast"] = false,
		["Auto Farm Mob Arua"] = false,

		--[World 1]
		["Auto New World"] = false,
		["Auto Saber"] = false,
		["Auto Pole"] = false,
		["Auto Buy Ablility"] = false,
		--[World 2]
		["Auto Third Sea"] = false,

		["Auto Dark Coat"] = false,
		["Auto Dark Coat Hop"] = false,

		["Auto Rengoku"] = false,
		["Auto Rengoku Hop"] = false,

		["Auto Dragon Trident"] = false,
		["Auto Dragon Trident Hop"] = false,

		["Auto Swan Glasses"] = false,
		["Auto Swan Glasses Hop"] = false,

		["Auto True Triple Katana"] = false,
		["Auto Ectoplasm"] = false,
		["Auto Evo Race V2"] = false,
		["Auto Bartilo Quest"] = false,
		["Auto Buy Legendary Sword"] = false,
		["Auto Buy Enchanment Haki"] = false,
		["Teleport to Sea Beast"] = false,


		-- [World3]

		["Auto Rainbow Haki"] = false,
		["Auto Rainbow Haki Hop"] = false,

		["Auto Musketeer Hat"] = false,
		["Auto Musketeer Hat Hop"] = false,

		["Auto Ken-Haki V2"] = false,

		["Auto Serpent Bow"] = false,
		["Auto Serpent Bow Hop"] = false,

		["Auto Elite Hunter"] = false,
		["Auto Elite Hunter Hop"] = false,

		["Auto Farm Bone"] = false,
		["Auto Random Bone"] = false,

		["Auto Cake Prince"] = false,
		["Auto Spawn Cake Prince"] = true,

		["Auto Buddy Sword"] = false,
		["Auto Buddy Sword Hop"] = false,

		["Auto Twin Hook"] = false,
		["Auto Twin Hook Hop"] = false,

		["Auto Farm Boss Hallow"] = false,
		["Auto Farm Boss Hallow Hop"] = false,

		["Auto Dark Dagger"] = false,
		["Auto Dark Dagger Hop"] = false,

		["Auto Cavander"] = false,
		["Auto Cavander Hop"] = false,

		["Auto Yama "] = false,
		["Auto Tushita"] = false,
		["Auto Cursed Dual Katana"] = false,

		["Auto Superhuman"] = false,
		["Auto Death Step"] = false,
		["Auto SharkMan Karate"] = false,
		["Auto Electric Claw"] = false,
		["Auto Dragon Talon"] = false,

		["Auto Fully SharkMan Karate"] = false,
		["Auto Fully DeathStep"] = false,
	},

	Players = {
		["Spectate Player"] = false, 
		["Teleport to Player"] = false,
		["Enabled PvP"] = false,
	},

	Stats = {
		["Auto Stats Melee"] = false,
		["Auto Stats Defense"] = false,
		["Auto Stats Sword"] = false,
		["Auto Stats Gun"] = false,
		["Auto Stats Devil Fruit"] = false,
	},

	Dungeon = {
		["Auto Buy Chip Dungeon"] = false,
		["Auto Dungeon"] = false,
		["Auto Next Island"] = false,
		["Kill Aura"] = false,
		["Auto Awake"] = false,
	},

	LawDungeon = {
		["Auto Buy Law Chip"] = false,
		["Auto Start Law Dungeon"] = false,
		["Auto Kill Law"] = false,
	},

	Fruit = {
		["Auto Buy Devil Fruit"] = false,
		["Auto Random Fruit"] = false,
		["Auto Bring Fruit"] = false,
		["Auto Store Fruit"] = false,
	},

	Esp = {
		["Esp Player"] = false,
		["Esp Island"] = false,
		["Esp Fruit"] = false,
		["Esp Flower"] = false,
		["Esp Chest"] = false,
	},

	Misc = {
		["No clip"] = false,
		["Infinit Energy"] = false,
		["Infinit CameraMaxZoom"] = false,
		["Walk on Water"] = false,
	},

	Boss = {
		["Auto Quest Boss"] = false,
		["Auto Farm Boss"] = false,
		["Auto Farm All Boss"] = true,
	},

	Mastery = {
		["Auto Farm Fruit Mastery"] = false,
		["Auto Farm Gun Mastery"] = false,
	},

	Configs = {
		["Disabled Damage Text"] = false,
		["Double Quest"] = false,
		["Bypass TP"] = false,
		["Disabled Damage"] = false,

		["Fast Attack"] = true,
		["Bring Mob"] = true,
		["Auto Rejoin"] = true,

		--[Skill Configs]
		["Skill Z"] = true,
		["Skill X"] = true,
		["Skill C"] = true,
		["Skill V"] = true,
	},
}

if _G.Config then
	if _G.Settings.Main["Auto Farm Level"] then
		_G.Auto_Farm_Level = true
	end
	if _G.Settings.Main["Auto Farm Quest"] then
		_G.Auto_Farm_Quest = true
	end
	if _G.Settings.Main["Auto Farm Fast"] then
		_G.Auto_Farm_Fast = true
	end
	if _G.Settings.Main["Auto Farm Mob Aura"] then
		_G.Auto_Farm_Mob_Aura = true
	end

	-- [World1] --

	if _G.Settings.Main["Auto New World"] then
		_G.Auto_New_World = true
	end

	-- [Other Function]

	if _G.Settings.Main["Auto Saber"] then
		_G.Auto_Saber = true
	end

	if _G.Settings.Main["Auto Pole"] then
		_G.Auto_Pole = true
	end

	if _G.Settings.Main["Auto Buy Ablility"] then
		_G.Auto_Buy_Ablility = true
	end

	-- [World2] --

	if _G.Settings.Main["Auto Third World"] then
		_G.Auto_Third_World = true
	end

	if _G.Settings.Main["Auto Rengoku"] then
		_G.Auto_Rengoku = true
	end

	if _G.Settings.Main["Auto Rengoku Hop"] then
		_G.Auto_Rengoku_Hop = true
	end

	if _G.Settings.Main["Auto Dragon Trident"] then
		_G.Auto_Dragon_Trident = true
	end

	if _G.Settings.Main["Auto Dragon Trident Hop"] then
		_G.Auto_Dragon_Trident_Hop = true
	end

	if _G.Settings.Main["Auto Dark Coat"] then
		_G.Auto_Dark_Coat = true
	end

	if _G.Settings.Main["Auto Dark Coat Hop"] then
		_G.Auto_Dark_Coat_Hop = true
	end

	if _G.Settings.Main["Auto Swan Glasses"] then
		_G.Auto_Swan_Glasses = true
	end

	if _G.Settings.Main["Auto Swan Glasses Hop"] then
		_G.Auto_Swan_Glasses_Hop = true
	end

	-- [Other Function] -- World2

	if _G.Settings.Main["Auto Bartilo Quest"] then
		_G.Auto_Bartilo_Quest = true
	end

	if _G.Settings.Main["Auto Ectoplasm"] then
		_G.Auto_Ectoplasm = true
	end

	if _G.Settings.Main["Auto Evo Race V2"] then
		_G.Auto_Evo_Race_V2 = true
	end

	if _G.Settings.Main["Auto True Triple Katana"] then
		_G.Auto_True_Triple_Katana = true
	end

	if _G.Settings.Main["Auto Buy Legendary Sword"] then
		_G.Auto_Buy_Legendary_Sword = true
	end

	if _G.Settings.Main["Auto Buy Enchanment Haki"] then
		_G.Auto_Buy_Enchanment_Haki = true
	end

	-- [World3] -- index Function

	if _G.Settings.Main["Auto Elite Hunter"] then
		_G.Auto_Elite_Hunter = true
	end

	if _G.Settings.Main["Auto Elite Hunter Hop"] then
		_G.Auto_Elite_Hunter_Hop = true
	end

	if _G.Settings.Main["Auto Farm Bone"] then
		_G.Auto_Farm_Bone = true
	end

	if _G.Settings.Main["Auto Random Bone"] then
		_G.Auto_Random_Bone = true
	end

	if _G.Settings.Main["Auto Cake Prince"] then
		_G.Auto_Cake_Prince = true
	end

	if _G.Settings.Main["Auto Spawn Cake Prince"] then
		_G.Auto_Spawn_Cake_Prince = true
	end

	-- [Sworld] -- World3

	if _G.Settings.Main["Auto Buddy Sword"] then
		_G.Auto_Buddy_Sword = true
	end

	if _G.Settings.Main["Auto Buddy Sword Hop"] then
		_G.Auto_Buddy_Sword_Hop = true
	end

	if _G.Settings.Main["Auto Farm Boss Hallow"] then
		_G.Auto_Farm_Boss_Hallow = true
	end

	if _G.Settings.Main["Auto Farm Boss Hallow Hop"] then
		_G.Auto_Farm_Boss_Hallow_Hop = true
	end

	if _G.Settings.Main["Auto Twin Hook"] then
		_G.Auto_Twin_Hook = true
	end

	if _G.Settings.Main["Auto Twin Hook Hop"] then
		_G.Auto_Twin_Hook_Hop = true
	end

	if _G.Settings.Main["Auto Cavander"] then
		_G.Auto_Cavander = true
	end

	if _G.Settings.Main["Auto Cavander Hop"] then
		_G.Auto_Cavander_Hop = true
	end

	if _G.Settings.Main["Auto Yama"] then
		_G.Auto_Yama = true
	end

	if _G.Settings.Main["Auto Tushita"] then
		_G.Auto_Tushita = true
	end

	if _G.Settings.Sword["Auto Cursed Dual Katana"] then
		_G.Auto_Cursed_Dual_Katana = true
	end

	if _G.Settings.Main["Auto Serpent Bow"] then
		_G.Auto_Serpent_Bow = true
	end

	if _G.Settings.Main["Auto Serpent Bow Hop"] then
		_G.Auto_Serpent_Bow_Hop = true
	end

	if _G.Settings.Main["Auto Dark Dagger"] then
		_G.Auto_Dark_Dagger = true
	end

	if _G.Settings.Main["Auto Dark Dagger Hop"] then
		_G.Auto_Dark_Dagger_Hop = true
	end

	if _G.Settings.Main["Auto Rainbow Haki"] then
		_G.Auto_Rainbow_Haki = true
	end

	if _G.Settings.Main["Auto Rainbow Haki Hop"] then
		_G.Auto_Rainbow_Haki_Hop = true
	end

	if _G.Settings.Main["Auto Musketeer Hat"] then
		_G.Auto_Musketeer_Hat = true
	end

	if _G.Settings.Main["Auto Musketeer Hat Hop"] then
		_G.Auto_Musketeer_Hat_Hop = true
	end

	if _G.Settings.Main["Auto Musketeer Hat Hop"] then
		_G.Auto_Musketeer_Hat_Hop = true
	end

	if _G.Settings.Main["Auto Ken-Haki V2"] then
		_G.Auto_Ken_Haki_V2 = true
	end

	-- [Boss] --

	if _G.Settings.Boss["Auto Farm Boss"] then
		_G.Auto_Farm_Boss = true
	end

	if _G.Settings.Boss["Auto Quest Boss"] then
		_G.Auto_Quest_Boss = true
	end

	if _G.Settings.Boss["Auto Farm All Boss"] then
		_G.Auto_Farm_All_Boss = true
	end

	-- [Mastery] --

	if _G.Settings.Mastery["Auto Farm Fruit Mastery"] then
		_G.Auto_Farm_BF_Mastery = true
	end

	if _G.Settings.Mastery["Auto Farm Gun Mastery"] then
		_G.Auto_Farm_Gun_Mastery = true
	end
	-- [Fighting Style] --

	if _G.Settings.Main["Auto Superhuman"] then
		_G.AutoSuperhuman = true
	end

	if _G.Settings.Main["Auto Death Step"] then
		_G.AutoDeathStep = true
	end

	if _G.Settings.Main["Auto SharkMan Karate"] then
		_G.AutoSuperhuman = true
	end

	-- [Fully Fighting Style] --

	if _G.Settings.Main["Auto Fully SharkMan Karate"] then
		_G.Auto_Fully_SharkMan_Karate = true
	end

	if _G.Settings.Main["Auto Fully DeathStep"] then
		_G.Auto_Fully_DeathStep = true
	end

	-- [Fighting Style] --

	if _G.Settings.Main["Auto Electric Claw"] then
		_G.Auto_Electric_Claw = true
	end

	if _G.Settings.Main["Auto Dragon Talon"] then
		_G.Auto_Dragon_Talon = true
	end

	-- [set up function] -- 

	if _G.Settings.Configs["Disabled Damage Text"] then
		_G.Disabled_Damage_Text = true
	end

	if _G.Settings.Configs["Fast Attack"] then
		_G.FastAttack = true
	end

	if _G.Settings.Configs["Bring Mob"] then
		_G.Bring_Mob = true
	end

	if _G.Settings.Configs["Disabled Damage"] then
		_G.DisnableDame = true
	end

	if _G.Settings.Configs["Auto Rejoin"] then
		_G.AutoRejoin = true
	end

	if _G.Settings.Configs["Skill Z"] then
		_G.Skill_Z = true
	end

	if _G.Settings.Configs["Skill X"] then
		_G.Skill_X = true
	end

	if _G.Settings.Configs["Skill C"] then
		_G.Skill_C = true
	end

	if _G.Settings.Configs["Skill V"] then
		_G.Skill_V = true
	end
	------------------------------------------------------------------
	-- [Players] -- 

	if _G.Settings.Players["Spectate Player"] then
		_G.Spectate_Player = true
	end

	if _G.Settings.Players["Teleport to Player"] then
		_G.Teleport_to_Player = true
	end

	if _G.Settings.Players["Enabled PvP"] then
		_G.Enabled_PvP = true
	end

	-- [Stats] -- 
	if _G.Settings.Players["Auto Stats Melee"] then
		_G.Auto_Stats_Melee = true
	end

	if _G.Settings.Players["Auto Stats Defense"] then
		_G.Auto_Stats_Defense = true
	end

	if _G.Settings.Players["Auto Stats Sword"] then
		_G.Auto_Stats_Sword = true
	end

	if _G.Settings.Players["Auto Stats Gun"] then
		_G.Auto_Stats_Gun = true
	end

	if _G.Settings.Players["Auto Stats Devil Fruit"] then
		_G.Auto_Stats_Devil_Fruit = true
	end

	------------------------------------------------------------------

	-- [Dungeon] -- 

	if _G.Settings.Dungeon["Auto Buy Chip Dungeon"] then
		_G.Auto_Buy_Chip_Dungeon = true
	end

	if _G.Settings.Dungeon["Auto Dungeon"] then
		_G.Auto_Start_Dungeon = true
	end

	if _G.Settings.Dungeon["Auto Next Island"] then
		_G.Auto_Next_Island = true
	end

	if _G.Settings.Dungeon["Kill Aura"] then
		_G.Kill_Aura = true
	end

	if _G.Settings.Dungeon["Auto Awake"] then
		_G.Auto_Awake = true
	end

	------------------------------------------------------------------

	-- [Law Dungeon] --

	if _G.Settings.LawDungeon["Auto Buy Law Chip"] then
		_G.Auto_Buy_Law_Chip = true
	end

	if _G.Settings.LawDungeon["Auto Start Law Dungeon"] then
		_G.Auto_Start_Law_Dungeon = true
	end

	if _G.Settings.LawDungeon["Auto Kill Law"] then
		_G.Auto_Kill_Law = true
	end
	------------------------------------------------------------------

	-- [Esp] --

	if _G.Settings.LawDungeon["Esp Player"] then
		_G.EspPlayer = true
	end

	if _G.Settings.LawDungeon["Esp Island"] then
		_G.EspIsland = true
	end

	if _G.Settings.LawDungeon["Esp Fruit"] then
		_G.EspFruit = true
	end

	if _G.Settings.LawDungeon["Esp Flower"] then
		_G.EspFlower = true
	end

	if _G.Settings.LawDungeon["Esp Chest"] then
		_G.EspChest = true
	end

	------------------------------------------------------------------

	-- [Misc] --

	if _G.Settings.LawDungeon["No clip"] then
		_G.No_clip = true
	end

	if _G.Settings.LawDungeon["Infinit Energy"] then
		_G.Infinit_Energy = true
	end

	if _G.Settings.LawDungeon["Infinit CameraMaxZoom"] then
		_G.CameraMaxZoom = true
	end

	if _G.Settings.LawDungeon["Walk on Water"] then
		_G.WalkWater = true
	end

end

if _G.Config then
	if _G.Settings.Main["Auto Farm Level"] then
		_G.Auto_Farm_Level = true
	end
	if _G.Settings.Main["Auto Farm Quest"] then
		_G.Auto_Farm_Quest = true
	end
	if _G.Settings.Main["Auto Farm Fast"] then
		_G.Auto_Farm_Fast = true
	end
	if _G.Settings.Main["Auto Farm Mob Aura"] then
		_G.Auto_Farm_Mob_Aura = true
	end

	-- [World1] --

	if _G.Settings.Main["Auto New World"] then
		_G.Auto_New_World = true
	end

	-- [Other Function]

	if _G.Settings.Main["Auto Saber"] then
		_G.Auto_Saber = true
	end

	if _G.Settings.Main["Auto Pole"] then
		_G.Auto_Pole = true
	end

	if _G.Settings.Main["Auto Buy Ablility"] then
		_G.Auto_Buy_Ablility = true
	end

	-- [World2] --

	if _G.Settings.Main["Auto Third World"] then
		_G.Auto_Third_World = true
	end

	if _G.Settings.Main["Auto Rengoku"] then
		_G.Auto_Rengoku = true
	end

	if _G.Settings.Main["Auto Rengoku Hop"] then
		_G.Auto_Rengoku_Hop = true
	end

	if _G.Settings.Main["Auto Dragon Trident"] then
		_G.Auto_Dragon_Trident = true
	end

	if _G.Settings.Main["Auto Dragon Trident Hop"] then
		_G.Auto_Dragon_Trident_Hop = true
	end

	if _G.Settings.Main["Auto Dark Coat"] then
		_G.Auto_Dark_Coat = true
	end

	if _G.Settings.Main["Auto Dark Coat Hop"] then
		_G.Auto_Dark_Coat_Hop = true
	end

	if _G.Settings.Main["Auto Swan Glasses"] then
		_G.Auto_Swan_Glasses = true
	end

	if _G.Settings.Main["Auto Swan Glasses Hop"] then
		_G.Auto_Swan_Glasses_Hop = true
	end

	-- [Other Function] -- World2

	if _G.Settings.Main["Auto Bartilo Quest"] then
		_G.Auto_Bartilo_Quest = true
	end

	if _G.Settings.Main["Auto Ectoplasm"] then
		_G.Auto_Ectoplasm = true
	end

	if _G.Settings.Main["Auto Evo Race V2"] then
		_G.Auto_Evo_Race_V2 = true
	end

	if _G.Settings.Main["Auto True Triple Katana"] then
		_G.Auto_True_Triple_Katana = true
	end

	if _G.Settings.Main["Auto Buy Legendary Sword"] then
		_G.Auto_Buy_Legendary_Sword = true
	end

	if _G.Settings.Main["Auto Buy Enchanment Haki"] then
		_G.Auto_Buy_Enchanment_Haki = true
	end

	if _G.Settings.Main["Teleport to Sea Beast"] then
		_G.Teleport_to_Sea_Beast = true
	end

	-- [World3] -- index Function

	if _G.Settings.Main["Auto Elite Hunter"] then
		_G.Auto_Elite_Hunter = true
	end

	if _G.Settings.Main["Auto Elite Hunter Hop"] then
		_G.Auto_Elite_Hunter_Hop = true
	end

	if _G.Settings.Main["Auto Farm Bone"] then
		_G.Auto_Farm_Bone = true
	end

	if _G.Settings.Main["Auto Random Bone"] then
		_G.Auto_Random_Bone = true
	end

	if _G.Settings.Main["Auto Cake Prince"] then
		_G.Auto_Cake_Prince = true
	end

	if _G.Settings.Main["Auto Spawn Cake Prince"] then
		_G.Auto_Spawn_Cake_Prince = true
	end

	-- [Sworld] -- World3

	if _G.Settings.Main["Auto Buddy Sword"] then
		_G.Auto_Buddy_Sword = true
	end

	if _G.Settings.Main["Auto Buddy Sword Hop"] then
		_G.Auto_Buddy_Sword_Hop = true
	end

	if _G.Settings.Main["Auto Farm Boss Hallow"] then
		_G.Auto_Farm_Boss_Hallow = true
	end

	if _G.Settings.Main["Auto Farm Boss Hallow Hop"] then
		_G.Auto_Farm_Boss_Hallow_Hop = true
	end

	if _G.Settings.Main["Auto Twin Hook"] then
		_G.Auto_Twin_Hook = true
	end

	if _G.Settings.Main["Auto Twin Hook Hop"] then
		_G.Auto_Twin_Hook_Hop = true
	end

	if _G.Settings.Main["Auto Cavander"] then
		_G.Auto_Cavander = true
	end

	if _G.Settings.Main["Auto Cavander Hop"] then
		_G.Auto_Cavander_Hop = true
	end

	if _G.Settings.Main["Auto Yama"] then
		_G.Auto_Yama = true
	end

	if _G.Settings.Main["Auto Tushita"] then
		_G.Auto_Tushita = true
	end

	if _G.Settings.Sword["Auto Cursed Dual Katana"] then
		_G.Auto_Cursed_Dual_Katana = true
	end

	if _G.Settings.Main["Auto Serpent Bow"] then
		_G.Auto_Serpent_Bow = true
	end

	if _G.Settings.Main["Auto Serpent Bow Hop"] then
		_G.Auto_Serpent_Bow_Hop = true
	end

	if _G.Settings.Main["Auto Dark Dagger"] then
		_G.Auto_Dark_Dagger = true
	end

	if _G.Settings.Main["Auto Dark Dagger Hop"] then
		_G.Auto_Dark_Dagger_Hop = true
	end

	if _G.Settings.Main["Auto Rainbow Haki"] then
		_G.Auto_Rainbow_Haki = true
	end

	if _G.Settings.Main["Auto Rainbow Haki Hop"] then
		_G.Auto_Rainbow_Haki_Hop = true
	end

	if _G.Settings.Main["Auto Musketeer Hat"] then
		_G.Auto_Musketeer_Hat = true
	end

	if _G.Settings.Main["Auto Musketeer Hat Hop"] then
		_G.Auto_Musketeer_Hat_Hop = true
	end

	if _G.Settings.Main["Auto Musketeer Hat Hop"] then
		_G.Auto_Musketeer_Hat_Hop = true
	end

	if _G.Settings.Main["Auto Ken-Haki V2"] then
		_G.Auto_Ken_Haki_V2 = true
	end

	-- [Boss] --

	if _G.Settings.Boss["Auto Farm Boss"] then
		_G.Auto_Farm_Boss = true
	end

	if _G.Settings.Boss["Auto Quest Boss"] then
		_G.Auto_Quest_Boss = true
	end

	if _G.Settings.Boss["Auto Farm All Boss"] then
		_G.Auto_Farm_All_Boss = true
	end

	-- [Mastery] --

	if _G.Settings.Mastery["Auto Farm Fruit Mastery"] then
		_G.Auto_Farm_BF_Mastery = true
	end

	if _G.Settings.Mastery["Auto Farm Gun Mastery"] then
		_G.Auto_Farm_Gun_Mastery = true
	end
	-- [Fighting Style] --

	if _G.Settings.Main["Auto Superhuman"] then
		_G.AutoSuperhuman = true
	end

	if _G.Settings.Main["Auto Death Step"] then
		_G.AutoDeathStep = true
	end

	if _G.Settings.Main["Auto SharkMan Karate"] then
		_G.AutoSuperhuman = true
	end

	-- [Fully Fighting Style] --

	if _G.Settings.Main["Auto Fully SharkMan Karate"] then
		_G.Auto_Fully_SharkMan_Karate = true
	end

	if _G.Settings.Main["Auto Fully DeathStep"] then
		_G.Auto_Fully_DeathStep = true
	end

	-- [Fighting Style] --

	if _G.Settings.Main["Auto Electric Claw"] then
		_G.Auto_Electric_Claw = true
	end

	if _G.Settings.Main["Auto Dragon Talon"] then
		_G.Auto_Dragon_Talon = true
	end

	-- [set up function] -- 

	if _G.Settings.Configs["Disabled Damage Text"] then
		_G.Disabled_Damage_Text = true
	end

	if _G.Settings.Configs["Fast Attack"] then
		_G.FastAttack = true
	end

	if _G.Settings.Configs["Bring Mob"] then
		_G.Bring_Mob = true
	end

	if _G.Settings.Configs["Disabled Damage"] then
		_G.DisnableDame = true
	end

	if _G.Settings.Configs["Auto Rejoin"] then
		_G.AutoRejoin = true
	end

	if _G.Settings.Configs["Skill Z"] then
		_G.Skill_Z = true
	end

	if _G.Settings.Configs["Skill X"] then
		_G.Skill_X = true
	end

	if _G.Settings.Configs["Skill C"] then
		_G.Skill_C = true
	end

	if _G.Settings.Configs["Skill V"] then
		_G.Skill_V = true
	end
	------------------------------------------------------------------
	-- [Players] -- 

	if _G.Settings.Players["Spectate Player"] then
		_G.Spectate_Player = true
	end

	if _G.Settings.Players["Teleport to Player"] then
		_G.Teleport_to_Player = true
	end

	if _G.Settings.Players["Enabled PvP"] then
		_G.Enabled_PvP = true
	end

	-- [Stats] -- 
	if _G.Settings.Players["Auto Stats Melee"] then
		_G.Auto_Stats_Melee = true
	end

	if _G.Settings.Players["Auto Stats Defense"] then
		_G.Auto_Stats_Defense = true
	end

	if _G.Settings.Players["Auto Stats Sword"] then
		_G.Auto_Stats_Sword = true
	end

	if _G.Settings.Players["Auto Stats Gun"] then
		_G.Auto_Stats_Gun = true
	end

	if _G.Settings.Players["Auto Stats Devil Fruit"] then
		_G.Auto_Stats_Devil_Fruit = true
	end

	------------------------------------------------------------------

	-- [Dungeon] -- 

	if _G.Settings.Dungeon["Auto Buy Chip Dungeon"] then
		_G.Auto_Buy_Chip_Dungeon = true
	end

	if _G.Settings.Dungeon["Auto Dungeon"] then
		_G.Auto_Start_Dungeon = true
	end

	if _G.Settings.Dungeon["Auto Next Island"] then
		_G.Auto_Next_Island = true
	end

	if _G.Settings.Dungeon["Kill Aura"] then
		_G.Kill_Aura = true
	end

	if _G.Settings.Dungeon["Auto Awake"] then
		_G.Auto_Awake = true
	end

	------------------------------------------------------------------

	-- [Law Dungeon] --

	if _G.Settings.LawDungeon["Auto Buy Law Chip"] then
		_G.Auto_Buy_Law_Chip = true
	end

	if _G.Settings.LawDungeon["Auto Start Law Dungeon"] then
		_G.Auto_Start_Law_Dungeon = true
	end

	if _G.Settings.LawDungeon["Auto Kill Law"] then
		_G.Auto_Kill_Law = true
	end
	------------------------------------------------------------------

	-- [Esp] --

	if _G.Settings.LawDungeon["Esp Player"] then
		_G.EspPlayer = true
	end

	if _G.Settings.LawDungeon["Esp Island"] then
		_G.EspIsland = true
	end

	if _G.Settings.LawDungeon["Esp Fruit"] then
		_G.EspFruit = true
	end

	if _G.Settings.LawDungeon["Esp Flower"] then
		_G.EspFlower = true
	end

	if _G.Settings.LawDungeon["Esp Chest"] then
		_G.EspChest = true
	end

	------------------------------------------------------------------

	-- [Misc] --

	if _G.Settings.LawDungeon["No clip"] then
		_G.No_clip = true
	end

	if _G.Settings.LawDungeon["Infinit Energy"] then
		_G.Infinit_Energy = true
	end

	if _G.Settings.LawDungeon["Infinit CameraMaxZoom"] then
		_G.CameraMaxZoom = true
	end

	if _G.Settings.LawDungeon["Walk on Water"] then
		_G.WalkWater = true
	end

end

if game.PlaceId == 2753915549 then
	World1 = true
elseif game.PlaceId == 4442272183 then
	World2 = true
elseif game.PlaceId == 7449423635 then
	World3 = true
end


function CheckQuest() 
	local MyLevel = game.Players.LocalPlayer.Data.Level.Value
	if World1 then
		if MyLevel == 1 or MyLevel <= 9 or _G.Select_Mob_Farm == "Bandit [Lv. 5]" then -- Bandit
			Ms = "Bandit [Lv. 5]"
			NameQuest = "BanditQuest1"
			LevelQuest = 1
			NameMon = "Bandit"
			CFrameQuest = CFrame.new(1061.66699, 16.5166187, 1544.52905, -0.942978859, -3.33851502e-09, 0.332852632, 7.04340497e-09, 1, 2.99841325e-08, -0.332852632, 3.06188177e-08, -0.942978859)
			CFrameMon = CFrame.new(1199.31287, 52.2717781, 1536.91516, -0.929782331, 6.60215846e-08, -0.368109822, 3.9077392e-08, 1, 8.06501603e-08, 0.368109822, 6.06023249e-08, -0.929782331)
			SPAWNPOINT = "Default"
		elseif MyLevel == 10 or MyLevel <= 14 or _G.Select_Mob_Farm == "Monkey [Lv. 14]" then -- Monkey
			Ms = "Monkey [Lv. 14]"
			NameQuest = "JungleQuest"
			LevelQuest = 1
			NameMon = "Monkey"
			CFrameQuest = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
			CFrameMon = CFrame.new(-1502.74609, 98.5633316, 90.6417007, 0.836947978, 0, 0.547282517, -0, 1, -0, -0.547282517, 0, 0.836947978)
			SPAWNPOINT = "Jungle"
		elseif MyLevel == 15 or MyLevel <= 29 or _G.Select_Mob_Farm == "Gorilla [Lv. 20]" then -- Gorilla
			Ms = "Gorilla [Lv. 20]"
			NameQuest = "JungleQuest"
			LevelQuest = 2
			NameMon = "Gorilla"
			CFrameQuest = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
			CFrameMon = CFrame.new(-1223.52808, 6.27936459, -502.292664, 0.310949147, -5.66602516e-08, 0.950426519, -3.37275488e-08, 1, 7.06501808e-08, -0.950426519, -5.40241736e-08, 0.310949147)
			SPAWNPOINT = "Jungle"
		elseif MyLevel == 30 or MyLevel <= 39 or _G.Select_Mob_Farm == "Pirate [Lv. 35]" then -- Pirate
			Ms = "Pirate [Lv. 35]"
			NameQuest = "BuggyQuest1"
			LevelQuest = 1
			NameMon = "Pirate"
			CFrameQuest = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
			CFrameMon = CFrame.new(-1219.32324, 4.75205183, 3915.63452, -0.966492832, -6.91238853e-08, 0.25669381, -5.21195496e-08, 1, 7.3047012e-08, -0.25669381, 5.72206496e-08, -0.966492832)
			SPAWNPOINT = "Pirate"
		elseif MyLevel == 40 or MyLevel <= 59 or _G.Select_Mob_Farm == "Brute [Lv. 45]" then -- Brute
			Ms = "Brute [Lv. 45]"
			NameQuest = "BuggyQuest1"
			LevelQuest = 2
			NameMon = "Brute"
			CFrameQuest = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
			CFrameMon = CFrame.new(-1146.49646, 96.0936813, 4312.1333, -0.978175163, -1.53222057e-08, 0.207781896, -3.33316912e-08, 1, -8.31738873e-08, -0.207781896, -8.82843523e-08, -0.978175163)
			SPAWNPOINT = "Pirate"
		elseif MyLevel == 60 or MyLevel <= 74 or _G.Select_Mob_Farm == "Desert Bandit [Lv. 60]" then -- Desert Bandit
			Ms = "Desert Bandit [Lv. 60]"
			NameQuest = "DesertQuest"
			LevelQuest = 1
			NameMon = "Desert Bandit"
			CFrameQuest = CFrame.new(897.031128, 6.43846416, 4388.97168, -0.804044724, 3.68233266e-08, 0.594568789, 6.97835176e-08, 1, 3.24365246e-08, -0.594568789, 6.75715199e-08, -0.804044724)
			CFrameMon = CFrame.new(932.788818, 6.4503746, 4488.24609, -0.998625934, 3.08948351e-08, 0.0524050146, 2.79967303e-08, 1, -5.60361286e-08, -0.0524050146, -5.44919629e-08, -0.998625934)
			SPAWNPOINT = "Desert"
		elseif MyLevel == 75 or MyLevel <= 89 or _G.Select_Mob_Farm == "Desert Officer [Lv. 70]" then -- Desert Officre
			Ms = "Desert Officer [Lv. 70]"
			NameQuest = "DesertQuest"
			LevelQuest = 2
			NameMon = "Desert Officer"
			CFrameQuest = CFrame.new(897.031128, 6.43846416, 4388.97168, -0.804044724, 3.68233266e-08, 0.594568789, 6.97835176e-08, 1, 3.24365246e-08, -0.594568789, 6.75715199e-08, -0.804044724)
			CFrameMon = CFrame.new(1580.03198, 4.61375761, 4366.86426, 0.135744005, -6.44280718e-08, -0.990743816, 4.35738308e-08, 1, -5.90598574e-08, 0.990743816, -3.51534837e-08, 0.135744005)
			SPAWNPOINT = "Desert"
		elseif MyLevel == 90 or MyLevel <= 99 or _G.Select_Mob_Farm == "Snow Bandit [Lv. 90]" then -- Snow Bandits
			Ms = "Snow Bandit [Lv. 90]"
			NameQuest = "SnowQuest"
			LevelQuest = 1
			NameMon = "Snow Bandits"
			CFrameQuest = CFrame.new(1384.14001, 87.272789, -1297.06482, 0.348555952, -2.53947841e-09, -0.937287986, 1.49860568e-08, 1, 2.86358204e-09, 0.937287986, -1.50443711e-08, 0.348555952)
			CFrameMon = CFrame.new(1370.24316, 102.403511, -1411.52905, 0.980274439, -1.12995728e-08, 0.197641045, -9.57343449e-09, 1, 1.04655214e-07, -0.197641045, -1.04482936e-07, 0.980274439)
			SPAWNPOINT = "Ice"
		elseif MyLevel == 100 or MyLevel <= 119 or _G.Select_Mob_Farm == "Snowman [Lv. 100]"  then -- Snowman
			Ms = "Snowman [Lv. 100]"
			NameQuest = "SnowQuest"
			LevelQuest = 2
			NameMon = "Snowman"
			CFrameQuest = CFrame.new(1384.14001, 87.272789, -1297.06482, 0.348555952, -2.53947841e-09, -0.937287986, 1.49860568e-08, 1, 2.86358204e-09, 0.937287986, -1.50443711e-08, 0.348555952)
			CFrameMon = CFrame.new(1370.24316, 102.403511, -1411.52905, 0.980274439, -1.12995728e-08, 0.197641045, -9.57343449e-09, 1, 1.04655214e-07, -0.197641045, -1.04482936e-07, 0.980274439)
			SPAWNPOINT = "Ice"
		elseif MyLevel == 120 or MyLevel <= 149 or _G.Select_Mob_Farm == "Chief Petty Officer [Lv. 120]" then -- Chief Petty Officer
			Ms = "Chief Petty Officer [Lv. 120]"
			NameQuest = "MarineQuest2"
			LevelQuest = 1
			NameMon = "Chief Petty Officer"
			CFrameQuest = CFrame.new(-5035.0835, 28.6520386, 4325.29443, 0.0243340395, -7.08064647e-08, 0.999703884, -6.36926814e-08, 1, 7.23777944e-08, -0.999703884, -6.54350671e-08, 0.0243340395)
			CFrameMon = CFrame.new(-4882.8623, 22.6520386, 4255.53516, 0.273695946, -5.40380647e-08, -0.96181643, 4.37720793e-08, 1, -4.37274998e-08, 0.96181643, -3.01326679e-08, 0.273695946)
			SPAWNPOINT = "MarineBase"
		elseif MyLevel == 150 or MyLevel <= 174 or _G.Select_Mob_Farm == "Sky Bandit [Lv. 150]" then -- Sky Bandit
			Ms = "Sky Bandit [Lv. 150]"
			NameQuest = "SkyQuest"
			LevelQuest = 1
			NameMon = "Sky Bandit"
			CFrameQuest = CFrame.new(-4841.83447, 717.669617, -2623.96436, -0.875942111, 5.59710216e-08, -0.482416272, 3.04023082e-08, 1, 6.08195947e-08, 0.482416272, 3.86078725e-08, -0.875942111)
			CFrameMon = CFrame.new(-4970.74219, 294.544342, -2890.11353, -0.994874597, -8.61311236e-08, -0.101116329, -9.10836206e-08, 1, 4.43614923e-08, 0.101116329, 5.33441664e-08, -0.994874597)
			SPAWNPOINT = "Sky"
		elseif MyLevel == 175 or MyLevel <= 189 or _G.Select_Mob_Farm == "Dark Master [Lv. 175]" then -- Dark Master
			Ms = "Dark Master [Lv. 175]"
			NameQuest = "SkyQuest"
			LevelQuest = 2
			NameMon = "Dark Master"
			CFrameQuest = CFrame.new(-4841.83447, 717.669617, -2623.96436, -0.875942111, 5.59710216e-08, -0.482416272, 3.04023082e-08, 1, 6.08195947e-08, 0.482416272, 3.86078725e-08, -0.875942111)
			CFrameMon = CFrame.new(-5220.58594, 430.693298, -2278.17456, -0.925375521, 1.12086873e-08, 0.379051805, -1.05115507e-08, 1, -5.52320891e-08, -0.379051805, -5.50948407e-08, -0.925375521)
			SPAWNPOINT = "Sky"
		elseif MyLevel == 190 or MyLevel <= 209 or _G.Select_Mob_Farm == "Prisoner [Lv. 190]" then
			Ms = "Prisoner [Lv. 190]"
			NameQuest = "PrisonerQuest"
			LevelQuest = 1
			NameMon = "Prisoner"
			CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
			CFrameMon = CFrame.new(5433.39307, 88.678093, 514.986877, 0.879988372, 0, -0.474995494, 0, 1, 0, 0.474995494, 0, 0.879988372)
			SPAWNPOINT = "Prison"
		elseif MyLevel == 210 or MyLevel <= 249 or _G.Select_Mob_Farm == "Dangerous Prisoner [Lv. 210]" then
			Ms = "Dangerous Prisoner [Lv. 210]"
			NameQuest = "PrisonerQuest"
			LevelQuest = 2
			NameMon = "Dangerous Prisoner"
			CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
			CFrameMon = CFrame.new(5433.39307, 88.678093, 514.986877, 0.879988372, 0, -0.474995494, 0, 1, 0, 0.474995494, 0, 0.879988372)
			SPAWNPOINT = "Prison"
		elseif MyLevel == 250 or MyLevel <= 274 or _G.Select_Mob_Farm == "Toga Warrior [Lv. 225]" then -- Toga Warrior
			Ms = "Toga Warrior [Lv. 250]"
			NameQuest = "ColosseumQuest"
			LevelQuest = 1
			NameMon = "Toga Warrior"
			CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
			CFrameMon = CFrame.new(-1779.97583, 44.6077499, -2736.35474, 0.984437346, 4.10396339e-08, 0.175734788, -3.62286876e-08, 1, -3.05844168e-08, -0.175734788, 2.3741821e-08, 0.984437346)
			SPAWNPOINT = "Colosseum"
		elseif MyLevel == 275 or MyLevel <= 299 or _G.Select_Mob_Farm == "Gladiator [Lv. 275]" then -- Gladiato
			Ms = "Gladiator [Lv. 275]"
			NameQuest = "ColosseumQuest"
			LevelQuest = 2
			NameMon = "Gladiato"
			CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
			CFrameMon = CFrame.new(-1274.75903, 58.1895943, -3188.16309, 0.464524001, 6.21005611e-08, 0.885560572, -4.80449414e-09, 1, -6.76054768e-08, -0.885560572, 2.71497012e-08, 0.464524001)
			SPAWNPOINT = "Colosseum"
		elseif MyLevel == 300 or MyLevel <= 324 or _G.Select_Mob_Farm == "Military Soldier [Lv. 300]" then -- Military Soldier
			Ms = "Military Soldier [Lv. 300]"
			NameQuest = "MagmaQuest"
			LevelQuest = 1
			NameMon = "Military Soldier"
			CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
			CFrameMon = CFrame.new(-5363.01123, 41.5056877, 8548.47266, -0.578253984, -3.29503091e-10, 0.815856814, 9.11209668e-08, 1, 6.498761e-08, -0.815856814, 1.11920997e-07, -0.578253984)
			SPAWNPOINT = "Magma"
		elseif MyLevel == 325 or MyLevel <= 374 or _G.Select_Mob_Farm == "Military Spy [Lv. 330]" then -- Military Spy
			Ms = "Military Spy [Lv. 325]"
			NameQuest = "MagmaQuest"
			LevelQuest = 2
			NameMon = "Military Spy"
			CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
			CFrameMon = CFrame.new(-5787.99023, 120.864456, 8762.25293, -0.188358366, -1.84706277e-08, 0.982100308, -1.23782129e-07, 1, -4.93306951e-09, -0.982100308, -1.22495649e-07, -0.188358366)
			SPAWNPOINT = "Magma"
		elseif MyLevel == 375 or MyLevel <= 399 or _G.Select_Mob_Farm == "Fishman Warrior [Lv. 375]" then -- Fishman Warrior
			Ms = "Fishman Warrior [Lv. 375]"
			NameQuest = "FishmanQuest"
			LevelQuest = 1
			NameMon = "Fishman Warrior"
			CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
			CFrameMon = CFrame.new(60946.6094, 48.6735229, 1525.91687, -0.0817126185, 8.90751153e-08, 0.996655822, 2.00889794e-08, 1, -8.77269599e-08, -0.996655822, 1.28533992e-08, -0.0817126185)
			SPAWNPOINT = "Fountain"
		elseif MyLevel == 400 or MyLevel <= 449 or _G.Select_Mob_Farm == "Fishman Commando [Lv. 400]" then -- Fishman Commando
			Ms = "Fishman Commando [Lv. 400]"
			NameQuest = "FishmanQuest"
			LevelQuest = 2
			NameMon = "Fishman Commando"
			CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
			CFrameMon = CFrame.new(61885.5039, 18.4828243, 1504.17896, 0.577502489, 0, -0.816389024, -0, 1.00000012, -0, 0.816389024, 0, 0.577502489)
			SPAWNPOINT = "Fountain"
		elseif MyLevel == 450 or MyLevel <= 474 or _G.Select_Mob_Farm == "God's Guard [Lv. 450]" then -- God's Guards
			Ms = "God's Guard [Lv. 450]"
			NameQuest = "SkyExp1Quest"
			LevelQuest = 1
			NameMon = "God's Guards"
			CFrameQuest = CFrame.new(-4721.71436, 845.277161, -1954.20105, -0.999277651, -5.56969759e-09, 0.0380011722, -4.14751478e-09, 1, 3.75035256e-08, -0.0380011722, 3.73188307e-08, -0.999277651)
			CFrameMon = CFrame.new(-4716.95703, 853.089722, -1933.92542, -0.93441087, -6.77488776e-09, -0.356197298, 1.12145182e-08, 1, -4.84390199e-08, 0.356197298, -4.92565206e-08, -0.93441087)
			SPAWNPOINT = "Sky"
		elseif MyLevel == 475 or MyLevel <= 524 or _G.Select_Mob_Farm == "Shanda [Lv. 475]" then -- Shandas
			sky = false
			Ms = "Shanda [Lv. 475]"
			NameQuest = "SkyExp1Quest"
			LevelQuest = 2
			NameMon = "Shandas"
			CFrameQuest = CFrame.new(-7863.63672, 5545.49316, -379.826324, 0.362120807, -1.98046344e-08, -0.93213129, 4.05822291e-08, 1, -5.48095125e-09, 0.93213129, -3.58431969e-08, 0.362120807)
			CFrameMon = CFrame.new(-7685.12354, 5601.05127, -443.171509, 0.150056243, 1.79768236e-08, -0.988677442, 6.67798661e-09, 1, 1.91962481e-08, 0.988677442, -9.48289181e-09, 0.150056243)
			SPAWNPOINT = "Sky"
		elseif MyLevel == 525 or MyLevel <= 549 or _G.Select_Mob_Farm == "Royal Squad [Lv. 525]" then -- Royal Squad
			sky = true
			Ms = "Royal Squad [Lv. 525]"
			NameQuest = "SkyExp2Quest"
			LevelQuest = 1
			NameMon = "Royal Squad"
			CFrameQuest = CFrame.new(-7902.66895, 5635.96387, -1411.71802, 0.0504222959, 2.5710392e-08, 0.998727977, 1.12541557e-07, 1, -3.14249675e-08, -0.998727977, 1.13982921e-07, 0.0504222959)
			CFrameMon = CFrame.new(-7685.02051, 5606.87842, -1442.729, 0.561947823, 7.69527464e-09, -0.827172697, -4.24974544e-09, 1, 6.41599973e-09, 0.827172697, -9.01838604e-11, 0.561947823)
			SPAWNPOINT = "Sky2"
		elseif MyLevel == 550 or MyLevel <= 624 or _G.Select_Mob_Farm == "Royal Soldier [Lv. 550]" then -- Royal Soldier
			Dis = 240
			sky = true
			Ms = "Royal Soldier [Lv. 550]"
			NameQuest = "SkyExp2Quest"
			LevelQuest = 2
			NameMon = "Royal Soldier"
			CFrameQuest = CFrame.new(-7902.66895, 5635.96387, -1411.71802, 0.0504222959, 2.5710392e-08, 0.998727977, 1.12541557e-07, 1, -3.14249675e-08, -0.998727977, 1.13982921e-07, 0.0504222959)
			CFrameMon = CFrame.new(-7864.44775, 5661.94092, -1708.22351, 0.998389959, 2.28686137e-09, -0.0567218624, 1.99431383e-09, 1, 7.54200258e-08, 0.0567218624, -7.54117195e-08, 0.998389959)
			SPAWNPOINT = "Sky2"
		elseif MyLevel == 625 or MyLevel <= 649 or _G.Select_Mob_Farm == "Galley Pirate [Lv. 625]" then -- Galley Pirate
			Dis = 240
			sky = false
			Ms = "Galley Pirate [Lv. 625]"
			NameQuest = "FountainQuest"
			LevelQuest = 1
			NameMon = "Galley Pirate"
			CFrameQuest = CFrame.new(5254.60156, 38.5011406, 4049.69678, -0.0504891425, -3.62066501e-08, -0.998724639, -9.87921389e-09, 1, -3.57534553e-08, 0.998724639, 8.06145284e-09, -0.0504891425)
			CFrameMon = CFrame.new(5595.06982, 41.5013695, 3961.47095, -0.992138803, -2.11610267e-08, -0.125142589, -1.34249509e-08, 1, -6.26613996e-08, 0.125142589, -6.04887518e-08, -0.992138803)
			SPAWNPOINT = "Fountain"
		elseif MyLevel >= 650 or _G.Select_Mob_Farm == "Galley Captain [Lv. 650]" then -- Galley Captain
			Dis = 240
			Ms = "Galley Captain [Lv. 650]"
			NameQuest = "FountainQuest"
			LevelQuest = 2
			NameMon = "Galley Captain"
			CFrameQuest = CFrame.new(5254.60156, 38.5011406, 4049.69678, -0.0504891425, -3.62066501e-08, -0.998724639, -9.87921389e-09, 1, -3.57534553e-08, 0.998724639, 8.06145284e-09, -0.0504891425)
			CFrameMon = CFrame.new(5658.5752, 38.5361786, 4928.93506, -0.996873081, 2.12391046e-06, -0.0790185928, 2.16989656e-06, 1, -4.96097414e-07, 0.0790185928, -6.66008248e-07, -0.996873081)
			SPAWNPOINT = "Fountain"
		end
	elseif World2 then
		if MyLevel == 700 or MyLevel <= 724 or _G.Select_Mob_Farm == "Raider [Lv. 700]" then -- Raider [Lv. 700]
			Ms = "Raider [Lv. 700]"
			NameQuest = "Area1Quest"
			LevelQuest = 1
			NameMon = "Raider"
			CFrameQuest = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
			CFrameMon = CFrame.new(-737.026123, 39.1748352, 2392.57959, 0.272128761, 0, -0.962260842, -0, 1, -0, 0.962260842, 0, 0.272128761)
			SPAWNPOINT = "DressTown"
		elseif MyLevel == 725 or MyLevel <= 774 or _G.Select_Mob_Farm == "Mercenary [Lv. 725]" then -- Mercenary [Lv. 725]
			Ms = "Mercenary [Lv. 725]"
			NameQuest = "Area1Quest"
			LevelQuest = 2
			NameMon = "Mercenary"
			CFrameQuest = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
			CFrameMon = CFrame.new(-973.731995, 95.8733215, 1836.46936, 0.999135971, 2.02326991e-08, -0.0415605344, -1.90767793e-08, 1, 2.82094952e-08, 0.0415605344, -2.73922804e-08, 0.999135971)
			SPAWNPOINT = "DressTown"
		elseif MyLevel == 775 or MyLevel <= 799 or _G.Select_Mob_Farm == "Swan Pirate [Lv. 775]" then -- Swan Pirate [Lv. 775]
			Ms = "Swan Pirate [Lv. 775]"
			NameQuest = "Area2Quest"
			LevelQuest = 1
			NameMon = "Swan Pirate"
			CFrameQuest = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
			CFrameMon = CFrame.new(970.369446, 142.653198, 1217.3667, 0.162079468, -4.85452638e-08, -0.986777723, 1.03357589e-08, 1, -4.74980872e-08, 0.986777723, -2.50063148e-09, 0.162079468)
			SPAWNPOINT = "DressTown"
		elseif MyLevel == 800 or MyLevel <= 874 or _G.Select_Mob_Farm == "Factory Staff [Lv. 800]" then -- Factory Staff [Lv. 800]
			Ms = "Factory Staff [Lv. 800]"
			NameQuest = "Area2Quest"
			LevelQuest = 2
			NameMon = "Factory Staff"
			CFrameQuest = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
			CFrameMon = CFrame.new(296.786499, 72.9948196, -57.1298141, -0.876037002, -5.32364979e-08, 0.482243896, -3.87658332e-08, 1, 3.99718729e-08, -0.482243896, 1.63222538e-08, -0.876037002)
			SPAWNPOINT = "DressTown"
		elseif MyLevel == 875 or MyLevel <= 899 or _G.Select_Mob_Farm == "Marine Lieutenant [Lv. 875]" then -- Marine Lieutenant [Lv. 875]
			Ms = "Marine Lieutenant [Lv. 875]"
			NameQuest = "MarineQuest3"
			LevelQuest = 1
			NameMon = "Marine Lieutenant"
			CFrameQuest = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
			CFrameMon = CFrame.new(-2913.26367, 73.0011826, -2971.64282, 0.910507619, 0, 0.413492233, 0, 1.00000012, 0, -0.413492233, 0, 0.910507619)
			SPAWNPOINT = "Greenb"
		elseif MyLevel == 900 or MyLevel <= 949 or _G.Select_Mob_Farm == "Marine Captain [Lv. 900]" then -- Marine Captain [Lv. 900]
			Ms = "Marine Captain [Lv. 900]"
			NameQuest = "MarineQuest3"
			LevelQuest = 2
			NameMon = "Marine Captain"
			CFrameQuest = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
			CFrameMon = CFrame.new(-1868.67688, 73.0011826, -3321.66333, -0.971402287, 1.06502087e-08, 0.237439692, 3.68856199e-08, 1, 1.06050372e-07, -0.237439692, 1.11775684e-07, -0.971402287)
			SPAWNPOINT = "Greenb"
		elseif MyLevel == 950 or MyLevel <= 974 or _G.Select_Mob_Farm == "Zombie [Lv. 950]" then -- Zombie [Lv. 950]
			Ms = "Zombie [Lv. 950]"
			NameQuest = "ZombieQuest"
			LevelQuest = 1
			NameMon = "Zombie"
			CFrameQuest = CFrame.new(-5492.79395, 48.5151672, -793.710571, 0.321800292, -6.24695815e-08, 0.946807742, 4.05616092e-08, 1, 5.21931227e-08, -0.946807742, 2.16082796e-08, 0.321800292)
			CFrameMon = CFrame.new(-5634.83838, 126.067039, -697.665039, -0.992770672, 6.77618939e-09, 0.120025545, 1.65461245e-08, 1, 8.04023372e-08, -0.120025545, 8.18070234e-08, -0.992770672)
			SPAWNPOINT = "Graveyard"
		elseif MyLevel == 975 or MyLevel <= 999 or _G.Select_Mob_Farm == "Vampire [Lv. 975]" then -- Vampire [Lv. 975]
			Ms = "Vampire [Lv. 975]"
			NameQuest = "ZombieQuest"
			LevelQuest = 2
			NameMon = "Vampire"
			CFrameQuest = CFrame.new(-5492.79395, 48.5151672, -793.710571, 0.321800292, -6.24695815e-08, 0.946807742, 4.05616092e-08, 1, 5.21931227e-08, -0.946807742, 2.16082796e-08, 0.321800292)
			CFrameMon = CFrame.new(-6030.32031, 6.4377408, -1313.5564, -0.856965423, 3.9138893e-08, -0.515373945, -1.12178942e-08, 1, 9.45958547e-08, 0.515373945, 8.68467822e-08, -0.856965423)
			SPAWNPOINT = "Graveyard"
		elseif MyLevel == 1000 or MyLevel <= 1049 or _G.Select_Mob_Farm == "Snow Trooper [Lv. 1000]" then -- Snow Trooper [Lv. 1000] **
			Ms = "Snow Trooper [Lv. 1000]"
			NameQuest = "SnowMountainQuest"
			LevelQuest = 1
			NameMon = "Snow Trooper"
			CFrameQuest = CFrame.new(604.964966, 401.457062, -5371.69287, 0.353063971, 1.89520435e-08, -0.935599446, -5.81846002e-08, 1, -1.70033754e-09, 0.935599446, 5.50377841e-08, 0.353063971)
			CFrameMon = CFrame.new(535.893433, 401.457062, -5329.6958, -0.999524176, 0, 0.0308452044, 0, 1, -0, -0.0308452044, 0, -0.999524176)
			SPAWNPOINT = "Snowy"
		elseif MyLevel == 1050 or MyLevel <= 1099 or _G.Select_Mob_Farm == "Winter Warrior [Lv. 1050]" then -- Winter Warrior [Lv. 1050]
			Ms = "Winter Warrior [Lv. 1050]"
			NameQuest = "SnowMountainQuest"
			LevelQuest = 2
			NameMon = "Winter Warrior"
			CFrameQuest = CFrame.new(604.964966, 401.457062, -5371.69287, 0.353063971, 1.89520435e-08, -0.935599446, -5.81846002e-08, 1, -1.70033754e-09, 0.935599446, 5.50377841e-08, 0.353063971)
			CFrameMon = CFrame.new(1223.7417, 454.575226, -5170.02148, 0.473996818, 2.56845354e-08, 0.880526543, -5.62456428e-08, 1, 1.10811016e-09, -0.880526543, -5.00510211e-08, 0.473996818)
			SPAWNPOINT = "Snowy"
		elseif MyLevel == 1100 or MyLevel <= 1124 or _G.Select_Mob_Farm == "Lab Subordinate [Lv. 1100]" then -- Lab Subordinate [Lv. 1100]
			Ms = "Lab Subordinate [Lv. 1100]"
			NameQuest = "IceSideQuest"
			LevelQuest = 1
			NameMon = "Lab Subordinate"
			CFrameQuest = CFrame.new(-6060.10693, 15.9868021, -4904.7876, -0.411000341, -5.06538868e-07, 0.91163528, 1.26306062e-07, 1, 6.12581289e-07, -0.91163528, 3.66916197e-07, -0.411000341)
			CFrameMon = CFrame.new(-5769.2041, 37.9288292, -4468.38721, -0.569419742, -2.49055017e-08, 0.822046936, -6.96206541e-08, 1, -1.79282633e-08, -0.822046936, -6.74401548e-08, -0.569419742)
			SPAWNPOINT = "CircleIslandIce"
		elseif MyLevel == 1125 or MyLevel <= 1174 or _G.Select_Mob_Farm == "Horned Warrior [Lv. 1125]" then -- Horned Warrior [Lv. 1125]
			Ms = "Horned Warrior [Lv. 1125]"
			NameQuest = "IceSideQuest"
			LevelQuest = 2
			NameMon = "Horned Warrior"
			CFrameQuest = CFrame.new(-6060.10693, 15.9868021, -4904.7876, -0.411000341, -5.06538868e-07, 0.91163528, 1.26306062e-07, 1, 6.12581289e-07, -0.91163528, 3.66916197e-07, -0.411000341)
			CFrameMon = CFrame.new(-6400.85889, 24.7645149, -5818.63574, -0.964845479, 8.65926566e-08, -0.262817472, 3.98261392e-07, 1, -1.13260398e-06, 0.262817472, -1.19745812e-06, -0.964845479)
			SPAWNPOINT = "CircleIslandIce"
		elseif MyLevel == 1175 or MyLevel <= 1199 or _G.Select_Mob_Farm == "Magma Ninja [Lv. 1175]" then -- Magma Ninja [Lv. 1175]
			Ms = "Magma Ninja [Lv. 1175]"
			NameQuest = "FireSideQuest"
			LevelQuest = 1
			NameMon = "Magma Ninja"
			CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223, 0.831796765, 1.15322464e-07, -0.555080295, -1.10814341e-07, 1, 4.17010995e-08, 0.555080295, 2.68240168e-08, 0.831796765)
			CFrameMon = CFrame.new(-5496.65576, 58.6890411, -5929.76855, -0.885073781, 0, -0.465450764, 0, 1.00000012, -0, 0.465450764, 0, -0.885073781)
			SPAWNPOINT = "CircleIslandFire"
		elseif MyLevel == 1200 or MyLevel <= 1249 or _G.Select_Mob_Farm == "Lava Pirate [Lv. 1200]" then -- Lava Pirate [Lv. 1200]
			Ms = "Lava Pirate [Lv. 1200]"
			NameQuest = "FireSideQuest"
			LevelQuest = 2
			NameMon = "Lava Pirate"
			CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223, 0.831796765, 1.15322464e-07, -0.555080295, -1.10814341e-07, 1, 4.17010995e-08, 0.555080295, 2.68240168e-08, 0.831796765)
			CFrameMon = CFrame.new(-5169.71729, 34.1234779, -4669.73633, -0.196780294, 0, 0.98044765, 0, 1.00000012, -0, -0.98044765, 0, -0.196780294)
			SPAWNPOINT = "CircleIslandFire"
		elseif MyLevel == 1250 or MyLevel <= 1274 or _G.Select_Mob_Farm == "Ship Deckhand [Lv. 1250]" then -- Ship Deckhand [Lv. 1250]
			Ms = "Ship Deckhand [Lv. 1250]"
			NameQuest = "ShipQuest1"
			LevelQuest = 1
			NameMon = "Ship Deckhand"
			CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
			CFrameMon = CFrame.new(1163.80872, 138.288452, 33058.4258, -0.998580813, 5.49076979e-08, -0.0532564968, 5.57436763e-08, 1, -1.42118655e-08, 0.0532564968, -1.71604082e-08, -0.998580813)
			SPAWNPOINT = "Ship"
		elseif MyLevel == 1275 or MyLevel <= 1299 or _G.Select_Mob_Farm == "Ship Engineer [Lv. 1275]"  then -- Ship Engineer [Lv. 1275]
			Ms = "Ship Engineer [Lv. 1275]"
			NameQuest = "ShipQuest1"
			LevelQuest = 2
			NameMon = "Ship Engineer"
			CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
			CFrameMon = CFrame.new(916.666504, 44.0920448, 32917.207, -0.99746871, -4.85034697e-08, -0.0711069331, -4.8925461e-08, 1, 4.19294288e-09, 0.0711069331, 7.66126895e-09, -0.99746871)
			SPAWNPOINT = "Ship"
		elseif MyLevel == 1300 or MyLevel <= 1324 or _G.Select_Mob_Farm == "Ship Steward [Lv. 1300]" then -- Ship Steward [Lv. 1300]
			Ms = "Ship Steward [Lv. 1300]"
			NameQuest = "ShipQuest2"
			LevelQuest = 1
			NameMon = "Ship Steward"
			CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
			CFrameMon = CFrame.new(918.743286, 129.591064, 33443.4609, -0.999792814, -1.7070947e-07, -0.020350717, -1.72559169e-07, 1, 8.91351277e-08, 0.020350717, 9.2628369e-08, -0.999792814)
			SPAWNPOINT = "Ship"
		elseif MyLevel == 1325 or MyLevel <= 1349 or _G.Select_Mob_Farm == "Ship Officer [Lv. 1325]" then -- Ship Officer [Lv. 1325]
			Ms = "Ship Officer [Lv. 1325]"
			NameQuest = "ShipQuest2"
			LevelQuest = 2
			NameMon = "Ship Officer"
			CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
			CFrameMon = CFrame.new(786.051941, 181.474106, 33303.2969, 0.999285698, -5.32193063e-08, 0.0377905183, 5.68968588e-08, 1, -9.62386864e-08, -0.0377905183, 9.83201005e-08, 0.999285698)
			SPAWNPOINT = "Ship"
		elseif MyLevel == 1350 or MyLevel <= 1374 or _G.Select_Mob_Farm == "Arctic Warrior [Lv. 1350]" then -- Arctic Warrior [Lv. 1350]
			Ms = "Arctic Warrior [Lv. 1350]"
			NameQuest = "FrostQuest"
			LevelQuest = 1
			NameMon = "Arctic Warrior"
			CFrameQuest = CFrame.new(5669.43506, 28.2117786, -6482.60107, 0.888092756, 1.02705066e-07, 0.459664226, -6.20391774e-08, 1, -1.03572376e-07, -0.459664226, 6.34646895e-08, 0.888092756)
			CFrameMon = CFrame.new(5995.07471, 57.3188477, -6183.47314, 0.702747107, -1.53454167e-07, -0.711440146, -1.08168464e-07, 1, -3.22542007e-07, 0.711440146, 3.03620908e-07, 0.702747107)
			SPAWNPOINT = "IceCastle"
		elseif MyLevel == 1375 or MyLevel <= 1424 or _G.Select_Mob_Farm == "Snow Lurker [Lv. 1375]" then -- Snow Lurker [Lv. 1375]
			Ms = "Snow Lurker [Lv. 1375]"
			NameQuest = "FrostQuest"
			LevelQuest = 2
			NameMon = "Snow Lurker"
			CFrameQuest = CFrame.new(5669.43506, 28.2117786, -6482.60107, 0.888092756, 1.02705066e-07, 0.459664226, -6.20391774e-08, 1, -1.03572376e-07, -0.459664226, 6.34646895e-08, 0.888092756)
			CFrameMon = CFrame.new(5518.00684, 60.5559731, -6828.80518, -0.650781393, -3.64292951e-08, 0.759265184, -4.07668654e-09, 1, 4.44854642e-08, -0.759265184, 2.58550248e-08, -0.650781393)
			SPAWNPOINT = "IceCastle"
		elseif MyLevel == 1425 or MyLevel <= 1449 or _G.Select_Mob_Farm == "Sea Soldier [Lv. 1425]" then -- Sea Soldier [Lv. 1425]
			Ms = "Sea Soldier [Lv. 1425]"
			NameQuest = "ForgottenQuest"
			LevelQuest = 1
			NameMon = "Sea Soldier"
			CFrameQuest = CFrame.new(-3052.99097, 236.881363, -10148.1943, -0.997911751, 4.42321983e-08, 0.064591676, 4.90968759e-08, 1, 7.37270085e-08, -0.064591676, 7.67442998e-08, -0.997911751)
			CFrameMon = CFrame.new(-3029.78467, 66.944252, -9777.38184, -0.998552859, 1.09555076e-08, 0.0537791774, 7.79564235e-09, 1, -5.89660658e-08, -0.0537791774, -5.84614881e-08, -0.998552859)
			SPAWNPOINT = "ForgottenIsland"
		elseif MyLevel >= 1450 or _G.Select_Mob_Farm == "Water Fighter [Lv. 1450]" then -- Water Fighter [Lv. 1450]
			Ms = "Water Fighter [Lv. 1450]"
			NameQuest = "ForgottenQuest"
			LevelQuest = 2
			NameMon = "Water Fighter"
			CFrameQuest = CFrame.new(-3052.99097, 236.881363, -10148.1943, -0.997911751, 4.42321983e-08, 0.064591676, 4.90968759e-08, 1, 7.37270085e-08, -0.064591676, 7.67442998e-08, -0.997911751)
			CFrameMon = CFrame.new(-3262.00098, 298.699615, -10553.6943, -0.233570755, -4.57538185e-08, 0.972339869, -5.80986068e-08, 1, 3.30992194e-08, -0.972339869, -4.87605725e-08, -0.233570755)
			SPAWNPOINT = "ForgottenIsland"
		end
	elseif World3 then
		if MyLevel == 1500 or MyLevel <= 1524 or _G.Select_Mob_Farm == "Pirate Millionaire [Lv. 1500]" then
			Ms = "Pirate Millionaire [Lv. 1500]"
			NameQuest = "PiratePortQuest"
			LevelQuest = 1
			NameMon = "Pirate Millionaire"
			CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
			CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
			SPAWNPOINT = "Default"
		elseif MyLevel == 1525 or MyLevel <= 1574 or _G.Select_Mob_Farm == "Pistol Billionaire [Lv. 1525]" then
			Ms = "Pistol Billionaire [Lv. 1525]"
			NameQuest = "PiratePortQuest"
			LevelQuest = 2
			NameMon = "Pistol Billionaire"
			CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
			CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
			SPAWNPOINT = "Default"
		elseif MyLevel == 1575 or MyLevel <= 1599 or _G.Select_Mob_Farm == "Dragon Crew Warrior [Lv. 1575]" then
			Ms = "Dragon Crew Warrior [Lv. 1575]"
			NameQuest = "AmazonQuest"
			LevelQuest = 1
			NameMon = "Dragon Crew Warrior"
			CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
			CFrameMon = CFrame.new(6241.9951171875, 51.522083282471, -1243.9771728516)
			SPAWNPOINT = "Hydra3"
		elseif MyLevel == 1600 or MyLevel <= 1624 or _G.Select_Mob_Farm == "Dragon Crew Archer [Lv. 1600]" then
			Ms = "Dragon Crew Archer [Lv. 1600]"
			NameQuest = "AmazonQuest"
			LevelQuest = 2
			NameMon = "Dragon Crew Archer"
			CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
			CFrameMon = CFrame.new(6488.9155273438, 383.38375854492, -110.66246032715)
			SPAWNPOINT = "Hydra3"
		elseif MyLevel == 1625 or MyLevel <= 1649 or _G.Select_Mob_Farm == "Female Islander [Lv. 1625]" then
			Ms = "Female Islander [Lv. 1625]"
			NameQuest = "AmazonQuest2"
			LevelQuest = 1
			NameMon = "Female Islander"
			CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
			CFrameMon = CFrame.new(4770.4990234375, 758.95520019531, 1069.8680419922)
			SPAWNPOINT = "Hydra1"
		elseif MyLevel == 1650 or MyLevel <= 1699 or _G.Select_Mob_Farm == "Giant Islander [Lv. 1650]" then
			Ms = "Giant Islander [Lv. 1650]"
			NameQuest = "AmazonQuest2"
			LevelQuest = 2
			NameMon = "Giant Islander"
			CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
			CFrameMon = CFrame.new(4530.3540039063, 656.75695800781, -131.60952758789)
			SPAWNPOINT = "Hydra1"
		elseif MyLevel == 1700 or MyLevel <= 1724 or _G.Select_Mob_Farm == "Marine Commodore [Lv. 1700]" then
			Ms = "Marine Commodore [Lv. 1700]"
			NameQuest = "MarineTreeIsland"
			LevelQuest = 1
			NameMon = "Marine Commodore"
			CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
			CFrameMon = CFrame.new(2490.0844726563, 190.4232635498, -7160.0502929688)
			SPAWNPOINT = "GreatTree"
		elseif MyLevel == 1725 or MyLevel <= 1774 or _G.Select_Mob_Farm == "Marine Rear Admiral [Lv. 1725]" then
			Ms = "Marine Rear Admiral [Lv. 1725]"
			NameQuest = "MarineTreeIsland"
			LevelQuest = 2
			NameMon = "Marine Rear Admiral"
			CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
			CFrameMon = CFrame.new(3951.3903808594, 229.11549377441, -6912.81640625)
			SPAWNPOINT = "GreatTree"
		elseif MyLevel == 1775 or MyLevel <= 1799 or _G.Select_Mob_Farm == "Fishman Raider [Lv. 1775]" then
			Ms = "Fishman Raider [Lv. 1775]"
			NameQuest = "DeepForestIsland3"
			LevelQuest = 1
			NameMon = "Fishman Raider"
			CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
			CFrameMon = CFrame.new(-10322.400390625, 390.94473266602, -8580.0908203125)
			SPAWNPOINT = "PineappleTown"
		elseif MyLevel == 1800 or MyLevel <= 1824 or _G.Select_Mob_Farm == "Fishman Captain [Lv. 1800]" then
			Ms = "Fishman Captain [Lv. 1800]"
			NameQuest = "DeepForestIsland3"
			LevelQuest = 2
			NameMon = "Fishman Captain"
			CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
			CFrameMon = CFrame.new(-11194.541992188, 442.02795410156, -8608.806640625)
			SPAWNPOINT = "PineappleTown"
		elseif MyLevel == 1825 or MyLevel <= 1849 or _G.Select_Mob_Farm == "Forest Pirate [Lv. 1825]" then
			Ms = "Forest Pirate [Lv. 1825]"
			NameQuest = "DeepForestIsland"
			LevelQuest = 1
			NameMon = "Forest Pirate"
			CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
			CFrameMon = CFrame.new(-13225.809570313, 428.19387817383, -7753.1245117188)
			SPAWNPOINT = "BigMansion"
		elseif MyLevel == 1850 or MyLevel <= 1899 or _G.Select_Mob_Farm == "Mythological Pirate [Lv. 1850]" then
			Ms = "Mythological Pirate [Lv. 1850]"
			NameQuest = "DeepForestIsland"
			LevelQuest = 2
			NameMon = "Mythological Pirate"
			CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
			CFrameMon = CFrame.new(-13869.172851563, 564.95251464844, -7084.4135742188)
			SPAWNPOINT = "BigMansion"
		elseif MyLevel == 1900 or MyLevel <= 1924 or _G.Select_Mob_Farm == "Jungle Pirate [Lv. 1900]" then
			Ms = "Jungle Pirate [Lv. 1900]"
			NameQuest = "DeepForestIsland2"
			LevelQuest = 1
			NameMon = "Jungle Pirate"
			CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
			CFrameMon = CFrame.new(-11982.221679688, 376.32522583008, -10451.415039063)
			SPAWNPOINT = "PineappleTown"
		elseif MyLevel == 1925 or MyLevel <= 1974 or _G.Select_Mob_Farm == "Musketeer Pirate [Lv. 1925]" then
			Ms = "Musketeer Pirate [Lv. 1925]"
			NameQuest = "DeepForestIsland2"
			LevelQuest = 2
			NameMon = "Musketeer Pirate"
			CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
			CFrameMon = CFrame.new(-13282.3046875, 496.23684692383, -9565.150390625)
			SPAWNPOINT = "PineappleTown"
		elseif MyLevel == 1975 or MyLevel <= 1999 or _G.Select_Mob_Farm == "Reborn Skeleton [Lv. 1975]" then
			Ms = "Reborn Skeleton [Lv. 1975]"
			NameQuest = "HauntedQuest1"
			LevelQuest = 1
			NameMon = "Reborn Skeleton"
			CFrameQuest = CFrame.new(-9479.2168, 141.215088, 5566.09277, 0, 0, 1, 0, 1, -0, -1, 0, 0)
			CFrameMon = CFrame.new(-8761.3154296875, 164.85829162598, 6161.1567382813)
			SPAWNPOINT = "HauntedCastle"
		elseif MyLevel == 2000 or MyLevel <= 2024 or _G.Select_Mob_Farm == "Living Zombie [Lv. 2000]" then
			Ms = "Living Zombie [Lv. 2000]"
			NameQuest = "HauntedQuest1"
			LevelQuest = 2
			NameMon = "Living Zombie"
			CFrameQuest = CFrame.new(-9479.2168, 141.215088, 5566.09277, 0, 0, 1, 0, 1, -0, -1, 0, 0)
			CFrameMon = CFrame.new(-10093.930664063, 237.38233947754, 6180.5654296875)
			SPAWNPOINT = "HauntedCastle"
		elseif MyLevel == 2025 or MyLevel <= 2049 or _G.Select_Mob_Farm == "Demonic Soul [Lv. 2025]" then
			Ms = "Demonic Soul [Lv. 2025]"
			NameQuest = "HauntedQuest2"
			LevelQuest = 1
			NameMon = "Demonic Soul"
			CFrameQuest = CFrame.new(-9514.78027, 171.162918, 6078.82373, 0.301918149, 7.4535027e-09, 0.953333855, -3.22802141e-09, 1, -6.79604995e-09, -0.953333855, -1.02553133e-09, 0.301918149)
			CFrameMon = CFrame.new(-9466.72949, 171.162918, 6132.01514)
			SPAWNPOINT = "HauntedCastle"
		elseif MyLevel == 2050 or MyLevel <= 2074 or _G.Select_Mob_Farm == "Posessed Mummy [Lv. 2050]" then
			Ms = "Posessed Mummy [Lv. 2050]" 
			NameQuest = "HauntedQuest2"
			LevelQuest = 2
			NameMon = "Posessed Mummy"
			CFrameQuest = CFrame.new(-9514.78027, 171.162918, 6078.82373, 0.301918149, 7.4535027e-09, 0.953333855, -3.22802141e-09, 1, -6.79604995e-09, -0.953333855, -1.02553133e-09, 0.301918149)
			CFrameMon = CFrame.new(-9589.93848, 4.85058546, 6190.27197)
			SPAWNPOINT = "HauntedCastle"
		elseif MyLevel == 2075 or MyLevel <= 2099 or _G.Select_Mob_Farm == "Peanut Scout [Lv. 2075]" then
			Ms = "Peanut Scout [Lv. 2075]"
			NameQuest = "NutsIslandQuest"
			LevelQuest = 1
			NameMon = "Peanut Scout"
			CFrameQuest = CFrame.new(-2103.9375, 38.139019012451, -10192.702148438)
			CFrameMon = CFrame.new(-2150.587890625, 122.49767303467, -10358.994140625)
			SPAWNPOINT = "Peanut"
		elseif MyLevel == 2100 or MyLevel <= 2124 or _G.Select_Mob_Farm == "Peanut President [Lv. 2100]" then
			Ms = "Peanut President [Lv. 2100]"
			NameQuest = "NutsIslandQuest"
			LevelQuest = 2
			NameMon = "Peanut President"
			CFrameQuest = CFrame.new(-2103.9375, 38.139019012451, -10192.702148438)
			CFrameMon = CFrame.new(-2150.587890625, 122.49767303467, -10358.994140625)
			SPAWNPOINT = "Peanut"
		elseif MyLevel == 2125 or MyLevel <= 2149 or _G.Select_Mob_Farm == "Ice Cream Chef [Lv. 2125]" then
			Ms = "Ice Cream Chef [Lv. 2125]"
			NameQuest = "IceCreamIslandQuest"
			LevelQuest = 1
			NameMon = "Ice Cream Chef"
			CFrameQuest = CFrame.new(-819.84533691406, 65.845329284668, -10965.487304688)
			CFrameMon = CFrame.new(-890.55895996094, 186.34135437012, -11127.306640625)
			SPAWNPOINT = "IceCream"
		elseif MyLevel == 2150 or MyLevel <= 2199 or _G.Select_Mob_Farm == "Ice Cream Commander [Lv. 2150]" then
			Ms = "Ice Cream Commander [Lv. 2150]"
			NameQuest = "IceCreamIslandQuest"
			LevelQuest = 2
			NameMon = "Ice Cream Commander"
			CFrameQuest = CFrame.new(-819.84533691406, 65.845329284668, -10965.487304688)
			CFrameMon = CFrame.new(-890.55895996094, 186.34135437012, -11127.306640625)
			SPAWNPOINT = "IceCream"
		elseif MyLevel == 2200 or MyLevel <= 2224 or _G.Select_Mob_Farm == "Cookie Crafter [Lv. 2200]" then
			Ms = "Cookie Crafter [Lv. 2200]"
			NameQuest = "CakeQuest1"
			LevelQuest = 1
			NameMon = "Cookie Crafter"
			CFrameQuest = CFrame.new(-2021.5509033203125, 37.798221588134766, -12028.103515625)
			CFrameMon = CFrame.new(-2273.00244140625, 90.22590637207031, -12151.62109375)
			SPAWNPOINT = "Loaf"
		elseif MyLevel == 2225 or MyLevel <= 2249 or _G.Select_Mob_Farm == "Cake Guard [Lv. 2225]" then
			Ms = "Cake Guard [Lv. 2225]"
			NameQuest = "CakeQuest1"
			LevelQuest = 2
			NameMon = "Cake Guard"
			CFrameQuest = CFrame.new(-2021.5509033203125, 37.798221588134766, -12028.103515625)
			CFrameMon = CFrame.new(-1442.373046875, 158.14111328125, -12277.37109375)
			SPAWNPOINT = "Loaf"
		elseif MyLevel == 2250 or MyLevel <= 2274 or _G.Select_Mob_Farm == "Baking Staff [Lv. 2250]" then
			Ms = "Baking Staff [Lv. 2250]"
			NameQuest = "CakeQuest2"
			LevelQuest = 1
			NameMon = "Baking Staff"
			CFrameQuest = CFrame.new(-1927.9107666015625, 37.79813003540039, -12843.78515625)
			CFrameMon = CFrame.new(-1837.2803955078125, 129.0594482421875, -12934.5498046875)
			SPAWNPOINT = "Loaf"
		elseif MyLevel == 2275 or MyLevel <= 2299 or _G.Select_Mob_Farm == "Head Baker [Lv. 2275]" then
			Ms = "Head Baker [Lv. 2275]"
			NameQuest = "CakeQuest2"
			LevelQuest = 2
			NameMon = "Head Baker"
			CFrameQuest = CFrame.new(-1927.9107666015625, 37.79813003540039, -12843.78515625)
			CFrameMon = CFrame.new(-2203.302490234375, 109.90937042236328, -12788.7333984375)
			SPAWNPOINT = "Loaf"
		elseif MyLevel == 2300 or MyLevel <= 2324 or _G.Select_Mob_Farm == "Cocoa Warrior [Lv. 2300]" then
			Ms = "Cocoa Warrior [Lv. 2300]"
			NameQuest = "ChocQuest1"
			LevelQuest = 1
			NameMon = "Cocoa Warrior"
			CFrameQuest = CFrame.new(231.13571166992188, 24.734268188476562, -12195.1162109375)
			CFrameMon = CFrame.new(231.13571166992188, 24.734268188476562, -12195.1162109375)
			SPAWNPOINT = "Chocolate"
		elseif MyLevel == 2325 or MyLevel <= 2349 or _G.Select_Mob_Farm == "Chocolate Bar Battler [Lv. 2325]" then
			Ms = "Chocolate Bar Battler [Lv. 2325]"
			NameQuest = "ChocQuest1"
			LevelQuest = 2
			NameMon = "Chocolate Bar Battler"
			CFrameQuest = CFrame.new(231.13571166992188, 24.734268188476562, -12195.1162109375)
			CFrameMon = CFrame.new(231.13571166992188, 24.734268188476562, -12195.1162109375)
			SPAWNPOINT = "Chocolate"
		elseif MyLevel == 2350 or MyLevel <= 2374 or _G.Select_Mob_Farm == "Sweet Thief [Lv. 2350]" then
			Ms = "Sweet Thief [Lv. 2350]"
			NameQuest = "ChocQuest2"
			LevelQuest = 1
			NameMon = "Sweet Thief"
			CFrameQuest = CFrame.new(147.52256774902344, 24.793832778930664, -12775.3583984375)
			CFrameMon = CFrame.new(147.52256774902344, 24.793832778930664, -12775.3583984375)
			SPAWNPOINT = "Chocolate"
		elseif MyLevel == 2375 or MyLevel <= 2400 or _G.Select_Mob_Farm == "Candy Rebel [Lv. 2375]" then
			Ms = "Candy Rebel [Lv. 2375]"
			NameQuest = "ChocQuest2"
			LevelQuest = 2
			NameMon = "Candy Rebel"
			CFrameQuest = CFrame.new(147.52256774902344, 24.793832778930664, -12775.3583984375)
			CFrameMon = CFrame.new(147.52256774902344, 24.793832778930664, -12775.3583984375)
			SPAWNPOINT = "Chocolate"
		elseif MyLevel == 2400 or MyLevel <= 2425 or _G.Select_Mob_Farm == "Candy Pirate [Lv. 2400]" then
			Ms = "Candy Pirate [Lv. 2400]"
			NameQuest = "CandyQuest1"
			LevelQuest = 1
			NameMon = "Candy Pirate"
			CFrameQuest = CFrame.new(-1151.48987, 16.1422901, -14445.6904, -0.316594511, -6.85698254e-08, -0.948560953, -2.05343067e-08, 1, -6.54346692e-08, 0.948560953, -1.23821675e-09, -0.316594511)
			CFrameMon = CFrame.new(-1408.46521, 16.1423531, -14552.2041, 0.90175873, -8.17216943e-08, -0.432239741, 7.81264475e-08, 1, -2.60746162e-08, 0.432239741, -1.02563433e-08, 0.90175873)
			SPAWNPOINT = "Chocolate"
		elseif MyLevel == 2425 or MyLevel <= 2449 or _G.Select_Mob_Farm == "Snow Demon [Lv. 2425]" then
			Ms = "Snow Demon [Lv. 2425]"
			NameQuest = "CandyQuest1"
			LevelQuest = 2
			NameMon = "Snow Demon"
			CFrameQuest = CFrame.new(-1151.48987, 16.1422901, -14445.6904, -0.316594511, -6.85698254e-08, -0.948560953, -2.05343067e-08, 1, -6.54346692e-08, 0.948560953, -1.23821675e-09, -0.316594511)
			CFrameMon = CFrame.new(-777.070862, 23.5809536, -14453.0078, 0.33384338, 0, -0.942628562, 0, 1, 0, 0.942628562, 0, 0.33384338)
			SPAWNPOINT = "Chocolate"
		elseif MyLevel == 2450 or MyLevel <= 2474 then
			Ms = "Isle Outlaw"
			NameQuest = "TikiQuest1"
			LevelQuest = 1            
			NameMon = "Isle Outlaw"
			CFrameQuest = CFrame.new(-16550.8242, 55.6605682, -173.9104, -0.905696571, -9.94871652e-09, 0.423926592, 2.55107824e-09, 1, 2.89182598e-08, -0.423926592, 2.72726375e-08, -0.905696571)
			CFrameMon = CFrame.new(-16226.8994, 21.761652, -189.266098, -0.393145293, -1.96587813e-08, -0.91947639, -8.38096481e-10, 1, -2.10220605e-08, 0.91947639, -7.49411377e-09, -0.393145293)
		elseif MyLevel == 2475 or MyLevel <= 2499 then
			Ms = "Island Boy"
			NameQuest = "TikiQuest1"
			LevelQuest = 2            
			NameMon = "Island Boy"
			CFrameQuest = CFrame.new(-16550.8242, 55.6605682, -173.9104, -0.905696571, -9.94871652e-09, 0.423926592, 2.55107824e-09, 1, 2.89182598e-08, -0.423926592, 2.72726375e-08, -0.905696571)
			CFrameMon = CFrame.new(-16789.03515625, 21.761653900146484, -165.9088897705078)
		elseif MyLevel == 2500 or MyLevel <= 2524 then
			Ms = "Sun-kissed Wraaior"
			NameQuest = "TikiQuest2"
			LevelQuest = 1           
			NameMon = "Sun-kissed Wraaior"
			CFrameQuest = CFrame.new(-16282.751953125, 21.761648178100586, 1030.4146728515625)
			CFrameMon = CFrame.new(-16789.03515625, 21.761653900146484, -165.9088897705078)
		elseif MyLevel == 2525 or MyLevel <= 2550 then
			Ms = "Isle Champion"
			NameQuest = "TikiQuest2"
			LevelQuest = 2            
			NameMon = "Isle Champion"
			CFrameQuest = CFrame.new(-16282.751953125, 21.761648178100586, 1030.4146728515625)
			CFrameMon = CFrame.new(-16889.427734375, 11.66054916381836, 1028.85986328125)
		end
	end
end

-- [Save Settings]

function LoadSettings()
	if readfile and writefile and isfile and isfolder then
		if not isfolder("Manake Hub Premium Scripts") then
			makefolder("Manake Hub Premium Scripts")
		end
		if not isfolder("Manake Hub Premium Scripts/Blox Fruits/") then
			makefolder("Manake Hub Premium Scripts/Blox Fruits/")
		end
		if not isfile("Manake Hub Premium Scripts/Blox Fruits/" .. game.Players.LocalPlayer.Name .. ".json") then
			writefile("Manake Hub Premium Scripts/Blox Fruits/" .. game.Players.LocalPlayer.Name .. ".json", game:GetService("HttpService"):JSONEncode(_G.Settings))
		else
			local Decode = game:GetService("HttpService"):JSONDecode(readfile("Manake Hub Premium Scripts/Blox Fruits/" .. game.Players.LocalPlayer.Name .. ".json"))
			for i,v in pairs(Decode) do
				_G.Settings[i] = v
			end
		end
	else
		return warn("Status : Undetected Executor")
	end
end

function SaveSettings()
	if readfile and writefile and isfile and isfolder then
		if not isfile("Manake Hub Premium Scripts/Blox Fruits/" .. game.Players.LocalPlayer.Name .. ".json") then
			LoadSettings()
		else
			local Decode = game:GetService("HttpService"):JSONDecode(readfile("Manake Hub Premium Scripts/Blox Fruits/" .. game.Players.LocalPlayer.Name .. ".json"))
			local Array = {}
			for i,v in pairs(_G.Settings) do
				Array[i] = v
			end
			writefile("Manake Hub Premium Scripts/Blox Fruits/" .. game.Players.LocalPlayer.Name .. ".json", game:GetService("HttpService"):JSONEncode(Array))
		end
	else
		return warn("Status : Undetected Executor")
	end
end

LoadSettings()

function FPSBooster()
	local decalsyeeted = true
	local g = game
	local w = g.Workspace
	local l = g.Lighting
	local t = w.Terrain
	sethiddenproperty(l,"Technology",2)
	sethiddenproperty(t,"Decoration",false)
	t.WaterWaveSize = 0
	t.WaterWaveSpeed = 0
	t.WaterReflectance = 0
	t.WaterTransparency = 0
	l.GlobalShadows = false
	l.FogEnd = 9e9
	l.Brightness = 0
	settings().Rendering.QualityLevel = "Level01"
	for i, v in pairs(g:GetDescendants()) do
		if v:IsA("Part") or v:IsA("Union") or v:IsA("CornerWedgePart") or v:IsA("TrussPart") then
			v.Material = "Plastic"
			v.Reflectance = 0
		elseif v:IsA("Decal") or v:IsA("Texture") and decalsyeeted then
			v.Transparency = 1
		elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
			v.Lifetime = NumberRange.new(0)
		elseif v:IsA("Explosion") then
			v.BlastPressure = 1
			v.BlastRadius = 1
		elseif v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles") then
			v.Enabled = false
		elseif v:IsA("MeshPart") then
			v.Material = "Plastic"
			v.Reflectance = 0
			v.TextureID = 10385902758728957
		end
	end
	for i, e in pairs(l:GetChildren()) do
		if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
			e.Enabled = false
		end
	end
end

function ClickTpTool()
	local plr = game:GetService("Players").LocalPlayer
	local mouse = plr:GetMouse()
	local tool = Instance.new("Tool")
	tool.RequiresHandle = false
	tool.Name = "Teleport Tool"
	tool.Activated:Connect(function()
		local root = plr.Character.HumanoidRootPart
		local pos = mouse.Hit.Position+Vector3.new(0,2.5,0)
		local offset = pos-root.Position
		root.CFrame = root.CFrame+offset
	end)
	tool.Parent = plr.Backpack
end


function GetMaterial(matname)
	for i,v in pairs(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventory")) do
		if type(v) == "table" then
			if v.Type == "Material" then
				if v.Name == matname then
					return v.Count
				end
			end
		end
	end
	return 0
end

function GetWeaponInventory(Weaponname)
	for i,v in pairs(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventory")) do
		if type(v) == "table" then
			if v.Type == "Sword" then
				if v.Name == Weaponname then
					return true
				end
			end
		end
	end
	return false
end

getgenv().ToTarget = function(Pos)
	local r = game:GetService("Players").LocalPlayer
	local xTweenPosition = {}
	if not game.Players.LocalPlayer.Character:FindFirstChild("Root")then 
		local K = Instance.new("Part",game.Players.LocalPlayer.Character) -- Create part
		K.Size = Vector3.new(20,0.5,20)
		K.Name = "Root"
		K.Anchored = true
		K.Transparency = 1
		K.CanCollide = false
		K.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame*CFrame.new(0,0.6,0) --spawn at player
	end
	local Tween_Service = game:service"TweenService"
	local TweenPosition = (Pos.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude -- diatance 
	local Magnitude=TweenInfo.new((game:GetService("Players")["LocalPlayer"].Character.Root.Position-Pos.Position).Magnitude/200,Enum.EasingStyle.Linear) -- Create Tween
	local function PartToPlayers() --teleport parta to player
		game.Players.LocalPlayer.Character.Root.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
	end

	local function PlayersToPart() -- teleport player to part
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.Root.CFrame
	end

	function xTweenPosition:Stop() --stop tween
		tween:Cancel()
		game.Players.LocalPlayer.Character["Root"]:Destroy()
		return tween
	end

	if TweenPosition <= 0 then
		pcall(function()
			tween:Cancel()
			game.Players.LocalPlayer.Character.Root.CFrame = Pos
			game.Players.LocalPlayer.Character["Root"]:Destroy()
		end)
	end

	task.spawn(function()
		while wait() do -- or RenderStepped
			pcall(function()
				PlayersToPart()
				if(game.Players.LocalPlayer.Character.Root.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude >= 1 then
					PartToPlayers()
				elseif (Pos.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1 then
					game.Players.LocalPlayer.Character["Root"]:Destroy()
				end
			end)
		end
	end)
	if game.Players.LocalPlayer.Character:WaitForChild("Humanoid").Health <= 0 then 
		if tween then 
			tween:Cancel()
			game.Players.LocalPlayer.Character["Root"]:Destroy()
		end 
		repeat wait() until game.Players.LocalPlayer.Character:WaitForChild("Humanoid").Health > 0; wait(0.2)
	end

	local tween,error = pcall(function()
		tween=Tween_Service:Create(
			game.Players.LocalPlayer.Character["Root"],Magnitude,{CFrame=Pos})
		tween:Play() 
	end)
	if not tween then return error end

	return xTweenPosition
end




function AutoHaki()
	if not game:GetService("Players").LocalPlayer.Character:FindFirstChild("HasBuso") then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
	end
end

function EquipWeapon(ToolSe)
	if not _G.NotAutoEquip then
		if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
			local Tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
			wait(.1)
			game.Players.LocalPlayer.Character.Humanoid:EquipTool(Tool)
		end
	end
end


local function GetIsLand(...)
	local RealtargetPos = {...}
	local targetPos = RealtargetPos[1]
	local RealTarget
	if type(targetPos) == "vector" then
		RealTarget = targetPos
	elseif type(targetPos) == "userdata" then
		RealTarget = targetPos.Position
	elseif type(targetPos) == "number" then
		RealTarget = CFrame.new(unpack(RealtargetPos))
		RealTarget = RealTarget.p
	end

	local ReturnValue
	local CheckInOut = math.huge;
	if game.Players.LocalPlayer.Team then
		for i,v in pairs(game.Workspace._WorldOrigin.PlayerSpawns:FindFirstChild(tostring(game.Players.LocalPlayer.Team)):GetChildren()) do 
			local ReMagnitude = (RealTarget - v:GetModelCFrame().p).Magnitude;
			if ReMagnitude < CheckInOut then
				CheckInOut = ReMagnitude;
				ReturnValue = v.Name
			end
		end
		if ReturnValue then
			return ReturnValue
		end 
	end
end

--BTP
function BTP(P)
	repeat wait(1)
		game.Players.LocalPlayer.Character.Humanoid:ChangeState(15)
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = P
		task.wait()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = P
	until (P.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1500
end

function Com(com,...)
	local Remote = game:GetService('ReplicatedStorage').Remotes:FindFirstChild("Comm"..com)
	if Remote:IsA("RemoteEvent") then
		Remote:FireServer(...)
	elseif Remote:IsA("RemoteFunction") then
		Remote:InvokeServer(...)
	end
end

function Hop()
	local PlaceID = game.PlaceId
	local AllIDs = {}
	local foundAnything = ""
	local actualHour = os.date("!*t").hour
	local Deleted = false
	function TPReturner()
		local Site;
		if foundAnything == "" then
			Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
		else
			Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
		end
		local ID = ""
		if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
			foundAnything = Site.nextPageCursor
		end
		local num = 0;
		for i,v in pairs(Site.data) do
			local Possible = true
			ID = tostring(v.id)
			if tonumber(v.maxPlayers) > tonumber(v.playing) then
				for _,Existing in pairs(AllIDs) do
					if num ~= 0 then
						if ID == tostring(Existing) then
							Possible = false
						end
					else
						if tonumber(actualHour) ~= tonumber(Existing) then
							local delFile = pcall(function()
								AllIDs = {}
								table.insert(AllIDs, actualHour)
							end)
						end
					end
					num = num + 1
				end
				if Possible == true then
					table.insert(AllIDs, ID)
					wait()
					pcall(function()
						wait()
						game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
					end)
					wait(4)
				end
			end
		end
	end
	function Teleport() 
		while wait() do
			pcall(function()
				TPReturner()
				if foundAnything ~= "" then
					TPReturner()
				end
			end)
		end
	end
	Teleport()
end


spawn(function()
	while task.wait() do
		pcall(function()
			if _G.Auto_Farm_Level or _G.Auto_Farm_Mob_Aura or _G.Auto_New_World or _G.Auto_Farm_BF_Mastery or _G.Auto_Farm_Gun_Mastery or _G.Auto_Third_World or _G.AutoFarmChest or _G.Start_Tween_Island or _G.Auto_Farm_Boss or _G.Auto_Elite_Hunter or _G.Auto_Cake_Prince or _G.Auto_Farm_All_Boss or _G.AutoSaber or _G.Auto_Pole or _G.Auto_Factory_Farm or _G.Auto_Farm_Ectoplasm or _G.Auto_Bartilo_Quest or _G.Auto_Rengoku or _G.Auto_Evo_Race_V2 or _G.Auto_Swan_Glasses or _G.Auto_Dragon_Trident or _G.Auto_Farm_Bone or  _G.Auto_Rainbow_Haki or _G.Auto_Holy_Torch or _G.Auto_Canvander or _G.Auto_Twin_Hook or _G.Auto_Serpent_Bow or _G.AutoFarmMaterial or _G.Auto_Fully_Death_Step or _G.Auto_Fully_SharkMan_Karate or _G.Teleport_to_Player or _G.Auto_Kill_Player_Melee or _G.Auto_Kill_Player_Gun or _G.Auto_Next_Island or _G.AutoFarmSelectMonster or _G.Auto_Factory_Farm or _G.Auto_Tushita or _G.Auto_Yama or _G.Auto_Kill_Law or _G.Auto_Soul_Guitar or _G.Auto_Farm_Chest_Fast then
				if not game:GetService("Players").LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
					local Noclip = Instance.new("BodyVelocity")
					Noclip.Name = "BodyClip"
					Noclip.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
					Noclip.MaxForce = Vector3.new(100000,100000,100000)
					Noclip.Velocity = Vector3.new(0,0,0)
				end
			else
				game:GetService("Players").LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip"):Destroy()
			end
		end)
	end
end)

spawn(function()
	local Methodnow = 1
	while wait(1) do
		if _G.Method then
			if Methodnow == 1 then
				Methodnow = 2
				MethodFarm = CFrame.new(40, 35, 0) -- เคลื่อนที่ไปทางด้านขวา
			elseif Methodnow == 2 then
				Methodnow = 3
				MethodFarm = CFrame.new(0, 35, 30) -- เคลื่อนที่ไปทางด้านหลัง
			elseif Methodnow == 3 then 
				Methodnow = 4
				MethodFarm = CFrame.new(-40, 35, 0) -- เคลื่อนที่ไปทางด้านซ้าย
			else
				Methodnow = 1
				MethodFarm = CFrame.new(0, 35, -40) -- เคลื่อนที่ไปทางด้านหน้า
			end
		else
			MethodFarm = CFrame.new(0, 35, 0)
		end
	end
end)

function CheckBossQuest()
	if _G.Select_Boss == "Saber Expert [Lv. 200] [Boss]" then
		MsBoss = "Saber Expert [Lv. 200] [Boss]"
		NameBoss = "Saber Expert"
		CFrameBoss = CFrame.new(-1458.89502, 29.8870335, -50.633564, 0.858821094, 1.13848939e-08, 0.512275636, -4.85649254e-09, 1, -1.40823326e-08, -0.512275636, 9.6063415e-09, 0.858821094)
	elseif _G.Select_Boss == "The Saw [Lv. 100] [Boss]" then
		MsBoss = "The Saw [Lv. 100] [Boss]"
		NameBoss = "The Saw"
		CFrameBoss = CFrame.new(-683.519897, 13.8534927, 1610.87854, -0.290192783, 6.88365773e-08, 0.956968188, 6.98413629e-08, 1, -5.07531119e-08, -0.956968188, 5.21077759e-08, -0.290192783)
	elseif _G.Select_Boss == "Greybeard [Lv. 750] [Raid Boss]" then
		MsBoss = "Greybeard [Lv. 750] [Raid Boss]"
		NameBoss = "Greybeard"
		CFrameBoss = CFrame.new(-4955.72949, 80.8163834, 4305.82666, -0.433646321, -1.03394289e-08, 0.901083171, -3.0443168e-08, 1, -3.17633075e-09, -0.901083171, -2.88092288e-08, -0.433646321)
	elseif _G.Select_Boss == "The Gorilla King [Lv. 25] [Boss]" then
		MsBoss = "The Gorilla King [Lv. 25] [Boss]"
		NameBoss = "The Gorilla King"
		NameQuestBoss = "JungleQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
		CFrameBoss = CFrame.new(-1223.52808, 6.27936459, -502.292664, 0.310949147, -5.66602516e-08, 0.950426519, -3.37275488e-08, 1, 7.06501808e-08, -0.950426519, -5.40241736e-08, 0.310949147)
	elseif _G.Select_Boss == "Bobby [Lv. 55] [Boss]" then
		MsBoss = "Bobby [Lv. 55] [Boss]"
		NameBoss = "Bobby"
		NameQuestBoss = "BuggyQuest1"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
		CFrameBoss = CFrame.new(-1147.65173, 32.5966301, 4156.02588, 0.956680477, -1.77109952e-10, -0.29113996, 5.16530874e-10, 1, 1.08897802e-09, 0.29113996, -1.19218679e-09, 0.956680477)
	elseif _G.Select_Boss == "Yeti [Lv. 110] [Boss]" then
		MsBoss = "Yeti [Lv. 110] [Boss]"
		NameBoss = "Yeti"
		NameQuestBoss = "SnowQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(1384.90247, 87.3078308, -1296.6825, 0.280209213, 2.72035177e-08, -0.959938943, -6.75690828e-08, 1, 8.6151708e-09, 0.959938943, 6.24481444e-08, 0.280209213)
		CFrameBoss = CFrame.new(1221.7356, 138.046906, -1488.84082, 0.349343032, -9.49245944e-08, 0.936994851, 6.29478194e-08, 1, 7.7838429e-08, -0.936994851, 3.17894653e-08, 0.349343032)
	elseif _G.Select_Boss == "Mob Leader [Lv. 120] [Boss]" then
		MsBoss = "Mob Leader [Lv. 120] [Boss]"
		NameBoss = "Mob Leader"
		CFrameBoss = CFrame.new(-2848.59399, 7.4272871, 5342.44043, -0.928248107, -8.7248246e-08, 0.371961564, -7.61816636e-08, 1, 4.44474857e-08, -0.371961564, 1.29216433e-08, -0.92824)
	elseif _G.Select_Boss == "Vice Admiral [Lv. 130] [Boss]" then
		MsBoss = "Vice Admiral [Lv. 130] [Boss]"
		NameBoss = "Vice Admiral"
		NameQuestBoss = "MarineQuest2"
		LevelQuestBoss = 2
		CFrameQuestBoss = CFrame.new(-5035.42285, 28.6520386, 4324.50293, -0.0611100644, -8.08395768e-08, 0.998130739, -1.57416586e-08, 1, 8.00271849e-08, -0.998130739, -1.08217701e-08, -0.0611100644)
		CFrameBoss = CFrame.new(-5078.45898, 99.6520691, 4402.1665, -0.555574954, -9.88630566e-11, 0.831466436, -6.35508286e-08, 1, -4.23449258e-08, -0.831466436, -7.63661632e-08, -0.555574954)
	elseif _G.Select_Boss == "Warden [Lv. 175] [Boss]" then
		MsBoss = "Warden [Lv. 175] [Boss]"
		NameBoss = "Warden"
		NameQuestBoss = "ImpelQuest"
		LevelQuestBoss = 1
		CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
		CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
	elseif _G.Select_Boss == "Chief Warden [Lv. 200] [Boss]" then
		MsBoss = "Chief Warden [Lv. 200] [Boss]"
		NameBoss = "Chief Warden"
		NameQuestBoss = "ImpelQuest"
		LevelQuestBoss = 2
		CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
		CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
	elseif _G.Select_Boss == "Swan [Lv. 225] [Boss]" then
		MsBoss = "Swan [Lv. 225] [Boss]"
		NameBoss = "Swan"
		NameQuestBoss = "ImpelQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
		CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
	elseif _G.Select_Boss == "Magma Admiral [Lv. 350] [Boss]" then
		MsBoss = "Magma Admiral [Lv. 350] [Boss]"
		NameBoss = "Magma Admiral"
		NameQuestBoss = "MagmaQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-5317.07666, 12.2721891, 8517.41699, 0.51175487, -2.65508806e-08, -0.859131515, -3.91131572e-08, 1, -5.42026761e-08, 0.859131515, 6.13418294e-08, 0.51175487)
		CFrameBoss = CFrame.new(-5530.12646, 22.8769703, 8859.91309, 0.857838571, 2.23414389e-08, 0.513919294, 1.53689133e-08, 1, -6.91265853e-08, -0.513919294, 6.71978384e-08, 0.857838571)
	elseif _G.Select_Boss == "Fishman Lord [Lv. 425] [Boss]" then
		MsBoss = "Fishman Lord [Lv. 425] [Boss]"
		NameBoss = "Fishman Lord"
		NameQuestBoss = "FishmanQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(61123.0859, 18.5066795, 1570.18018, 0.927145958, 1.0624845e-07, 0.374700129, -6.98219367e-08, 1, -1.10790765e-07, -0.374700129, 7.65569368e-08, 0.927145958)
		CFrameBoss = CFrame.new(61351.7773, 31.0306778, 1113.31409, 0.999974668, 0, -0.00714713801, 0, 1.00000012, 0, 0.00714714266, 0, 0.999974549)
	elseif _G.Select_Boss == "Wysper [Lv. 500] [Boss]" then
		MsBoss = "Wysper [Lv. 500] [Boss]"
		NameBoss = "Wysper"
		NameQuestBoss = "SkyExp1Quest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-7862.94629, 5545.52832, -379.833954, 0.462944925, 1.45838088e-08, -0.886386991, 1.0534996e-08, 1, 2.19553424e-08, 0.886386991, -1.95022007e-08, 0.462944925)
		CFrameBoss = CFrame.new(-7925.48389, 5550.76074, -636.178345, 0.716468513, -1.22915289e-09, 0.697619379, 3.37381434e-09, 1, -1.70304748e-09, -0.697619379, 3.57381835e-09, 0.716468513)
	elseif _G.Select_Boss == "Thunder God [Lv. 575] [Boss]" then
		MsBoss = "Thunder God [Lv. 575] [Boss]"
		NameBoss = "Thunder God"
		NameQuestBoss = "SkyExp2Quest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-7902.78613, 5635.99902, -1411.98706, -0.0361216255, -1.16895912e-07, 0.999347389, 1.44533963e-09, 1, 1.17024491e-07, -0.999347389, 5.6715117e-09, -0.0361216255)
		CFrameBoss = CFrame.new(-7917.53613, 5616.61377, -2277.78564, 0.965189934, 4.80563429e-08, -0.261550069, -6.73089886e-08, 1, -6.46515304e-08, 0.261550069, 8.00056768e-08, 0.965189934)
	elseif _G.Select_Boss == "Cyborg [Lv. 675] [Boss]" then
		MsBoss = "Cyborg [Lv. 675] [Boss]"
		NameBoss = "Cyborg"
		NameQuestBoss = "FountainQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(5253.54834, 38.5361786, 4050.45166, -0.0112687312, -9.93677887e-08, -0.999936521, 2.55291371e-10, 1, -9.93769547e-08, 0.999936521, -1.37512213e-09, -0.0112687312)
		CFrameBoss = CFrame.new(6041.82813, 52.7112198, 3907.45142, -0.563162148, 1.73805248e-09, -0.826346457, -5.94632716e-08, 1, 4.26280238e-08, 0.826346457, 7.31437524e-08, -0.563162148)
		-- New World
	elseif _G.Select_Boss == "Diamond [Lv. 750] [Boss]" then
		MsBoss = "Diamond [Lv. 750] [Boss]"
		NameBoss = "Diamond"
		NameQuestBoss = "Area1Quest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
		CFrameBoss = CFrame.new(-1736.26587, 198.627731, -236.412857, -0.997808516, 0, -0.0661673471, 0, 1, 0, 0.0661673471, 0, -0.997808516)
	elseif _G.Select_Boss == "Jeremy [Lv. 850] [Boss]" then
		MsBoss = "Jeremy [Lv. 850] [Boss]"
		NameBoss = "Jeremy"
		NameQuestBoss = "Area2Quest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
		CFrameBoss = CFrame.new(2203.76953, 448.966034, 752.731079, -0.0217453763, 0, -0.999763548, 0, 1, 0, 0.999763548, 0, -0.0217453763)
	elseif _G.Select_Boss == "Fajita [Lv. 925] [Boss]" then
		MsBoss = "Fajita [Lv. 925] [Boss]"
		NameBoss = "Fajita"
		NameQuestBoss = "MarineQuest3"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
		CFrameBoss = CFrame.new(-2297.40332, 115.449463, -3946.53833, 0.961227536, -1.46645796e-09, -0.275756449, -2.3212845e-09, 1, -1.34094433e-08, 0.275756449, 1.35296352e-08, 0.961227536)
	elseif _G.Select_Boss == "Don Swan [Lv. 1000] [Boss]" then
		MsBoss = "Don Swan [Lv. 1000] [Boss]"
		NameBoss = "Don Swan"
		CFrameBoss = CFrame.new(2288.802, 15.1870775, 863.034607, 0.99974072, -8.41247214e-08, -0.0227668174, 8.4774733e-08, 1, 2.75850098e-08, 0.0227668174, -2.95079072e-08, 0.99974072)
	elseif _G.Select_Boss == "Smoke Admiral [Lv. 1150] [Boss]" then
		MsBoss = "Smoke Admiral [Lv. 1150] [Boss]"
		NameBoss = "Smoke Admiral"
		NameQuestBoss = "IceSideQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-6059.96191, 15.9868021, -4904.7373, -0.444992423, -3.0874483e-09, 0.895534337, -3.64098796e-08, 1, -1.4644522e-08, -0.895534337, -3.91229982e-08, -0.444992423)
		CFrameBoss = CFrame.new(-5115.72754, 23.7664986, -5338.2207, 0.251453817, 1.48345061e-08, -0.967869282, 4.02796978e-08, 1, 2.57916977e-08, 0.967869282, -4.54708946e-08, 0.251453817)
	elseif _G.Select_Boss == "Cursed Captain [Lv. 1325] [Raid Boss]" then
		MsBoss = "Cursed Captain [Lv. 1325] [Raid Boss]"
		NameBoss = "Cursed Captain"
		CFrameBoss = CFrame.new(916.928589, 181.092773, 33422, -0.999505103, 9.26310495e-09, 0.0314563364, 8.42916226e-09, 1, -2.6643713e-08, -0.0314563364, -2.63653774e-08, -0.999505103)
	elseif _G.Select_Boss == "Darkbeard [Lv. 1000] [Raid Boss]" then
		MsBoss = "Darkbeard [Lv. 1000] [Raid Boss]"
		NameBoss = "Darkbeard"
		CFrameBoss = CFrame.new(3876.00366, 24.6882591, -3820.21777, -0.976951957, 4.97356325e-08, 0.213458836, 4.57335361e-08, 1, -2.36868622e-08, -0.213458836, -1.33787044e-08, -0.976951957)
	elseif _G.Select_Boss == "Order [Lv. 1250] [Raid Boss]" then
		MsBoss = "Order [Lv. 1250] [Raid Boss]"
		NameBoss = "Order"
		CFrameBoss = CFrame.new(-6221.15039, 16.2351036, -5045.23584, -0.380726993, 7.41463495e-08, 0.924687505, 5.85604774e-08, 1, -5.60738549e-08, -0.924687505, 3.28013137e-08, -0.380726993)
	elseif _G.Select_Boss == "Awakened Ice Admiral [Lv. 1400] [Boss]" then
		MsBoss = "Awakened Ice Admiral [Lv. 1400] [Boss]"
		NameBoss = "Awakened Ice Admiral"
		NameQuestBoss = "FrostQuest"
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(5669.33203, 28.2118053, -6481.55908, 0.921275556, -1.25320829e-08, 0.388910472, 4.72230788e-08, 1, -7.96414241e-08, -0.388910472, 9.17372489e-08, 0.921275556)
		CFrameBoss = CFrame.new(6407.33936, 340.223785, -6892.521, 0.49051559, -5.25310213e-08, -0.871432424, -2.76146022e-08, 1, -7.58250565e-08, 0.871432424, 6.12576301e-08, 0.49051559)
	elseif _G.Select_Boss == "Tide Keeper [Lv. 1475] [Boss]" then
		MsBoss = "Tide Keeper [Lv. 1475] [Boss]"
		NameBoss = "Tide Keeper"
		NameQuestBoss = "ForgottenQuest"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-3053.89648, 236.881363, -10148.2324, -0.985987961, -3.58504737e-09, 0.16681771, -3.07832915e-09, 1, 3.29612559e-09, -0.16681771, 2.73641976e-09, -0.985987961)
		CFrameBoss = CFrame.new(-3570.18652, 123.328949, -11555.9072, 0.465199202, -1.3857326e-08, 0.885206044, 4.0332897e-09, 1, 1.35347511e-08, -0.885206044, -2.72606271e-09, 0.465199202)
		-- Thire World
	elseif _G.Select_Boss == "Stone [Lv. 1550] [Boss]" then
		MsBoss = "Stone [Lv. 1550] [Boss]"
		NameBoss = "Stone"
		NameQuestBoss = "PiratePortQuest"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-290, 44, 5577)
		CFrameBoss = CFrame.new(-1085, 40, 6779)
	elseif _G.Select_Boss == "Island Empress [Lv. 1675] [Boss]" then
		MsBoss = "Island Empress [Lv. 1675] [Boss]"
		NameBoss = "Island Empress"
		NameQuestBoss = "AmazonQuest2"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(5443, 602, 752)
		CFrameBoss = CFrame.new(5659, 602, 244)
	elseif _G.Select_Boss == "Kilo Admiral [Lv. 1750] [Boss]" then
		MsBoss = "Kilo Admiral [Lv. 1750] [Boss]"
		NameBoss = "Kilo Admiral"
		NameQuestBoss = "MarineTreeIsland"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(2178, 29, -6737)
		CFrameBoss =CFrame.new(2846, 433, -7100)
	elseif _G.Select_Boss == "Captain Elephant [Lv. 1875] [Boss]" then
		MsBoss = "Captain Elephant [Lv. 1875] [Boss]"
		NameBoss = "Captain Elephant"
		NameQuestBoss = "DeepForestIsland"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-13232, 333, -7631)
		CFrameBoss = CFrame.new(-13221, 325, -8405)
	elseif _G.Select_Boss == "Beautiful Pirate [Lv. 1950] [Boss]" then
		MsBoss = "Beautiful Pirate [Lv. 1950] [Boss]"
		NameBoss = "Beautiful Pirate"
		NameQuestBoss = "DeepForestIsland2"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-12686, 391, -9902)
		CFrameBoss = CFrame.new(5182, 23, -20)
	elseif _G.Select_Boss == "Cake Queen [Lv. 2175] [Boss]" then
		MsBoss = "Cake Queen [Lv. 2175] [Boss]"
		NameBoss = "Cake Queen"
		NameQuestBoss = "IceCreamIslandQuest"             
		LevelQuestBoss = 3
		CFrameQuestBoss = CFrame.new(-716, 382, -11010)
		CFrameBoss = CFrame.new(-821, 66, -10965)
	elseif _G.Select_Boss == "rip_indra True Form [Lv. 5000] [Raid Boss]" then
		MsBoss = "rip_indra True Form [Lv. 5000] [Raid Boss]"
		NameBoss = "rip_indra True Form"
		CFrameBoss = CFrame.new(-5359, 424, -2735)
	elseif _G.Select_Boss == "Longma [Lv. 2000] [Boss]" then
		MsBoss = "Longma [Lv. 2000] [Boss]"
		NameBoss = "Longma"
		CFrameBoss = CFrame.new(-10248.3936, 353.79129, -9306.34473)
	elseif _G.Select_Boss == "Soul Reaper [Lv. 2100] [Raid Boss]" then
		MsBoss = "Soul Reaper [Lv. 2100] [Raid Boss]"
		NameBoss = "Soul Reaper"
		CFrameBoss = CFrame.new(-9515.62109, 315.925537, 6691.12012)
	end
end

-----------------------------------------------------------------------------------------------------------------

local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
local SaveManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/dawid-scripts/Fluent/master/Addons/SaveManager.lua"))()
local InterfaceManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/dawid-scripts/Fluent/master/Addons/InterfaceManager.lua"))()

local Window = Fluent:CreateWindow({
	Title = "Manake Hub",
	SubTitle = "| Back in 6 months "..os.date('%A, %B %d %Y'),
	TabWidth = 160,
	Size = UDim2.fromOffset(600, 400),
	Acrylic = true,
	Theme = "Darker",
	MinimizeKey = Enum.KeyCode.LeftControl
})

local Tabs = {
	Main = Window:AddTab({ Title = "General", Icon = "http://www.roblox.com/asset/?id=6026568198" }),
	Quest = Window:AddTab({ Title = "items / Quest", Icon = "http://www.roblox.com/asset/?id=6023426926" }),
	Stats = Window:AddTab({ Title = "Players / Stats", Icon = "http://www.roblox.com/asset/?id=7040410130" }),
	Dungeon = Window:AddTab({ Title = "Dungeon / Fruit", Icon = "http://www.roblox.com/asset/?id=7044284832" }),
	Teleport = Window:AddTab({ Title = "Teleport / Server", Icon = "http://www.roblox.com/asset/?id=6035190846" }),
	Misc = Window:AddTab({ Title = "Misc / Shop", Icon = "http://www.roblox.com/asset/?id=6031265976" }),
	Settings = Window:AddTab({ Title = "Settings / Function", Icon = "settings" })
}

local Options = Fluent.Options
local Toggle = Tabs.Main:AddToggle("Auto_Farm_Level", {Title = "Auto Farm Level", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Farm_Level = Options.Auto_Farm_Level.Value
	Auto_Farm_Level = Options.Auto_Farm_Level.Value
	if Options.Auto_Farm_Level.Value == false then
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
	SaveSettings()
end)

Options.Auto_Farm_Level:SetValue(_G.Auto_Farm_Level)


spawn(function()
	while wait() do
		if _G.Auto_Farm_Level then
			pcall(function()
				if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
					StartMagnet = false
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
				end
				if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
					StartMagnet = false
					CheckQuest()
					repeat wait() getgenv().ToTarget(CFrameQuest) until (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_Farm_Level
					if (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest",NameQuest,LevelQuest)
					end
				elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
					CheckQuest()
					if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
								if v.Name == Ms then
									repeat wait()
										if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
											EquipWeapon(_G.Select_Weapon)
											AutoHaki()
											PosMon = v.HumanoidRootPart.CFrame
											v.HumanoidRootPart.CanCollide = false
											v.Humanoid.WalkSpeed = 0
											v.Head.CanCollide = false
											v.HumanoidRootPart.Size = Vector3.new(50,50,50)
											StartMagnet = true
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										else
											StartMagnet = false
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
										end
									until not _G.Auto_Farm_Level or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
								end
							end
						end
					else
						StartMagnet = false
						if game:GetService("ReplicatedStorage"):FindFirstChild(Ms) then
							getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild(Ms).HumanoidRootPart.CFrame * MethodFarm)
						else	
							getgenv().ToTarget(CFrameMon)
						end
					end
				end
			end)
		end
	end
end)


local Toggle = Tabs.Main:AddToggle("Auto_Farm_Mob_Aura", {Title = "Auto Farm Mob Aura", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Farm_Mob_Aura = Options.Auto_Farm_Mob_Aura.Value
	if Options.Auto_Farm_Mob_Aura.Value == false then
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
	SaveSettings()
end)

Options.Auto_Farm_Mob_Aura:SetValue(_G.Auto_Farm_Mob_Aura)

task.spawn(function()
	while wait() do
		pcall(function()
			if _G.Auto_Farm_Mob_Aura then
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if _G.Auto_Farm_Mob_Aura and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 1000 then
						repeat wait()
							EquipWeapon(_G.Select_Weapon)
							AutoHaki()
							PosMonAura = v.HumanoidRootPart.CFrame
							v.HumanoidRootPart.Size = Vector3.new(60,60,60)
							v.Humanoid.JumpPower = 0
							v.Humanoid.WalkSpeed = 0
							v.HumanoidRootPart.CanCollide = false
							v.Humanoid:ChangeState(11)
							getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
						until not _G.Auto_Farm_Mob_Aura or not v.Parent or v.Humanoid.Health <= 0
					end
				end
			end
		end)
	end
end)

if World1 then

	Tabs.Main:AddSection("New World")

	local Toggle = Tabs.Main:AddToggle("Auto_New_World", {Title = "Auto New World", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_New_World = Options.Auto_New_World.Value
		if Options.Auto_New_World.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_New_World:SetValue(_G.Auto_New_World)

	spawn(function()
		while wait() do
			if _G.Auto_New_World then
				pcall(function()
					if game.Players.LocalPlayer.Data.Level.Value >= 700 and World1 then
						_G.Auto_Farm_Level = false
						if game.Workspace.Map.Ice.Door.CanCollide == true and game.Workspace.Map.Ice.Door.Transparency == 0 then
							repeat wait() getgenv().ToTarget(CFrame.new(4851.8720703125, 5.6514348983765, 718.47094726563)) until (CFrame.new(4851.8720703125, 5.6514348983765, 718.47094726563).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_New_World
							wait(1)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("DressrosaQuestProgress","Detective")
							EquipWeapon("Key")
							local pos2 = CFrame.new(1347.7124, 37.3751602, -1325.6488)
							repeat wait() getgenv().ToTarget(pos2) until (pos2.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_New_World
							wait(3)
						elseif game.Workspace.Map.Ice.Door.CanCollide == false and game.Workspace.Map.Ice.Door.Transparency == 1 then
							if game:GetService("Workspace").Enemies:FindFirstChild("Ice Admiral [Lv. 700] [Boss]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Ice Admiral [Lv. 700] [Boss]" and v.Humanoid.Health > 0 then
										repeat wait()
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											v.HumanoidRootPart.CanCollide = false
											v.HumanoidRootPart.Size = Vector3.new(60,60,60)
											v.HumanoidRootPart.Transparency = 1
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										until v.Humanoid.Health <= 0 or not v.Parent or not _G.Auto_New_World
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
									end
								end
							else
								getgenv().ToTarget(CFrame.new(1347.7124, 37.3751602, -1325.6488))
							end
						else
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
						end
					end
				end)
			end
		end
	end)

	Tabs.Main:AddSection("Other Funcrion")

	local Toggle = Tabs.Main:AddToggle("Auto_Saber", {Title = "Auto Saber", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Saber = Options.Auto_Saber.Value
		if _G.Auto_Saber == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Saber:SetValue(_G.Auto_Saber)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Saber and game.Players.LocalPlayer.Data.Level.Value >= 200 and not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Saber") and not game.Players.LocalPlayer.Character:FindFirstChild("Saber") then
					if Auto_Farm_Level then
						_G.Auto_Farm_Level = false
					end
					if game:GetService("Workspace").Map.Jungle.Final.Part.Transparency == 0 then
						if game:GetService("Workspace").Map.Jungle.QuestPlates.Door.Transparency == 0 then
							if (CFrame.new(-1612.55884, 36.9774132, 148.719543, 0.37091279, 3.0717151e-09, -0.928667724, 3.97099491e-08, 1, 1.91679348e-08, 0.928667724, -4.39869794e-08, 0.37091279).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 100 then
								getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
								wait(1)
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate1.Button.CFrame
								wait(1)
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate2.Button.CFrame
								wait(1)
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate3.Button.CFrame
								wait(1)
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate4.Button.CFrame
								wait(1)
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate5.Button.CFrame
								wait(1) 
							else
								if (CFrame.new(-1612.55884, 36.9774132, 148.719543, 0.37091279, 3.0717151e-09, -0.928667724, 3.97099491e-08, 1, 1.91679348e-08, 0.928667724, -4.39869794e-08, 0.37091279).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
									BTP(CFrame.new(-1612.55884, 36.9774132, 148.719543, 0.37091279, 3.0717151e-09, -0.928667724, 3.97099491e-08, 1, 1.91679348e-08, 0.928667724, -4.39869794e-08, 0.37091279))
									return
								end
								getgenv().ToTarget(CFrame.new(-1612.55884, 36.9774132, 148.719543, 0.37091279, 3.0717151e-09, -0.928667724, 3.97099491e-08, 1, 1.91679348e-08, 0.928667724, -4.39869794e-08, 0.37091279))
							end
						else
							if game:GetService("Workspace").Map.Desert.Burn.Part.Transparency == 0 then
								if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Torch") or game.Players.LocalPlayer.Character:FindFirstChild("Torch") then
									EquipWeapon("Torch")
									getgenv().ToTarget(CFrame.new(1114.61475, 5.04679728, 4350.22803, -0.648466587, -1.28799094e-09, 0.761243105, -5.70652914e-10, 1, 1.20584542e-09, -0.761243105, 3.47544882e-10, -0.648466587))
								else
									getgenv().ToTarget(CFrame.new(-1610.00757, 11.5049858, 164.001587, 0.984807551, -0.167722285, -0.0449818149, 0.17364943, 0.951244235, 0.254912198, 3.42372805e-05, -0.258850515, 0.965917408))                 
								end
							else
								if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") ~= 0 then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","GetCup")
									wait(0.5)
									EquipWeapon("Cup")
									wait(0.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","FillCup",game:GetService("Players").LocalPlayer.Character.Cup)
									wait(0)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") 
								else
									if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == nil then
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
									elseif  game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 0 then
										if game:GetService("Workspace").Enemies:FindFirstChild("Mob Leader [Lv. 120] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
											getgenv().ToTarget(CFrame.new(-2967.59521, -4.91089821, 5328.70703, 0.342208564, -0.0227849055, 0.939347804, 0.0251603816, 0.999569714, 0.0150796166, -0.939287126, 0.0184739735, 0.342634559))
											for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
												if v.Name == "Mob Leader [Lv. 120] [Boss]" then
													repeat wait()
														StartMagnet = true
														AutoHaki()
														EquipWeapon(_G.Select_Weapon)
														getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
														PosMon = v.HumanoidRootPart.CFrame
														v.HumanoidRootPart.Size = Vector3.new(60,60,60)
														v.Humanoid.JumpPower = 0
														v.Humanoid.WalkSpeed = 0
														v.HumanoidRootPart.CanCollide = false
														v.Humanoid:ChangeState(11)
													until v.Humanoid.Health <= 0 or _G.Auto_Saber == false
												end
											end
										end
									elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 1 then
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
										wait(0.5)
										EquipWeapon("Relic")
										wait(0.5)
										getgenv().ToTarget(CFrame.new(-1404.91504, 29.9773273, 3.80598116, 0.876514494, 5.66906877e-09, 0.481375456, 2.53851997e-08, 1, -5.79995607e-08, -0.481375456, 6.30572643e-08, 0.876514494))
									end
								end
							end
						end
					else
						if game:GetService("Workspace").Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
							getgenv().ToTarget(CFrame.new(-1401.85046, 29.9773273, 8.81916237, 0.85820812, 8.76083845e-08, 0.513301849, -8.55007443e-08, 1, -2.77243419e-08, -0.513301849, -2.00944328e-08, 0.85820812))
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Saber Expert [Lv. 200] [Boss]" then
									repeat wait()
										StartMagnet = true
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										PosMon = v.HumanoidRootPart.CFrame
										v.HumanoidRootPart.Size = Vector3.new(60,60,60)
										v.Humanoid.JumpPower = 0
										v.Humanoid.WalkSpeed = 0
										v.HumanoidRootPart.CanCollide = false
										v.Humanoid:ChangeState(11)
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
									until v.Humanoid.Health <= 0 or _G.Auto_Saber == false
									if v.Humanoid.Health <= 0 then
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","PlaceRelic")
									end
									_G.Auto_Farm_Level  = true
								end
							end
						end
					end
				end
			end)
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Pole", {Title = "Auto Pole", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Pole = Options.Auto_Pole.Value
		if Options.Auto_Pole.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Pole:SetValue(_G.Auto_Pole)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Pole then
					if game.ReplicatedStorage:FindFirstChild("Thunder God [Lv. 575] [Boss]") or game.Workspace.Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if v.Name == "Thunder God [Lv. 575] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
								repeat wait()
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
										Farmtween = getgenv().ToTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Farmtween then Farmtween:Stop() end
										StartMagnet = true
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										PosMon = v.HumanoidRootPart.CFrame
										v.HumanoidRootPart.Size = Vector3.new(60,60,60)
										v.Humanoid.JumpPower = 0
										v.Humanoid.WalkSpeed = 0
										v.HumanoidRootPart.CanCollide = false
										v.Humanoid:ChangeState(11)
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
									end
								until not _G.Auto_Pole or v.Humanoid.Health <= 0 or not v.Parent
								StartMagnet = false
							end
						end
					else
						Questtween = getgenv().ToTarget(CFrame.new(-7900.66406, 5606.90918, -2267.46436).Position,CFrame.new(-7900.66406, 5606.90918, -2267.46436))
						if (CFrame.new(-7900.66406, 5606.90918, -2267.46436).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
							if Questtween then
								Questtween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-7900.66406, 5606.90918, -2267.46436)
						end
					end
				end
			end)
		end
	end)

	Tabs.Main:AddSection("Auto Buy Ablility")

	local Toggle = Tabs.Main:AddToggle("Auto_Buy_Ablility", {Title = "Auto Buy Ablility", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Buy_Ablility = Options.Auto_Buy_Ablility.Value
		SaveSettings()
	end)

	Options.Auto_Buy_Ablility:SetValue(_G.Auto_Buy_Ablility)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Settings.Main["Auto Buy Ablility"] then
					local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
					local BusoCheck = false
					local SoruCheck = false
					local GeppoCheck = false
					local KenCheck = false
					if Beli >= 885000 then
						repeat wait() 
							local args = {
								[1] = "BuyHaki",
								[2] = "Buso"
							}

							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							BusoCheck = true
							local args = {
								[1] = "BuyHaki",
								[2] = "Geppo"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							GeppoCheck = true
							local args = {
								[1] = "BuyHaki",
								[2] = "Soru"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							SoruCheck = true
							local args = {
								[1] = "KenTalk",
								[2] = "Start"
							}

							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))

							local args = {
								[1] = "KenTalk",
								[2] = "Buy"
							}

							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							KenCheck = true
						until not BusoCheck and not GeppoCheck and not SoruCheck and not KenCheck or not _G.Settings.Main["Auto Buy Ablility"]
					end
				end
			end)
		end
	end)
end

Tabs.Main:AddSection("Boss")

local BossTable = {}

for i, v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
	if string.find(v.Name, "Boss") then
		if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
		else
			table.insert(BossTable, v.Name)
		end
	end
end


local Boss = Tabs.Main:AddDropdown("Boss", {
	Title = "Select Boss",
	Values = BossTable,
	Multi = false,
	Default = 1,
})

Boss:SetValue("Select Boss")

Boss:OnChanged(function(value)
	_G.Select_Boss = value
	SaveSettings()
end)


Tabs.Main:AddButton({
	Title = "Refresh Boss",
	Description = "Refresh Boss",
	Callback = function()
		table.clear(BossTable)
		for i, v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
			if string.find(v.Name, "Boss") then
				if v.Name == "Ice Admiral [Lv. 700] [Boss]" then

				else
					table.insert(BossTable, v.Name)
				end
			end
		end
	end
})


local Toggle = Tabs.Main:AddToggle("Auto_Farm_Boss", {Title = "Auto Farm Boss", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Farm_Boss = Options.Auto_Farm_Boss.Value
	if Options.Auto_Farm_Boss.Value == false then
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
	SaveSettings()
end)

Options.Auto_Farm_Boss:SetValue(_G.Auto_Farm_Boss)


local Toggle = Tabs.Main:AddToggle("Auto_Quest_Boss", {Title = "Auto Quest Boss", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Quest_Boss = Options.Auto_Quest_Boss.Value
	SaveSettings()
end)

Options.Auto_Quest_Boss:SetValue(_G.Auto_Quest_Boss)


spawn(function()
	while wait() do
		if _G.Auto_Farm_Boss then
			pcall(function()
				CheckBossQuest()
				if MsBoss == "Soul Reaper [Lv. 2100] [Raid Boss]" or MsBoss == "Longma [Lv. 2000] [Boss]" or MsBoss == "Don Swan [Lv. 1000] [Boss]" or MsBoss == "Cursed Captain [Lv. 1325] [Raid Boss]" or MsBoss == "Order [Lv. 1250] [Raid Boss]" or MsBoss == "rip_indra True Form [Lv. 5000] [Raid Boss]" then
					if game:GetService("Workspace").Enemies:FindFirstChild(MsBoss) then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == MsBoss then
								repeat wait()
									EquipWeapon(_G.Select_Weapon)
									AutoHaki()
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									v.HumanoidRootPart.CanCollide = false
									v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
								until _G.Auto_Farm_Boss == false or not v.Parent or v.Humanoid.Health <= 0
							end
						end
					else
						if (CFrameBoss.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
							BTP(CFrameBoss)
							return
						end
						getgenv().ToTarget(CFrameBoss)
					end
				else
					if _G.Auto_Quest_Boss then
						CheckBossQuest()
						if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameBoss) then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
						end
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
							repeat wait() getgenv().ToTarget(CFrameQuestBoss) until (CFrameQuestBoss.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_Farm_Boss
							if (CFrameQuestBoss.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4 then
								wait(1.1)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuestBoss, LevelQuestBoss)
							end
						elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
							if game:GetService("Workspace").Enemies:FindFirstChild(MsBoss) then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == MsBoss then
										repeat wait()
											if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameBoss) then
												EquipWeapon(_G.Select_Weapon)
												AutoHaki()
												getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
												v.HumanoidRootPart.CanCollide = false
												v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)									
											else
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
											end
										until _G.Auto_Farm_Boss == false or not v.Parent or v.Humanoid.Health <= 0
									end
								end
							else
								if (CFrameBoss.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
									BTP(CFrameBoss)
									return
								end
								getgenv().ToTarget(CFrameBoss)
							end
						end
					else
						if game:GetService("Workspace").Enemies:FindFirstChild(MsBoss) then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == MsBoss then
									repeat wait()
										EquipWeapon(_G.Select_Weapon)
										AutoHaki()
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)									
									until _G.Auto_Farm_Boss == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						else
							if (CFrameBoss.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
								BTP(CFrameBoss)
								return
							end
							getgenv().ToTarget(CFrameBoss)
						end
					end
				end
			end)
		end
	end
end)

local Toggle = Tabs.Main:AddToggle("Auto_Farm_All_Boss", {Title = "Auto Farm All Boss", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Farm_All_Boss = Options.Auto_Farm_All_Boss.Value
	if Options.Auto_Farm_All_Boss.Value == false then
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
	SaveSettings()
end)

Options.Auto_Farm_All_Boss:SetValue(_G.Auto_Farm_All_Boss)

spawn(function()
	while wait() do
		if _G.Auto_Farm_All_Boss then
			pcall(function()
				for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
					if string.find(v.Name,"Boss") then
						repeat task.wait()
							if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame)
							elseif v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
								AutoHaki()
								EquipWeapon(_G.Select_Weapon)
								v.Humanoid.WalkSpeed = 0
								v.HumanoidRootPart.CanCollide = false
								v.Head.CanCollide = false
								v.HumanoidRootPart.Size = Vector3.new(80,80,80)
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
								sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",math.huge)
							end
						until v.Humanoid.Health <= 0 or _G.Auto_Farm_All_Boss == false or not v.Parent
					end
				end
			end)
		end
	end
end)

Tabs.Main:AddSection("Mastery")

local Toggle = Tabs.Main:AddToggle("Auto_Farm_BF_Mastery", {Title = "Auto Farm BF Mastery", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Farm_BF_Mastery = Options.Auto_Farm_BF_Mastery.Value
	if Options.Auto_Farm_BF_Mastery.Value == false then
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
	SaveSettings()
end)

if _G.Auto_Farm_BF_Mastery == false then
	UseSkill = false 
end

Options.Auto_Farm_BF_Mastery:SetValue(_G.Auto_Farm_BF_Mastery)


spawn(function()
	while wait() do
		local MyLevel = game.Players.LocalPlayer.Data.Level.Value
		local QuestC = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest
		pcall(function()
			if _G.Auto_Farm_BF_Mastery and _G.Auto_Farm_Quest == true then
				if QuestC.Visible == true then
					if game:GetService("Workspace").Enemies:FindFirstChild(QuestCheck()[3]) then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == QuestCheck()[3] then
								if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
									HealthMs = v.Humanoid.MaxHealth * _G.Kill_At/100
									repeat task.wait()
										if v.Humanoid.Health <= HealthMs then
											AutoHaki()
											EquipWeapon(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
											v.HumanoidRootPart.CanCollide = false
											PosMonMasteryFruit = v.HumanoidRootPart.CFrame
											v.Humanoid.WalkSpeed = 0
											v.Head.CanCollide = false
											UseSkill = true
										else           
											UseSkill = false 
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
											v.HumanoidRootPart.CanCollide = false
											v.HumanoidRootPart.Size = Vector3.new(50,50,50)
											PosMonMasteryFruit = v.HumanoidRootPart.CFrame
											v.Humanoid.WalkSpeed = 0
											v.Head.CanCollide = false
										end
										StartMasteryFruitMagnet = true
									until not _G.Auto_Farm_BF_Mastery or not v.Parent or v.Humanoid.Health <= 0 or QuestC.Visible == false or not v:FindFirstChild("HumanoidRootPart")
								end
							end
						end
					else
						StartMasteryFruitMagnet = false   
						UseSkill = false 
						for i,v in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
							if v.Name == QuestCheck()[6] then local CFrameEnemySpawns = v.CFrame  wait(0.5)
								getgenv().ToTarget(CFrameEnemySpawns * MethodFarm)
							end
						end
					end
				else
					if (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
						BTP(QuestCheck()[2])
						return
					end
					repeat wait() getgenv().ToTarget(QuestCheck()[2]) until (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 0 or not _G.Auto_Farm_BF_Mastery
					if (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10 then
						BringMobFarm = false
						wait(0.2)
						game:GetService('ReplicatedStorage').Remotes.CommF_:InvokeServer("StartQuest", QuestCheck()[4], QuestCheck()[1]) wait(0.5)
					else
						repeat wait() getgenv().ToTarget(QuestCheck()[2]) until (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 0 or not _G.Auto_Farm_BF_Mastery
						for i,v in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
							if v.Name == QuestCheck()[6] then local CFrameEnemySpawns = v.CFrame  wait(0.5)
								getgenv().ToTarget(CFrameEnemySpawns * MethodFarm)
							end
						end
					end
				end
			else
				if game:GetService("Workspace").Enemies:FindFirstChild(QuestCheck()[3]) then
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if v.Name == QuestCheck()[3] then
							if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
								HealthMs = v.Humanoid.MaxHealth * _G.Kill_At/100
								repeat task.wait()
									if v.Humanoid.Health <= HealthMs then
										AutoHaki()
										EquipWeapon(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										v.HumanoidRootPart.CanCollide = false
										PosMonMasteryFruit = v.HumanoidRootPart.CFrame
										v.Humanoid.WalkSpeed = 0
										v.Head.CanCollide = false
										UseSkill = true
									else           
										UseSkill = false 
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(50,50,50)
										PosMonMasteryFruit = v.HumanoidRootPart.CFrame
										v.Humanoid.WalkSpeed = 0
										v.Head.CanCollide = false
									end
									StartMasteryFruitMagnet = true
								until not _G.Auto_Farm_BF_Mastery or not v.Parent or v.Humanoid.Health <= 0 or QuestC.Visible == false or not v:FindFirstChild("HumanoidRootPart")
							end
						end
					end
				else
					StartMasteryFruitMagnet = false   
					UseSkill = false 
					for i,v in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
						if v.Name == QuestCheck()[6] then local CFrameEnemySpawns = v.CFrame  wait(0.5)
							getgenv().ToTarget(CFrameEnemySpawns * MethodFarm)
						end
					end
				end
			end
		end)
	end
end)

spawn(function()
	while wait() do
		if UseSkill then
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if game:GetService("Players").LocalPlayer.Character:FindFirstChild(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value) then
						MasBF = game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Data.DevilFruit.Value].Level.Value
					elseif game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value) then
						MasBF = game:GetService("Players").LocalPlayer.Backpack[game:GetService("Players").LocalPlayer.Data.DevilFruit.Value].Level.Value
					end
					if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon-Dragon") then                      
						if _G.Skill_Z then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                        
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
						end
						if _G.Skill_X then          
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))               
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
						end
						if _G.Skill_C then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                          
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
							wait(2)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
						end
					elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Venom-Venom") then   
						if _G.Skill_Z then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                        
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
						end
						if _G.Skill_X then        
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))               
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
						end
						if _G.Skill_C then 
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                          
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
							wait(2)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
						end
					elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha") then
						if _G.Skill_Z and game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Size == Vector3.new(2, 2.0199999809265, 1) then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                         
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
						end
						if _G.Skill_X then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                           
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
						end
						if _G.Skill_C then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                           
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
						end
						if _G.Skill_V then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"V",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"V",false,game)
						end
					elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value) then
						if _G.Skill_Z then 
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                         
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
						end
						if _G.Skill_X then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                           
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
						end
						if _G.Skill_C then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))                           
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
						end
						if _G.Skill_V then
							local args = {
								[1] = PosMonMasteryFruit.Position
							}
							game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
							game:GetService("VirtualInputManager"):SendKeyEvent(true,"V",false,game)
							game:GetService("VirtualInputManager"):SendKeyEvent(false,"V",false,game)
						end
					end
				end
			end)
		end
	end
end)

spawn(function()
	game:GetService("RunService").RenderStepped:Connect(function()
		pcall(function()
			if UseSkill then
				for i,v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Notifications:GetChildren()) do
					if v.Name == "NotificationTemplate" then
						if string.find(v.Text,"Skill locked!") then
							v:Destroy()
						end
					end
				end
			end
		end)
	end)
end)

spawn(function()
	pcall(function()
		game:GetService("RunService").RenderStepped:Connect(function()
			if UseSkill then
				local args = {
					[1] = PosMonMasteryFruit.Position
				}
				game:GetService("Players").LocalPlayer.Character[game:GetService("Players").LocalPlayer.Data.DevilFruit.Value].RemoteEvent:FireServer(unpack(args))
			end
		end)
	end)
end)


local Toggle = Tabs.Main:AddToggle("Auto_Farm_Gun_Mastery", {Title = "Auto Farm Gun Mastery", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Farm_Gun_Mastery = Options.Auto_Farm_Gun_Mastery.Value
	if Options.Auto_Farm_Gun_Mastery.Value == false then
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
	SaveSettings()
end)

Options.Auto_Farm_Gun_Mastery:SetValue(_G.Auto_Farm_Gun_Mastery)

spawn(function()
	pcall(function()
		while wait() do
			for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do  
				if v:IsA("Tool") then
					if v:FindFirstChild("RemoteFunctionShoot") then 
						SelectWeaponGun = v.Name
					end
				end
			end
		end
	end)
end)

spawn(function()
	while wait() do
		local MyLevel = game.Players.LocalPlayer.Data.Level.Value
		local QuestC = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest
		pcall(function()
			if _G.Auto_Farm_Gun_Mastery and _G.Auto_Farm_Quest == true then
				if QuestC.Visible == true then
					if game:GetService("Workspace").Enemies:FindFirstChild(QuestCheck()[3]) then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == QuestCheck()[3] then
								if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
									repeat task.wait()
										if string.find(QuestC.Container.QuestTitle.Title.Text, QuestCheck()[6]) then
											HealthMin = v.Humanoid.MaxHealth * _G.Kill_At/100
											if v.Humanoid.Health <= HealthMin then                                                
												EquipWeapon(SelectWeaponGun)
												getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.CanCollide = false
												v.HumanoidRootPart.Size = Vector3.new(2,2,1)
												v.Head.CanCollide = false                                                
												local args = {
													[1] = v.HumanoidRootPart.Position,
													[2] = v.HumanoidRootPart
												}
												game:GetService("Players").LocalPlayer.Character[SelectWeaponGun].RemoteFunctionShoot:InvokeServer(unpack(args))
											else
												AutoHaki()
												EquipWeapon(_G.Select_Weapon)
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.CanCollide = false
												v.Head.CanCollide = false               
												v.HumanoidRootPart.Size = Vector3.new(50,50,50)
												getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
											end
											StartMasteryGunMagnet = true 
											PosMonMasteryGun = v.HumanoidRootPart.CFrame
										else
											StartMasteryGunMagnet = false
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
										end
									until not _G.Auto_Farm_Gun_Mastery or not v.Parent or v.Humanoid.Health <= 0 or QuestC.Visible == false or not v:FindFirstChild("HumanoidRootPart")
								end
							end
						end
					else
						for i,v in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
							if v.Name == QuestCheck()[6] then local CFrameEnemySpawns = v.CFrame  wait(0.5)
								getgenv().ToTarget(CFrameEnemySpawns * MethodFarm)
							end
						end
					end
				else
					if (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
						BTP(QuestCheck()[2])
						return
					end
					repeat wait() getgenv().ToTarget(QuestCheck()[2]) until (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 0 or not _G.Auto_Farm_Gun_Mastery
					if (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10 then
						BringMobFarm = false
						wait(0.2)
						game:GetService('ReplicatedStorage').Remotes.CommF_:InvokeServer("StartQuest", QuestCheck()[4], QuestCheck()[1]) wait(0.5)
					else
						repeat wait() getgenv().ToTarget(QuestCheck()[2]) until (QuestCheck()[2].Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 0 or not _G.Auto_Farm_Gun_Mastery
						for i,v in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
							if v.Name == QuestCheck()[6] then local CFrameEnemySpawns = v.CFrame  wait(0.5)
								getgenv().ToTarget(CFrameEnemySpawns * MethodFarm)
							end
						end
					end
				end
			else
				if game:GetService("Workspace").Enemies:FindFirstChild(QuestCheck()[3]) then
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if v.Name == QuestCheck()[3] then
							if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
								repeat task.wait()
									if string.find(QuestC.Container.QuestTitle.Title.Text, QuestCheck()[6]) then
										HealthMin = v.Humanoid.MaxHealth * _G.Kill_At/100
										if v.Humanoid.Health <= HealthMin then                                                
											EquipWeapon(SelectWeaponGun)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
											v.Humanoid.WalkSpeed = 0
											v.HumanoidRootPart.CanCollide = false
											v.HumanoidRootPart.Size = Vector3.new(2,2,1)
											v.Head.CanCollide = false                                                
											local args = {
												[1] = v.HumanoidRootPart.Position,
												[2] = v.HumanoidRootPart
											}
											game:GetService("Players").LocalPlayer.Character[SelectWeaponGun].RemoteFunctionShoot:InvokeServer(unpack(args))
										else
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											v.Humanoid.WalkSpeed = 0
											v.HumanoidRootPart.CanCollide = false
											v.Head.CanCollide = false               
											v.HumanoidRootPart.Size = Vector3.new(50,50,50)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										end
										StartMasteryGunMagnet = true 
										PosMonMasteryGun = v.HumanoidRootPart.CFrame
									else
										StartMasteryGunMagnet = false
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
									end
								until not _G.Auto_Farm_Gun_Mastery or not v.Parent or v.Humanoid.Health <= 0 or QuestC.Visible == false or not v:FindFirstChild("HumanoidRootPart")
							end
						end
					end
				else
					for i,v in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
						if v.Name == QuestCheck()[6] then local CFrameEnemySpawns = v.CFrame  wait(0.5)
							getgenv().ToTarget(CFrameEnemySpawns * MethodFarm)
						end
					end
				end
			end
		end)
	end
end)

local KillAT = Tabs.Main:AddDropdown("KillAT", {
	Title = "Select Kill AT",
	Values = {"10","15","20","25","30","35","40","45","50"},
	Multi = false,
	Default = 1,
})

KillAT:SetValue("25")

KillAT:OnChanged(function(Value)
	_G.Kill_At = Value
	SaveSettings()
end)

if World2 then
	Tabs.Main:AddSection("Auto Third World")

	local Toggle = Tabs.Main:AddToggle("Auto_Third_World", {Title = "Auto Third World", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Third_World = Options.Auto_Third_World.Value
		if Options.Auto_Third_World.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Third_World:SetValue(_G.Auto_Third_World)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Third_World then
					if game.Players.LocalPlayer.Data.Level.Value >= 1500 then
						if Auto_Farm_Level then
							_G.Auto_Farm_Level = false
						end
						if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 then
							if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetUnlockables").FlamingoAccess ~= nil then
								Com("F_","TravelZou")
								if game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("ZQuestProgress", "Check") == 0 then
									if game.Workspace.Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") then 	
										for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
											if v.Name == "rip_indra [Lv. 1500] [Boss]" and v:FindFirstChild("Humanoid")and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
												repeat wait()
													if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
														Farmtween = getgenv().ToTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
													elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
														if Farmtween then Farmtween:Stop() end
														AutoHaki()
														EquipWeapon(_G.Select_Weapon)
														PosMon = v.HumanoidRootPart.CFrame
														v.HumanoidRootPart.Size = Vector3.new(60,60,60)
														v.Humanoid.JumpPower = 0
														v.Humanoid.WalkSpeed = 0
														v.HumanoidRootPart.CanCollide = false
														v.Humanoid:ChangeState(11)
														getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
													end
												until not _G.Auto_Third_World or not v.Parent or v.Humanoid.Health <= 0 
												wait(.5)
												Check = 2
												repeat wait() Com("F_","TravelZou") until Check == 1
											end
										end
									else
										Com("F_","ZQuestProgress","Check")
										Com("F_","ZQuestProgress","Begin")
									end
								elseif game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("ZQuestProgress", "Check") == 1 then
									Com("F_","TravelZou")
								else
									if game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
										for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
											if v.Name == "Don Swan [Lv. 1000] [Boss]" and v:FindFirstChild("Humanoid")and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
												repeat wait()
													if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
														Farmtween = getgenv().ToTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
													elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
														if Farmtween then Farmtween:Stop() end
														AutoHaki()
														EquipWeapon(_G.Select_Weapon)
														PosMon = v.HumanoidRootPart.CFrame
														v.HumanoidRootPart.Size = Vector3.new(60,60,60)
														v.Humanoid.JumpPower = 0
														v.Humanoid.WalkSpeed = 0
														v.HumanoidRootPart.CanCollide = false
														v.Humanoid:ChangeState(11)
														getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
													end
												until not _G.Auto_Third_World or not v.Parent or v.Humanoid.Health <= 0 
											end
										end
									else
										if (CFrame.new(2288.802, 15.1870775, 863.034607).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
											BTP(CFrame.new(2288.802, 15.1870775, 863.034607))
											return
										end
										TweenDonSwanthireworld = getgenv().ToTarget(CFrame.new(2288.802, 15.1870775, 863.034607).Position,CFrame.new(2288.802, 15.1870775, 863.034607))
										if (CFrame.new(2288.802, 15.1870775, 863.034607).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if TweenDonSwanthireworld then
												TweenDonSwanthireworld:Stop()
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2288.802, 15.1870775, 863.034607)
											end
										end
									end
								end
							else
								if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetUnlockables").FlamingoAccess == nil then
									TabelDevilFruitStore = {}
									TabelDevilFruitOpen = {}

									for i,v in pairs(game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("getInventoryFruits")) do
										for i1,v1 in pairs(v) do
											if i1 == "Name" then 
												table.insert(TabelDevilFruitStore,v1)
											end
										end
									end

									for i,v in next,game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("GetFruits") do
										if v.Price >= 1000000 then  
											table.insert(TabelDevilFruitOpen,v.Name)
										end
									end

									for i,DevilFruitOpenDoor in pairs(TabelDevilFruitOpen) do
										for i1,DevilFruitStore in pairs(TabelDevilFruitStore) do
											if DevilFruitOpenDoor == DevilFruitStore and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetUnlockables").FlamingoAccess == nil then    
												if not game.Players.LocalPlayer.Backpack:FindFirstChild(DevilFruitStore) then   
													Com("F_","LoadFruit",DevilFruitStore)
												else
													Com("F_","TalkTrevor","1")
													Com("F_","TalkTrevor","2")
													Com("F_","TalkTrevor","3")
												end
											end
										end
									end

									Com("F_","TalkTrevor","1")
									Com("F_","TalkTrevor","2")
									Com("F_","TalkTrevor","3")	
								end
							end
						else
							if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 0 then
								if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Swan Pirates") and string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50") and game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
									if game.Workspace.Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
										for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
											if v.Name == "Swan Pirate [Lv. 775]" then
												pcall(function()
													repeat wait()
														if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
															Farmtween = getgenv().ToTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
														elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
															if Farmtween then Farmtween:Stop() end
															AutoHaki()
															EquipWeapon(_G.Select_Weapon)
															PosMon = v.HumanoidRootPart.CFrame
															v.HumanoidRootPart.Size = Vector3.new(60,60,60)
															v.Humanoid.JumpPower = 0
															v.Humanoid.WalkSpeed = 0
															v.HumanoidRootPart.CanCollide = false
															v.Humanoid:ChangeState(11)
															getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
														end
													until not v.Parent or v.Humanoid.Health <= 0 or _G.Auto_Third_World == false or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false
													StartMagnet = false
												end)
											end
										end
									else
										if (CFrame.new(1057.92761, 137.614319, 1242.08069).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
											BTP(CFrame.new(1057.92761, 137.614319, 1242.08069))
											return
										end
										Questtween = getgenv().ToTarget(CFrame.new(1057.92761, 137.614319, 1242.08069).Position,CFrame.new(1057.92761, 137.614319, 1242.08069))
										if (CFrame.new(1057.92761, 137.614319, 1242.08069).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if Bartilotween then Bartilotween:Stop() end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1057.92761, 137.614319, 1242.08069)
										end
									end
								else
									Bartilotween = getgenv().ToTarget(CFrame.new(-456.28952, 73.0200958, 299.895966).Position,CFrame.new(-456.28952, 73.0200958, 299.895966))
									if ( CFrame.new(-456.28952, 73.0200958, 299.895966).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Bartilotween then Bartilotween:Stop() end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =  CFrame.new(-456.28952, 73.0200958, 299.895966)
										Com("F_","StartQuest","BartiloQuest",1)
									end
								end
							elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 1 then
								if game.Workspace.Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
									for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
										if v.Name == "Jeremy [Lv. 850] [Boss]" then
											repeat wait()
												if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
													Farmtween = getgenv().ToTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
													if Farmtween then Farmtween:Stop() end
													AutoHaki()
													EquipWeapon(_G.Select_Weapon)
													PosMon = v.HumanoidRootPart.CFrame
													v.HumanoidRootPart.Size = Vector3.new(60,60,60)
													v.Humanoid.JumpPower = 0
													v.Humanoid.WalkSpeed = 0
													v.HumanoidRootPart.CanCollide = false
													v.Humanoid:ChangeState(11)															
													getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
												end
											until not v.Parent or v.Humanoid.Health <= 0 or _G.Auto_Third_World == false
										end
									end
								else
									if (CFrame.new(2099.88159, 448.931, 648.997375).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
										BTP(CFrame.new(2099.88159, 448.931, 648.997375))
										return
									end
									Bartilotween = getgenv().ToTarget(CFrame.new(2099.88159, 448.931, 648.997375).Position,CFrame.new(2099.88159, 448.931, 648.997375))
									if (CFrame.new(2099.88159, 448.931, 648.997375).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Bartilotween then Bartilotween:Stop() end
										game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2099.88159, 448.931, 648.997375)
									end
								end
							elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 2 then
								if (CFrame.new(-1836, 11, 1714).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									Bartilotween = getgenv().ToTarget(CFrame.new(-1836, 11, 1714).Position,CFrame.new(-1836, 11, 1714))
								elseif (CFrame.new(-1836, 11, 1714).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									if Bartilotween then Bartilotween:Stop() end
									game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1836, 11, 1714)
									wait(.5)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1850.49329, 13.1789551, 1750.89685)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.87305, 19.3777466, 1712.01807)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1803.94324, 16.5789185, 1750.89685)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.55835, 16.8604317, 1724.79541)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1869.54224, 15.987854, 1681.00659)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1800.0979, 16.4978027, 1684.52368)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1819.26343, 14.795166, 1717.90625)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1813.51843, 14.8604736, 1724.79541)
								end
							end
						end
					end
				end
			end)
		end
	end)

	Tabs.Main:AddSection("Rengoku")

	local Toggle = Tabs.Main:AddToggle("Auto_Rengoku", {Title = "Auto Rengoku", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Rengoku = Options.Auto_Rengoku.Value
		if Options.Auto_Rengoku.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Rengoku:SetValue(_G.Auto_Rengoku)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Rengoku then
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or game.Players.LocalPlayer.Character:FindFirstChild("Hidden Key") then
						EquipWeapon("Hidden Key")
						getgenv().ToTarget(CFrame.new(6571.1201171875, 299.23028564453, -6967.841796875))
					elseif game.Workspace.Enemies:FindFirstChild("Snow Lurker [Lv. 1375]") or game:GetService("Workspace").Enemies:FindFirstChild("Arctic Warrior [Lv. 1350]") then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if (v.Name == "Snow Lurker [Lv. 1375]" or v.Name == "Arctic Warrior [Lv. 1350]") and v.Humanoid.Health > 0 then
								repeat wait()
									StartMagnet = true
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									PosMon = v.HumanoidRootPart.CFrame
									v.HumanoidRootPart.Size = Vector3.new(60,60,60)
									v.Humanoid.JumpPower = 0
									v.Humanoid.WalkSpeed = 0
									v.HumanoidRootPart.CanCollide = false
									v.Humanoid:ChangeState(11)
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
								until game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or not _G.Auto_Rengoku or not v.Parent or v.Humanoid.Health <= 0
								StartMagnet = false
							end
						end
					else
						StartMagnet = false
						getgenv().ToTarget(CFrame.new(5525.7045898438, 262.90060424805, -6755.1186523438))
					end
				else 
					if _G.Auto_Rengoku_Hop and not game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or not game.Workspace.Enemies:FindFirstChild("Snow Lurker [Lv. 1375]") then
						Hop()
					else
						if (CFrame.new(5525.7045898438, 262.90060424805, -6755.1186523438).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
							BTP(CFrame.new(5525.7045898438, 262.90060424805, -6755.1186523438))
							return
						end
						getgenv().ToTarget(CFrame.new(5525.7045898438, 262.90060424805, -6755.1186523438))
					end
				end
			end)
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Rengoku_Hop", {Title = "Auto Rengoku Hop", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Rengoku_Hop = Options.Auto_Rengoku_Hop.Value
		SaveSettings()
	end)

	Options.Auto_Rengoku_Hop:SetValue(_G.Auto_Rengoku_Hop)

	Tabs.Main:AddSection("Dragon Trident")

	local Toggle = Tabs.Main:AddToggle("Auto_Dragon_Trident", {Title = "Auto Dragon Trident", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Dragon_Trident = Options.Auto_Dragon_Trident.Value
		if Options.Auto_Dragon_Trident.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Dragon_Trident:SetValue(_G.Auto_Dragon_Trident)

	spawn(function()
		while wait() do
			if _G.Auto_Dragon_Trident then
				pcall(function()
					if _G.Auto_Dragon_Trident and game.ReplicatedStorage:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") or game.Workspace.Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
						if game.Workspace.Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Tide Keeper [Lv. 1475] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
									repeat wait()
										EquipWeapon(_G.Select_Weapon)
										AutoHaki()
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until _G.Auto_Dragon_Trident or v.Humanoid.Health <= 0 or not v.Parent
								end
							end
						else
							if (CFrame.new(-3914.830322265625, 123.29389190673828, -11516.8642578125).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
								BTP(CFrame.new(-3914.830322265625, 123.29389190673828, -11516.8642578125))
								return
							end
							getgenv().ToTarget(CFrame.new(-3914.830322265625, 123.29389190673828, -11516.8642578125))
						end
					else
						if _G.Auto_Dragon_Trident_Hop and not game.Workspace.Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
							Hop()
						end
					end
				end)
			end
		end
	end)


	local Toggle = Tabs.Main:AddToggle("Auto_Dragon_Trident_Hop", {Title = "Auto Dragon Trident Hop", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Dragon_Trident_Hop = Options.Auto_Dragon_Trident_Hop.Value
		SaveSettings()
	end)

	Options.Auto_Dragon_Trident_Hop:SetValue(_G.Auto_Dragon_Trident)

	Tabs.Main:AddSection("Dark Coat")

	local Toggle = Tabs.Main:AddToggle("Auto_Dark_Coat", {Title = "Auto Dark Coat", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Dark_Coat = Options.Auto_Dark_Coat.Value
		if Options.Auto_Dark_Coat.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Dark_Coat:SetValue(_G.Auto_Dark_Coat)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Dark_Coat then
					if game:GetService("Workspace").Enemies:FindFirstChild("Darkbeard [Lv. 1000] [Raid Boss]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == ("Darkbeard [Lv. 1000] [Raid Boss]" or v.Name == "Darkbeard [Lv. 1000] [Raid Boss]") and v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
								repeat wait()
									StartMagnet = true
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									PosMon = v.HumanoidRootPart.CFrame
									v.HumanoidRootPart.Size = Vector3.new(60,60,60)
									v.Humanoid.JumpPower = 0
									v.Humanoid.WalkSpeed = 0
									v.HumanoidRootPart.CanCollide = false
									v.Humanoid:ChangeState(11)
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
								until _G.Auto_Dark_Coat == false or v.Humanoid.Health <= 0
								StartMagnet = false
							end
						end
					else
						getgenv().ToTarget(CFrame.new(3677.08203125, 62.751937866211, -3144.8332519531))
					end
				else 
					if _G.Auto_Dark_Coat_Hop and not game:GetService("Workspace").Enemies:FindFirstChild("Darkbeard [Lv. 1000] [Raid Boss]") then
						Hop()
					else
						if (CFrame.new(3677.08203125, 62.751937866211, -3144.8332519531).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
							BTP(CFrame.new(3677.08203125, 62.751937866211, -3144.8332519531))
							return
						end
						getgenv().ToTarget(CFrame.new(3677.08203125, 62.751937866211, -3144.8332519531))
					end
				end
			end)
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Dark_Coat_Hop", {Title = "Auto Dark Coat Hop", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Dark_Coat_Hop = Options.Auto_Dark_Coat_Hop.Value
		SaveSettings()
	end)

	Options.Auto_Dark_Coat_Hop:SetValue(_G.Auto_Dark_Coat_Hop)


	Tabs.Main:AddSection("Swan Glasses")

	local Toggle = Tabs.Main:AddToggle("Auto_Swan_Glasses", {Title = "Auto Swan Glasses", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Swan_Glasses = Options.Auto_Swan_Glasses.Value
		if Options.Auto_Swan_Glasses.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Swan_Glasses:SetValue(_G.Auto_Swan_Glasses)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Swan_Glasses then
					if game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Don Swan [Lv. 1000] [Boss]" and v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
								repeat wait()
									StartMagnet = true
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									PosMon = v.HumanoidRootPart.CFrame
									v.HumanoidRootPart.Size = Vector3.new(60,60,60)
									v.Humanoid.JumpPower = 0
									v.Humanoid.WalkSpeed = 0
									v.HumanoidRootPart.CanCollide = false
									v.Humanoid:ChangeState(11)
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
								until not _G.Auto_Swan_Glasses or v.Humanoid.Health <= 0
								StartMagnet = false
							end
						end
					else
						repeat wait()
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(2284.912109375, 15.537666320801, 905.48291015625)) 
						until (CFrame.new(2284.912109375, 15.537666320801, 905.48291015625).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4 or not _G.Settings.Main["Auto Swan Glasses"]
					end
				else 
					if _G.Auto_Swan_Glasses_Hop and not game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or not game.Workspace.Enemies:FindFirstChild("Snow Lurker [Lv. 1375]") then
						Hop()
					else
						if (CFrame.new(2284.912109375, 15.537666320801, 905.48291015625).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
							BTP(CFrame.new(2284.912109375, 15.537666320801, 905.48291015625))
							return
						end
						repeat wait()
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(2284.912109375, 15.537666320801, 905.48291015625)) 
						until (CFrame.new(2284.912109375, 15.537666320801, 905.48291015625).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4 or not _G.Settings.Main["Auto Swan Glasses"]
					end
				end
			end)
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Swan_Glasses_Hop", {Title = "Auto Swan Glasses Hop", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Swan_Glasses_Hop = Options.Auto_Swan_Glasses_Hop.Value
		SaveSettings()
	end)

	Options.Auto_Swan_Glasses_Hop:SetValue(_G.Auto_Swan_Glasses_Hop)

	Tabs.Main:AddSection("Other Function")

	local Toggle = Tabs.Main:AddToggle("Auto_Bartilo_Quest", {Title = "Auto Bartilo Quest", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Bartilo_Quest = Options.Auto_Bartilo_Quest.Value
		if Options.Auto_Bartilo_Quest.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Bartilo_Quest:SetValue(_G.Auto_Bartilo_Quest)


	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Bartilo_Quest then
					if game.Players.LocalPlayer.Data.Level.Value >= 850 then
						if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 0 then
							if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Swan Pirates") and string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50") and game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
								if game.Workspace.Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
									for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
										if v.Name == "Swan Pirate [Lv. 775]" then
											pcall(function()
												repeat wait()
													if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
														Farmtween = getgenv().ToTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
													elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
														if Farmtween then Farmtween:Stop() end
														AutoHaki()
														EquipWeapon(_G.Select_Weapon)
														PosMon = v.HumanoidRootPart.CFrame
														v.HumanoidRootPart.Size = Vector3.new(60,60,60)
														v.Humanoid.JumpPower = 0
														v.Humanoid.WalkSpeed = 0
														v.HumanoidRootPart.CanCollide = false
														v.Humanoid:ChangeState(11)
														getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
													end
												until not v.Parent or v.Humanoid.Health <= 0 or _G.Auto_Bartilo_Quest == false or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false
												StartMagnet = false
											end)
										end
									end
								else
									if (CFrame.new(1057.92761, 137.614319, 1242.08069).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
										BTP(CFrame.new(1057.92761, 137.614319, 1242.08069))
										return
									end
									Questtween = getgenv().ToTarget(CFrame.new(1057.92761, 137.614319, 1242.08069).Position,CFrame.new(1057.92761, 137.614319, 1242.08069))
									if (CFrame.new(1057.92761, 137.614319, 1242.08069).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Questtween then
											Questtween:Stop()
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1057.92761, 137.614319, 1242.08069)
									end
								end
							else
								Bartilotween = getgenv().ToTarget(CFrame.new(-456.28952, 73.0200958, 299.895966).Position,CFrame.new(-456.28952, 73.0200958, 299.895966))
								if ( CFrame.new(-456.28952, 73.0200958, 299.895966).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									if Bartilotween then
										Bartilotween:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =  CFrame.new(-456.28952, 73.0200958, 299.895966)
									local args = {
										[1] = "StartQuest",
										[2] = "BartiloQuest",
										[3] = 1
									}
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
								end
							end
						end
					elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 1 then
						if game.Workspace.Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Jeremy [Lv. 850] [Boss]" then
									repeat wait()
										if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											Farmtween = getgenv().ToTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
										elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if Farmtween then Farmtween:Stop() end
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											PosMon = v.HumanoidRootPart.CFrame
											v.HumanoidRootPart.Size = Vector3.new(60,60,60)
											v.Humanoid.JumpPower = 0
											v.Humanoid.WalkSpeed = 0
											v.HumanoidRootPart.CanCollide = false
											v.Humanoid:ChangeState(11)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										end
									until not v.Parent or v.Humanoid.Health <= 0 or _G.Auto_Bartilo_Quest == false
								end
							end
						else
							if (CFrame.new(2099.88159, 448.931, 648.997375).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
								BTP(CFrame.new(2099.88159, 448.931, 648.997375))
								return
							end
							Bartilotween = getgenv().ToTarget(CFrame.new(2099.88159, 448.931, 648.997375).Position,CFrame.new(2099.88159, 448.931, 648.997375))
							if (CFrame.new(2099.88159, 448.931, 648.997375).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
								if Bartilotween then
									Bartilotween:Stop()
								end
								game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2099.88159, 448.931, 648.997375)
							end
						end
					elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 2 then
						if (CFrame.new(-1836, 11, 1714).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
							Bartilotween = getgenv().ToTarget(CFrame.new(-1836, 11, 1714).Position,CFrame.new(-1836, 11, 1714))
						elseif (CFrame.new(-1836, 11, 1714).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
							if Bartilotween then
								Bartilotween:Stop()
							end
							game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1836, 11, 1714)
							wait(.5)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1850.49329, 13.1789551, 1750.89685)
							wait(1)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.87305, 19.3777466, 1712.01807)
							wait(1)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1803.94324, 16.5789185, 1750.89685)
							wait(1)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.55835, 16.8604317, 1724.79541)
							wait(1)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1869.54224, 15.987854, 1681.00659)
							wait(1)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1800.0979, 16.4978027, 1684.52368)
							wait(1)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1819.26343, 14.795166, 1717.90625)
							wait(1)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1813.51843, 14.8604736, 1724.79541)
						end
					end
				end
			end)
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Ectoplasm", {Title = "Auto Ectoplasm", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Ectoplasm = Options.Auto_Ectoplasm.Value
		if Options.Auto_Ectoplasm.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Ectoplasm:SetValue(_G.Auto_Ectoplasm)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Ectoplasm then
					if game:GetService("Workspace").Enemies:FindFirstChild("Ship Deckhand [Lv. 1250]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Engineer [Lv. 1275]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Steward [Lv. 1300]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Officer [Lv. 1325]") or game:GetService("Workspace").Enemies:FindFirstChild("Arctic Warrior [Lv. 1350]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Ship Deckhand [Lv. 1250]" or v.Name == "Ship Engineer [Lv. 1275]" or v.Name == "Ship Steward [Lv. 1300]" or v.Name == "Ship Officer [Lv. 1325]" or v.Name == "Arctic Warrior [Lv. 1350]" then
								if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
									repeat wait()
										StartMagnet = true
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										PosMon = v.HumanoidRootPart.CFrame
										v.HumanoidRootPart.Size = Vector3.new(60,60,60)
										v.Humanoid.JumpPower = 0
										v.Humanoid.WalkSpeed = 0
										v.HumanoidRootPart.CanCollide = false
										v.Humanoid:ChangeState(11)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until not _G.Auto_Ectoplasm or not v.Parent or v.Humanoid.Health <= 0
									StartMagnet = false
								end
							end
						end
					else
						StartMagnet = false
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
					end
				end
			end)
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Evo_Race_V2", {Title = "Auto Evo Race V2", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Evo_Race_V2 = Options.Auto_Evo_Race_V2.Value
		if Options.Auto_Evo_Race_V2.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Evo_Race_V2:SetValue(_G.Auto_Evo_Race_V2)

	spawn(function()
		pcall(function()
			while wait() do
				if  _G.Auto_Evo_Race_V2 then
					if not game:GetService("Players").LocalPlayer.Data.Race:FindFirstChild("Evolved") then
						if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 0 then
							getgenv().ToTarget(CFrame.new(-2779.83521, 72.9661407, -3574.02002, -0.730484903, 6.39014104e-08, -0.68292886, 3.59963224e-08, 1, 5.50667032e-08, 0.68292886, 1.56424669e-08, -0.730484903))
							if (Vector3.new(-2779.83521, 72.9661407, -3574.02002) - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4 then
								wait(1.3)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","2")
							end
						elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 1 then
							pcall(function()
								if not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 1") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 1") then
									getgenv().ToTarget(game:GetService("Workspace").Flower1.CFrame)
								elseif not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 2") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 2") then
									getgenv().ToTarget(game:GetService("Workspace").Flower2.CFrame)
								elseif not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 3") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 3") then
									if game:GetService("Workspace").Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
										for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
											if v.Name == "Swan Pirate [Lv. 775]" then
												repeat wait()
													AutoHaki()
													EquipWeapon(_G.Select_Weapon)
													getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
													v.HumanoidRootPart.CanCollide = false
													v.HumanoidRootPart.Size = Vector3.new(50,50,50)
													PosMonEvo = v.HumanoidRootPart.CFrame
													StartEvoMagnet = true
												until game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 3") or not v.Parent or v.Humanoid.Health <= 0 or _G.Auto_Evo_Race_V2 == false
												StartEvoMagnet = false
											end
										end
									else
										StartEvoMagnet = false
										getgenv().ToTarget(CFrame.new(980.0985107421875, 121.331298828125, 1287.2093505859375))
									end
								end
							end)
						elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 2 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","3")
						end
					end
				end
			end
		end)
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_True_Triple_Katana", {Title = "Auto True Triple Katana", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_True_Triple_Katana = Options.Auto_True_Triple_Katana.Value
		SaveSettings()
	end)

	Options.Auto_True_Triple_Katana:SetValue(_G.Auto_True_Triple_Katana)


	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_True_Triple_Katana then
					local string_1 = "MysteriousMan";
					local string_2 = "2";
					local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
					Target:InvokeServer(string_1, string_2);  
				end
			end)
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Buy_Legendary_Sword", {Title = "Auto Buy Legendary Sword", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Buy_Legendary_Sword = Options.Auto_Buy_Legendary_Sword.Value
		SaveSettings()
	end)

	Options.Auto_Buy_Legendary_Sword:SetValue(_G.Auto_Buy_Legendary_Sword)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Buy_Legendary_Sword then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LegendarySwordDealer","1")
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LegendarySwordDealer","2")
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LegendarySwordDealer","3")
				end
			end)
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Buy_Enchanment_Haki", {Title = "Auto Buy Enchanment Haki", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Buy_Enchanment_Haki = Options.Auto_Buy_Enchanment_Haki.Value
		SaveSettings()
	end)

	Options.Auto_Buy_Enchanment_Haki:SetValue(_G.Auto_Buy_Enchanment_Haki)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Buy_Enchanment_Haki then
					local args = {
						[1] = "ColorsDealer",
						[2] = "2"
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end
			end)
		end
	end)

elseif World3 then

	Tabs.Main:AddSection("Elite Hunter")

	Tabs.Main:AddParagraph({
		Title = "Elite Hunter",
		Content = "This is a paragraph.\nSecond line!"
	})

	local Toggle = Tabs.Main:AddToggle("Auto_Elite_Hunter", {Title = "Auto Elite Hunter", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Elite_Hunter = Options.Auto_Elite_Hunter.Value
		if Options.Auto_Elite_Hunter.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Elite_Hunter:SetValue(_G.Auto_Elite_Hunter)


	spawn(function()
		while wait() do
			if _G.Auto_Elite_Hunter and World3 then
				pcall(function()
					if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
						if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,"Diablo") or string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,"Deandre") or string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,"Urban") then
							if game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Diablo [Lv. 1750]" or v.Name == "Deandre [Lv. 1750]" or v.Name == "Urban [Lv. 1750]" then
										if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
											repeat wait()
												AutoHaki()
												EquipWeapon(_G.Select_Weapon)
												v.HumanoidRootPart.CanCollide = false
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.Size = Vector3.new(50,50,50)
												getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
												sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
											until _G.Auto_Elite_Hunter == false or v.Humanoid.Health <= 0 or not v.Parent
										end
									end
								end
							else					
								if game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") then
									if (game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]").HumanoidRootPart.CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
										BTP(game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]"))
										return
									end
									getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]").HumanoidRootPart.CFrame * MethodFarm)
								elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") then
									if (game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]").HumanoidRootPart.CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
										BTP(game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]"))
										return
									end
									getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]").HumanoidRootPart.CFrame * MethodFarm)
								elseif game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") then
									if (game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]").HumanoidRootPart.CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
										BTP(game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]"))
										return
									end
									getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]").HumanoidRootPart.CFrame * MethodFarm)
								end
							end                    
						end
					else
						if _G.Auto_Elite_Hunter_Hop and game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("EliteHunter") == "I don't have anything for you right now. Come back later." then
							Hop()
						else
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
						end
					end
				end)
			end
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Elite_Hunter_Hop", {Title = "Auto Elite Hunter Hop", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Elite_Hunter_Hop = Options.Auto_Elite_Hunter_Hop.Value
		SaveSettings()
	end)

	Options.Auto_Elite_Hunter_Hop:SetValue(_G.Auto_Elite_Hunter_Hop)

	Tabs.Main:AddSection("Bone")

	Tabs.Main:AddParagraph({
		Title = "Bone",
		Content = "This is a paragraph.\nSecond line!"
	})

	spawn(function()
		pcall(function()
			while wait() do
				Tabs.Main.Content:Set(" 🦴 Bone : "..(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Check")))
			end
		end)
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Farm_Bone", {Title = "Auto Farm Bone", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Farm_Bone = Options.Auto_Farm_Bone.Value
		if Options.Auto_Farm_Bone.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Farm_Bone:SetValue(_G.Auto_Farm_Bone)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Bone and World3 then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Reborn Skeleton [Lv. 1975]") or game:GetService("Workspace").Enemies:FindFirstChild("Living Zombie [Lv. 2000]") or game:GetService("Workspace").Enemies:FindFirstChild("Domenic Soul [Lv. 2025]") or game:GetService("Workspace").Enemies:FindFirstChild("Posessed Mummy [Lv. 2050]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Reborn Skeleton [Lv. 1975]" or v.Name == "Living Zombie [Lv. 2000]" or v.Name == "Demonic Soul [Lv. 2025]" or v.Name == "Posessed Mummy [Lv. 2050]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										StartMagnetBoneMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonBone = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until _G.Auto_Farm_Bone == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetBoneMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Reborn Skeleton [Lv. 1975]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
							elseif v.Name == "Living Zombie [Lv. 2000]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
							elseif v.Name == "Demonic Soul [Lv. 2025]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
							elseif v.Name == "Posessed Mummy [Lv. 2050]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
							end
						end
						if (CFrame.new(-9466.72949, 171.162918, 6132.01514).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
							BTP(CFrame.new(-9466.72949, 171.162918, 6132.01514))
							return
						end
						getgenv().ToTarget(CFrame.new(-9466.72949, 171.162918, 6132.01514))
					end
				end)
			end
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Random_Bone", {Title = "Auto Random Bone", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Random_Bone = Options.Auto_Random_Bone.Value
		SaveSettings()
	end)

	Options.Auto_Random_Bone:SetValue(_G.Auto_Random_Bone)

	spawn(function()
		while wait(.1) do
			if _G.Auto_Random_Bone then
				local args = {
					[1] = "Bones",
					[2] = "Buy",
					[3] = 1,
					[4] = 1
				}

				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end
		end
	end)

	Tabs.Main:AddSection("Cake Prince")

	local Toggle = Tabs.Main:AddToggle("Auto_Cake_Prince", {Title = "Auto Cake Prince", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Cake_Prince = Options.Auto_Cake_Prince.Value
		if Options.Auto_Cake_Prince.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Cake_Prince:SetValue(_G.Auto_Cake_Prince)

	spawn(function()
		while wait() do
			if _G.Auto_Cake_Prince then
				pcall(function()
					if game.ReplicatedStorage:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then   
						if game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do 
								if v.Name == "Cake Prince [Lv. 2300] [Raid Boss]" then
									repeat wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										v.HumanoidRootPart.CanCollide = false
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until _G.Auto_Cake_Prince == false or not v.Parent or v.Humanoid.Health <= 0
								end    
							end    
						else
							for _,x in pairs(game.ReplicatedStorage:GetChildren()) do 
								if x.Name == "Cake Prince [Lv. 2300] [Raid Boss]" or x.Name == "Dough King [Lv. 2300] [Raid Boss]" then
									if (x.HumanoidRootPart.CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1000 then
										getgenv().ToTarget(CFrame.new(-2145.89722, 70.0088272, -12399.6016, 0.99999702, 1.58276379e-08, 0.00245277886, -1.57982978e-08, 1, -1.19813057e-08, -0.00245277886, 1.19425199e-08, 0.99999702))
										return
									end
								end
							end
						end
					else
						if game.Workspace.Enemies:FindFirstChild("Baking Staff [Lv. 2250]") or game.Workspace.Enemies:FindFirstChild("Head Baker [Lv. 2275]") or game.Workspace.Enemies:FindFirstChild("Cake Guard [Lv. 2225]") or game.Workspace.Enemies:FindFirstChild("Cookie Crafter [Lv. 2200]")  then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do  
								if (v.Name == "Baking Staff [Lv. 2250]" or v.Name == "Head Baker [Lv. 2275]" or v.Name == "Cake Guard [Lv. 2225]" or v.Name == "Cookie Crafter [Lv. 2200]") and v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										StartCakeMagnet = true
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)  
										POSCAKE = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until _G.Auto_Cake_Prince == false or game:GetService("ReplicatedStorage"):FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						else
							if (CFrame.new(-1820.0634765625, 210.74781799316406, -12297.49609375).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
								BTP(CFrame.new(-1820.0634765625, 210.74781799316406, -12297.49609375))
								return
							end
							getgenv().ToTarget(CFrame.new(-1820.0634765625, 210.74781799316406, -12297.49609375))
							for i,v in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
								if (v.Name == "Baking Staff [Lv. 2250]" or v.Name == "Head Baker [Lv. 2275]" or v.Name == "Cake Guard [Lv. 2225]" or v.Name == "Cookie Crafter [Lv. 2200]") then local CFrameEnemySpawns = v.CFrame  wait(0.5)
									getgenv().ToTarget(CFrameEnemySpawns * MethodFarm)
								end
							end
						end
					end
				end)
			end
		end
	end)


	local Toggle = Tabs.Main:AddToggle("Auto_Spawn_Cake_Prince", {Title = "Auto Spawn Cake Prince", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Spawn_Cake_Prince = Options.Auto_Spawn_Cake_Prince.Value
		SaveSettings()
	end)

	Options.Auto_Cake_Prince:SetValue(_G.Auto_Spawn_Cake_Prince)

	spawn(function()
		while wait() do
			if _G.Auto_Spawn_Cake_Prince then
				local args = {
					[1] = "CakePrinceSpawner",
					[2] = true
				}

				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))                    
				local args = {
					[1] = "CakePrinceSpawner"
				}

				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end
		end
	end)

	Tabs.Main:AddSection("Buddy Sword")

	local Toggle = Tabs.Main:AddToggle("Auto_Buddy_Sword", {Title = "Auto Buddy Sword", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Buddy_Sword = Options.Auto_Buddy_Sword.Value
		if Options.Auto_Buddy_Sword.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Buddy_Sword:SetValue(_G.Auto_Buddy_Sword)


	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Buddy_Sword then
					if game:GetService("Workspace").Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == ("Cake Queen [Lv. 2175] [Boss]" or v.Name == "Cake Queen [Lv. 2175] [Boss]") and v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
								repeat wait()
									StartMagnet = true
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									PosMon = v.HumanoidRootPart.CFrame
									v.HumanoidRootPart.Size = Vector3.new(60,60,60)
									v.Humanoid.JumpPower = 0
									v.Humanoid.WalkSpeed = 0
									v.HumanoidRootPart.CanCollide = false
									v.Humanoid:ChangeState(11)
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
								until not _G.Auto_Buddy_Sword or v.Humanoid.Health <= 0
								StartMagnet = false
							end
						end
					end
				else 
					if _G.Auto_Buddy_Sword_Hop and not game:GetService("Workspace").Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
						Hop()
					else						
						if (CFrame.new(5525.7045898438, 262.90060424805, -6755.1186523438).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
							BTP(CFrame.new(5525.7045898438, 262.90060424805, -6755.1186523438))
							return
						end
						getgenv().ToTarget(CFrame.new(5525.7045898438, 262.90060424805, -6755.1186523438))
					end
				end
			end)
		end
	end)


	local Toggle = Tabs.Main:AddToggle("Auto_Buddy_Sword_Hop", {Title = "Auto Buddy Sword Hop", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Buddy_Sword_Hop = Options.Auto_Buddy_Sword_Hop.Value
		SaveSettings()
	end)

	Options.Auto_Buddy_Sword_Hop:SetValue(_G.Auto_Buddy_Sword_Hop)

	Tabs.Main:AddSection("Boss Hallow")

	local Toggle = Tabs.Main:AddToggle("Auto_Farm_Boss_Hallow", {Title = "Auto Farm Boss Hallow", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Farm_Boss_Hallow = Options.Auto_Farm_Boss_Hallow.Value
		if Options.Auto_Farm_Boss_Hallow.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Farm_Boss_Hallow:SetValue(_G.Auto_Farm_Boss_Hallow)


	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Farm_Boss_Hallow then
					if game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if string.find(v.Name , "Soul Reaper") then
								repeat wait()
									StartMagnet = true
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									PosMon = v.HumanoidRootPart.CFrame
									v.HumanoidRootPart.Size = Vector3.new(60,60,60)
									v.Humanoid.JumpPower = 0
									v.Humanoid.WalkSpeed = 0
									v.HumanoidRootPart.CanCollide = false
									v.Humanoid:ChangeState(11)
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
								until v.Humanoid.Health <= 0 or not _G.Auto_Farm_Boss_Hallow
								StartMagnet = false
							end
						end
					else
						getgenv().ToTarget(CFrame.new(-9524.7890625, 315.80429077148, 6655.7192382813))
					end
				else 
					if _G.Auto_Farm_Boss_Hallow_Hop and not game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
						Hop()
					else						
						if (CFrame.new(-9524.7890625, 315.80429077148, 6655.7192382813).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
							BTP(CFrame.new(-9524.7890625, 315.80429077148, 6655.7192382813))
							return
						end
						getgenv().ToTarget(CFrame.new(-9524.7890625, 315.80429077148, 6655.7192382813))
					end
				end
			end)
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Farm_Boss_Hallow_Hop", {Title = "Auto Farm Boss Hallow Hop", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Farm_Boss_Hallow_Hop = Options.Auto_Farm_Boss_Hallow_Hop.Value
		SaveSettings()
	end)

	Options.Auto_Farm_Boss_Hallow:SetValue(_G.Auto_Farm_Boss_Hallow_Hop)

	Tabs.Main:AddSection("Twin Hook")

	local Toggle = Tabs.Main:AddToggle("Twin_Hook", {Title = "Auto Twin Hook", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Twin_Hook = Options.Auto_Twin_Hook.Value
		if Options.Auto_Twin_Hook.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Twin_Hook:SetValue(_G.Auto_Twin_Hook)

	spawn(function()
		while wait() do
			if _G.Auto_Twin_Hook then
				pcall(function()
					if _G.Auto_Twin_Hook and game.ReplicatedStorage:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") or game.Workspace.Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
						if game.Workspace.Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Captain Elephant [Lv. 1875] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until _G.Auto_Twin_Hook or v.Humanoid.Health <= 0 or not v.Parent
								end
							end
						else
							if (CFrame.new(-13348.0654296875, 405.8904113769531, -8570.62890625).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
								BTP(CFrame.new(-13348.0654296875, 405.8904113769531, -8570.62890625))
								return
							end
							getgenv().ToTarget(CFrame.new(-13348.0654296875, 405.8904113769531, -8570.62890625))
						end
					else
						if _G.Auto_Twin_Hook_Hop then
							Hop()
						end
					end
				end)
			end
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Twin_Hook_Hop", {Title = "Auto Twin Hook Hop", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Twin_Hook_Hop = Options.Auto_Twin_Hook_Hop.Value
		SaveSettings()
	end)

	Options.Auto_Twin_Hook_Hop:SetValue(_G.Auto_Twin_Hook_Hop)

	Tabs.Main:AddSection("Cavander")

	local Toggle = Tabs.Main:AddToggle("Auto_Cavander", {Title = "Auto Cavander", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Cavander = Options.Auto_Cavander.Value
		if Options.Auto_Cavander.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Cavander:SetValue(_G.Auto_Cavander)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Cavander then
					if game:GetService("Workspace").Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == ("Beautiful Pirate [Lv. 1950] [Boss]") and v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
								repeat wait()
									StartMagnet = true
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									PosMon = v.HumanoidRootPart.CFrame
									v.HumanoidRootPart.Size = Vector3.new(60,60,60)
									v.Humanoid.JumpPower = 0
									v.Humanoid.WalkSpeed = 0
									v.HumanoidRootPart.CanCollide = false
									v.Humanoid:ChangeState(11)
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
								until not _G.Auto_Cavander or v.Humanoid.Health <= 0
								StartMagnet = false
							end
						end
					else
						if _G.Auto_Cavander_Hop and not game:GetService("Workspace").Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
							wait(10)
							Hop()
						else						
							if (CFrame.new(5283.609375, 22.56223487854, -110.78285217285).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
								BTP(CFrame.new(5283.609375, 22.56223487854, -110.78285217285))
								return
							end
							getgenv().ToTarget(CFrame.new(5283.609375, 22.56223487854, -110.78285217285))
						end
					end
				end
			end)
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Cavander_Hop", {Title = "Auto Cavander Hop", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Cavander_Hop = Options.Auto_Cavander_Hop.Value
		if Options.Auto_Cavander_Hop.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Cavander_Hop:SetValue(_G.Auto_Cavander_Hop)

	Tabs.Main:AddSection("Yama")

	local Toggle = Tabs.Main:AddToggle("Auto_Yama", {Title = "Auto Yama", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Yama = Options.Auto_Yama.Value
		if Options.Auto_Yama.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Yama:SetValue(_G.Auto_Yama)


	local Yama_All_Mon = {
		["Mon Quest"] = {"Diablo [Lv. 1750]","Deandre [Lv. 1750]","Urban [Lv. 1750]"},
		["Mon"] = {"Diablo","Deandre","Urban"},
		["Item"] = "God's Chalice",
	}

	spawn(function()
		while wait() do
			if _G.Auto_Yama then
				pcall(function()
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter","Progress") >= 30 then
						fireclickdetector(game:GetService("Workspace").Map.Waterfall.SealedKatana.Handle.ClickDetector)
					else
						local QuestUI = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest
						for _,_l1 in ipairs(Yama_All_Mon["Mon Quest"]) do
							for _,l in ipairs(Yama_All_Mon["Mon"]) do
								if QuestUI.Visible == true then
									if game:GetService("Workspace").Enemies:FindFirstChild(_l1) or game:GetService("ReplicatedStorage"):FindFirstChild(_l1) then
										for _,_v1 in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
											if _v1.Name == _l1 then
												if _v1:FindFirstChild("Humanoid") and _v1:FindFirstChild("HumanoidRootPart") and _v1.Humanoid.Health > 0 then
													repeat wait()
														_v1.HumanoidRootPart.Size = Vector3.new(60,60,60)
														_v1.HumanoidRootPart.CanCollide = false
														_v1.Head.CanCollide = false
														BringMobFarm = true
														EquipWeapon(_G.Select_Weapon)
														_v1.HumanoidRootPart.Transparency = 1
														getgenv().ToTarget(_v1.HumanoidRootPart.CFrame * MethodFarm)
													until not _G.Auto_Yama or _v1.Humanoid.Health <= 0 or not _v1.Parent
												end
											else
												if (game:GetService("ReplicatedStorage"):FindFirstChild(_l1).HumanoidRootPart.CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
													BTP(game:GetService("ReplicatedStorage"):FindFirstChild(_l1).HumanoidRootPart.CFrame)
													return
												end
												getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild(_l1).HumanoidRootPart.CFrame * MethodFarm)
											end
										end
									end
								else
									if game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("EliteHunter") == "I don't have anything for you right now. Come back later." and not ( game:GetService("Workspace").Enemies:FindFirstChild(_l1) or game:GetService("ReplicatedStorage"):FindFirstChild(_l1) ) then
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
										if (game:GetService("ReplicatedStorage"):FindFirstChild(_l1).HumanoidRootPart.CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
											BTP(game:GetService("ReplicatedStorage"):FindFirstChild(_l1).HumanoidRootPart.CFrame)
											return
										end
										getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild(_l1).HumanoidRootPart.CFrame * MethodFarm)
									end
								end
							end
						end
					end
				end)
			end
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Tushita", {Title = "Auto Tushita", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Tushita = Options.Auto_Tushita.Value
		if Options.Auto_Tushita.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Tushita:SetValue(_G.Auto_Tushita)

	spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Tushita then
					if game:GetService("Workspace").Map.Turtle.TushitaGate:GetChildren()[2].Transparency == 1 or game:GetService("Workspace").Map.Turtle.TushitaGate:GetChildren()[1].Transparency == 1 then
						if #game:GetService("Workspace").Enemies:GetChildren() > 0 then
							if game:GetService("Workspace").Enemies:FindFirstChild("Longma [Lv. 2000] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Longma [Lv. 2000] [Boss]") then
								for _,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Longma [Lv. 2000] [Boss]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
										repeat wait()
											v.HumanoidRootPart.Size = Vector3.new(60,60,60)
											v.HumanoidRootPart.CanCollide = false
											v.Head.CanCollide = false
											BringMobFarm = true
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											v.HumanoidRootPart.Transparency = 1
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										until not __G.Auto_Tushita or not v.Humanoid.Health <= 0 or not v.Parent
									else
										if (game:GetService("ReplicatedStorage"):FindFirstChild("Longma [Lv. 2000] [Boss]").HumanoidRootPart.CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
											BTP(game:GetService("ReplicatedStorage"):FindFirstChild("Longma [Lv. 2000] [Boss]").HumanoidRootPart.CFrame * MethodFarm)
											return
										end
										getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Longma [Lv. 2000] [Boss]").HumanoidRootPart.CFrame * MethodFarm)
									end
								end
							end
						end
					else
						if game:GetService("Workspace").Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
							if game:GetService("Players").LocalPlayer.Data.LastSpawnPoint.Value == tostring(GetIsLand(CFrame.new(-13274.528320313, 531.82073974609, -7579.22265625))) then
								wait(1)
								repeat getgenv().ToTarget(CFrame.new(-10752, 417, -9366)) wait() until not _G.Auto_Holy_Torch or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-10752, 417, -9366)).Magnitude <= 1
								wait(1)
								repeat getgenv().ToTarget(CFrame.new(-11672, 334, -9474)) wait() until not _G.Auto_Holy_Torch or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-11672, 334, -9474)).Magnitude <= 1
								wait(1)
								repeat getgenv().ToTarget(CFrame.new(-12132, 521, -10655)) wait() until not _G.Auto_Holy_Torch or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-12132, 521, -10655)).Magnitude <= 1
								wait(1)
								repeat getgenv().ToTarget(CFrame.new(-13336, 486, -6985)) wait() until not _G.Auto_Holy_Torch or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-13336, 486, -6985)).Magnitude <= 1
								wait(1)
								repeat getgenv().ToTarget(CFrame.new(-13489, 332, -7925)) wait() until not _G.Auto_Holy_Torch or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-13489, 332, -7925)).Magnitude <= 1
							else
								if (CFrame.new(5148.03613, 162.352493, 910.548218, 0, 0, -1, 0, 1, 0, 1, 0, 0).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
									BTP(CFrame.new(5148.03613, 162.352493, 910.548218, 0, 0, -1, 0, 1, 0, 1, 0, 0))
									return
								end
								getgenv().ToTarget(CFrame.new(5148.03613, 162.352493, 910.548218, 0, 0, -1, 0, 1, 0, 1, 0, 0))
								wait(2.5)
								return
							end
						end
					end
				else
					_G.Auto_Tushita = false
				end
			end)
		end
	end)

	Tabs.Main:AddSection("Cursed Dual Katana")


	local Toggle = Tabs.Main:AddToggle("Auto_Cursed_Dual_Katana", {Title = "Auto Cursed Dual Katana", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Cursed_Dual_Katana = Options.Auto_Cursed_Dual_Katana.Value
		if Options.Auto_Cursed_Dual_Katana.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Cursed_Dual_Katana:SetValue(_G.Auto_Cursed_Dual_Katana)


	spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Cursed_Dual_Katana then
					if GetWeaponInventory("Cursed Dual Katana") == true then
						if game.Players.LocalPlayer.Character:FindFirstChild("Cursed Dual Katana") or game.Players.LocalPlayer.Backpack:FindFirstChild("Cursed Dual Katana") then

						else
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadItem","Cursed Dual Katana")
						end
					else
						if game.Players.LocalPlayer.Character:FindFirstChild("Tushita") or game.Players.LocalPlayer.Backpack:FindFirstChild("Tushita") or game.Players.LocalPlayer.Character:FindFirstChild("Yama") or game.Players.LocalPlayer.Backpack:FindFirstChild("Yama") then
							if game.Players.LocalPlayer.Character:FindFirstChild("Tushita") or game.Players.LocalPlayer.Backpack:FindFirstChild("Tushita") then
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Tushita") then
									EquipWeapon("Tushita")
								else
									for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
										if v.Name == "Tushita" and v:IsA("Tool") then
											if v.Level.Value >= 350 then
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadItem","Yama")
												_G.Auto_Farm_Bone = false
											else
												_G.Select_Weapon = "Tushita"
												_G.Auto_Farm_Bone = true
											end
										end
									end
								end
							elseif game.Players.LocalPlayer.Character:FindFirstChild("Yama") or game.Players.LocalPlayer.Backpack:FindFirstChild("Yama") then
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Yama") then
									EquipWeapon("Yama")
								else
									for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
										if v.Name == "Yama" and v:IsA("Tool") then
											if v.Level.Value >= 350 then
												Auto_CDK_Quest = true
												_G.Auto_Farm_Bone = false
											else
												_G.Select_Weapon = "Yama"
												_G.Auto_Farm_Bone = true
											end
										end
									end
								end
							end
						else
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadItem","Tushita")
						end      
					end
				end
			end)
		end
	end)


	spawn(function()
		while wait() do
			pcall(function()
				if Auto_CDK_Quest then
					if GetMaterial("Alucard Fragment") == 0 then
						Auto_Quest_Yama_1 = true
						Auto_Quest_Yama_2 = false
						Auto_Quest_Yama_3 = false
						Auto_Quest_Tushita_1 = false
						Auto_Quest_Tushita_2 = false
						Auto_Quest_Tushita_3 = false
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","Progress","Evil")
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","StartTrial","Evil")
					elseif GetMaterial("Alucard Fragment") == 1 then
						Auto_Quest_Yama_1 = false
						Auto_Quest_Yama_2 = true
						Auto_Quest_Yama_3 = false
						Auto_Quest_Tushita_1 = false
						Auto_Quest_Tushita_2 = false
						Auto_Quest_Tushita_3 = false
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","Progress","Evil")
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","StartTrial","Evil")
					elseif GetMaterial("Alucard Fragment") == 2 then
						Auto_Quest_Yama_1 = false
						Auto_Quest_Yama_2 = false
						Auto_Quest_Yama_3 = true
						Auto_Quest_Tushita_1 = false
						Auto_Quest_Tushita_2 = false
						Auto_Quest_Tushita_3 = false
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","Progress","Evil")
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","StartTrial","Evil")
					elseif GetMaterial("Alucard Fragment") == 3 then
						Auto_Quest_Yama_1 = false
						Auto_Quest_Yama_2 = false
						Auto_Quest_Yama_3 = false
						Auto_Quest_Tushita_1 = true
						Auto_Quest_Tushita_2 = false
						Auto_Quest_Tushita_3 = false
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","Progress","Good")
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","StartTrial","Good")
					elseif GetMaterial("Alucard Fragment") == 4 then
						Auto_Quest_Yama_1 = false
						Auto_Quest_Yama_2 = false
						Auto_Quest_Yama_3 = false
						Auto_Quest_Tushita_1 = false
						Auto_Quest_Tushita_2 = true
						Auto_Quest_Tushita_3 = false
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","Progress","Good")
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","StartTrial","Good")
					elseif GetMaterial("Alucard Fragment") == 5 then
						Auto_Quest_Yama_1 = false
						Auto_Quest_Yama_2 = false
						Auto_Quest_Yama_3 = false
						Auto_Quest_Tushita_1 = false
						Auto_Quest_Tushita_2 = false
						Auto_Quest_Tushita_3 = true
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","Progress","Good")
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","StartTrial","Good")
					elseif GetMaterial("Alucard Fragment") == 6 then
						if game:GetService("Workspace").Enemies:FindFirstChild("Cursed Skeleton Boss [Lv. 2025] [Boss]") or game:GetService("Workspace").ReplicatedStorage:FindFirstChild("Cursed Skeleton Boss [Lv. 2025] [Boss]") then
							Auto_Quest_Yama_1 = false
							Auto_Quest_Yama_2 = false
							Auto_Quest_Yama_3 = false
							Auto_Quest_Tushita_1 = false
							Auto_Quest_Tushita_2 = false
							Auto_Quest_Tushita_3 = false
							if game:GetService("Workspace").Enemies:FindFirstChild("Cursed Skeleton Boss [Lv. 2025] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Cursed Skeleton [Lv. 2200]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Cursed Skeleton Boss [Lv. 2025] [Boss]" or v.Name == "Cursed Skeleton [Lv. 2200]" then
										if v.Humanoid.Health > 0 then
											v.HumanoidRootPart.CanCollide = false
											v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
											game:GetService'VirtualUser':CaptureController()
											game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
										end
									end
								end
							end
						else
							if (CFrame.new(-12361.7060546875, 603.3547973632812, -6550.5341796875).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 100 then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","Progress","Good")
								wait(1)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","Progress","Evil")
								wait(1)
								getgenv().ToTarget(CFrame.new(-12361.7060546875, 603.3547973632812, -6550.5341796875))
								wait(1.5)
								game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, game)
								wait(1.5)
								getgenv().ToTarget(CFrame.new(-12253.5419921875, 598.8999633789062, -6546.8388671875))
							else
								getgenv().ToTarget(CFrame.new(-12361.7060546875, 603.3547973632812, -6550.5341796875))
							end   
						end
					end
				end
			end)
		end
	end)


	spawn(function()
		while wait() do
			if Auto_Quest_Yama_1 then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Mythological Pirate [Lv. 1850]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Mythological Pirate [Lv. 1850]" then
								repeat wait()
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,0,-2))
								until not Auto_CDK_Quest or not Auto_Cursed_Dual_Katana 
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","StartTrial","Evil")
							end
						end
					else
						getgenv().ToTarget(CFrame.new(-13451.46484375, 543.712890625, -6961.0029296875))
					end
				end)
			end
		end
	end)

	spawn(function()
		while wait() do
			pcall(function()
				if Auto_Quest_Yama_2 then
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if v:FindFirstChild("HazeESP") then
							v.HazeESP.Size = UDim2.new(50,50,50,50)
							v.HazeESP.MaxDistance = "inf"
						end
					end
					for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
						if v:FindFirstChild("HazeESP") then
							v.HazeESP.Size = UDim2.new(50,50,50,50)
							v.HazeESP.MaxDistance = "inf"
						end
					end
				end
			end)
		end
	end)

	spawn(function()
		while wait() do
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if Auto_Quest_Yama_2 and v:FindFirstChild("HazeESP") and (v.HumanoidRootPart.Position - PosMonsEsp.Position).magnitude <= 300 then
						v.HumanoidRootPart.CFrame = PosMonsEsp
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if not v.HumanoidRootPart:FindFirstChild("BodyVelocity") then
							local vc = Instance.new("BodyVelocity", v.HumanoidRootPart)
							vc.MaxForce = Vector3.new(1, 1, 1) * math.huge
							vc.Velocity = Vector3.new(0, 0, 0)
						end
					end
				end
			end)
		end
	end)

	spawn(function()
		while wait() do
			if Auto_Quest_Yama_2 then 
				pcall(function() 
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if v:FindFirstChild("HazeESP") then
							repeat wait()
								if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
									BTP(v.HumanoidRootPart.CFrameMon* CFrame.new(0,20,0))
								else
									StartMagnet = true
									EquipWeapon(_G.Select_Weapon)
									PosMonsEsp = v.HumanoidRootPart.CFrame
									v.HumanoidRootPart.Size = Vector3.new(60,60,60)
									v.Humanoid.JumpPower = 0
									v.Humanoid.WalkSpeed = 0
									v.HumanoidRootPart.CanCollide = false
									v.Humanoid:ChangeState(11)
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))								
								end      
							until _G.Auto_Cursed_Dual_Katana == false or Auto_Quest_Yama_2 == false or not v.Parent or v.Humanoid.Health <= 0 or not v:FindFirstChild("HazeESP")
						else
							for x,y in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
								if y:FindFirstChild("HazeESP") then
									if (y.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
										BTP(y.HumanoidRootPart.CFrameMon* CFrame.new(0,20,0))
									else
										getgenv().ToTarget(y.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									end
								end
							end
						end
					end
				end)
			end
		end
	end)

	spawn(function()
		while wait() do
			if Auto_Quest_Yama_3 then
				pcall(function()
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Hallow Essence") then         
						_G.Auto_Farm_Bone = false           
						getgenv().ToTarget(game:GetService("Workspace").Map["Haunted Castle"].Summoner.Detection.CFrame)
					elseif game:GetService("Workspace").Map:FindFirstChild("HellDimension") then
						repeat wait()
							if game:GetService("Workspace").Enemies:FindFirstChild("Cursed Skeleton [Lv. 2200]") or game:GetService("Workspace").Enemies:FindFirstChild("Cursed Skeleton [Lv. 2200] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Hell's Messenger [Lv. 2200] [Boss]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Cursed Skeleton [Lv. 2200]" or v.Name == "Cursed Skeleton [Lv. 2200] [Boss]" or v.Name == "Hell's Messenger [Lv. 2200] [Boss]" then
										if v.Humanoid.Health > 0 then
											repeat wait()
												StartMagnet = true
												EquipWeapon(_G.Select_Weapon)
												PosMonsEsp = v.HumanoidRootPart.CFrame
												v.HumanoidRootPart.Size = Vector3.new(60,60,60)
												v.Humanoid.JumpPower = 0
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.CanCollide = false
												v.Humanoid:ChangeState(11)
												getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
											until v.Humanoid.Health <= 0 or not v.Parent or Auto_Quest_Yama_3 == false
										end
									end
								end
							else
								wait(5)
								getgenv().ToTarget(game:GetService("Workspace").Map.HellDimension.Torch1.CFrame)
								wait(1.5)
								game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, game)
								wait(1.5)        
								getgenv().ToTarget(game:GetService("Workspace").Map.HellDimension.Torch2.CFrame)
								wait(1.5)
								game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, game)
								wait(1.5)     
								getgenv().ToTarget().ToTarget(game:GetService("Workspace").Map.HellDimension.Torch3.CFrame)
								wait(1.5)
								game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, game)
								wait(1.5)     
								getgenv().ToTarget().ToTarget(game:GetService("Workspace").Map.HellDimension.Exit.CFrame)
							end
						until _G.Auto_Cursed_Dual_Katana == false or Auto_Quest_Yama_3 == false or GetMaterial("Alucard Fragment") == 3
					else
						if game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
							if game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Soul Reaper [Lv. 2100] [Raid Boss]" then
										if v.Humanoid.Health > 0 then
											repeat wait()
												getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,0,-2))
											until _G.Auto_Cursed_Dual_Katana == false or Auto_Quest_Yama_3 == false or game:GetService("Workspace").Map:FindFirstChild("HellDimension")
										end
									end
								end
							else
								getgenv().ToTarget(CFrame.new(-9570.033203125, 315.9346923828125, 6726.89306640625))
							end
						else
							_G.Auto_Farm_Bone = true
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
						end
					end
				end)
			end
		end
	end)

	spawn(function() 
		while wait() do
			if Auto_Quest_Tushita_1 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","BoatQuest",workspace.NPCs:FindFirstChild("Luxury Boat Dealer"))
			end
		end
	end)

	spawn(function()
		while wait() do
			if Auto_Quest_Tushita_1 then
				BTP(CFrame.new(-9546.990234375, 21.139892578125, 4686.1142578125))
				wait(5)
				BTP(CFrame.new(-6120.0576171875, 16.455780029296875, -2250.697265625))
				wait(5)
				BTP(CFrame.new(-9533.2392578125, 7.254445552825928, -8372.69921875))    
			end
		end
	end)

	spawn(function()
		while wait() do
			if Auto_Quest_Tushita_2 then
				pcall(function()
					if (CFrame.new(-5539.3115234375, 313.800537109375, -2972.372314453125).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 500 then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if Auto_Quest_Tushita_2 and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
								if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2000 then
									repeat wait()
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
										game:GetService'VirtualUser':CaptureController()
										game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
									until v.Humanoid.Health <= 0 or not v.Parent or Auto_Quest_Tushita_2 == false
								end
							end
						end
					else
						getgenv().ToTarget(CFrame.new(-5545.1240234375, 313.800537109375, -2976.616455078125))
					end
				end)
			end
		end
	end)

	spawn(function()
		while wait() do
			if Auto_Quest_Tushita_3 then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") or game.ReplicatedStorage:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
						if game:GetService("Workspace").Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Cake Queen [Lv. 2175] [Boss]" then
									if v.Humanoid.Health > 0 then
										repeat wait()
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											v.HumanoidRootPart.Size = Vector3.new(60,60,60)
											v.Humanoid.JumpPower = 0
											v.Humanoid.WalkSpeed = 0
											v.HumanoidRootPart.CanCollide = false
											v.Humanoid:ChangeState(11)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
										until _G.Auto_Cursed_Dual_Katana == false or Auto_Quest_Tushita_3 == false or game:GetService("Workspace").Map:FindFirstChild("HeavenlyDimension")
									end
								end
							end
						else
							getgenv().ToTarget(CFrame.new(-709.3132934570312, 381.6005859375, -11011.396484375))
						end
					elseif game:GetService("Workspace").Map:FindFirstChild("HeavenlyDimension") then
						repeat wait()
							if game:GetService("Workspace").Enemies:FindFirstChild("Cursed Skeleton [Lv. 2200]") or game:GetService("Workspace").Enemies:FindFirstChild("Cursed Skeleton [Lv. 2200] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Heaven's Guardian [Lv. 2200] [Boss]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Cursed Skeleton [Lv. 2200]" or v.Name == "Cursed Skeleton [Lv. 2200] [Boss]" or v.Name == "Heaven's Guardian [Lv. 2200] [Boss]" then
										if v.Humanoid.Health > 0 then
											repeat wait()
												AutoHaki()
												EquipWeapon(_G.Select_Weapon)
												v.HumanoidRootPart.Size = Vector3.new(60,60,60)
												v.Humanoid.JumpPower = 0
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.CanCollide = false
												v.Humanoid:ChangeState(11)
											until v.Humanoid.Health <= 0 or not v.Parent or Auto_Quest_Tushita_3 == false
										end
									end
								end
							else
								wait(5)
								getgenv().ToTarget(game:GetService("Workspace").Map.HeavenlyDimension.Torch1.CFrame)
								wait(1.5)
								game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, game)
								wait(1.5)        
								getgenv().ToTarget(game:GetService("Workspace").Map.HeavenlyDimension.Torch2.CFrame)
								wait(1.5)
								game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, game)
								wait(1.5)     
								getgenv().ToTarget(game:GetService("Workspace").Map.HeavenlyDimension.Torch3.CFrame)
								wait(1.5)
								game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, game)
								wait(1.5)     
								getgenv().ToTarget(game:GetService("Workspace").Map.HeavenlyDimension.Exit.CFrame)
							end
						until _G.Auto_Cursed_Dual_Katana == false or Auto_Quest_Tushita_3 == false or GetMaterial("Alucard Fragment") == 6
					else
						Hop()
					end
				end)
			end
		end
	end)

	Tushita_Quest1 = nil
	-- Page_Main.Button({Title = "Tushita Quest : 1",callback = function()
	-- 	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadItem","Tushita")
	-- 	wait(1)
	-- 	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","StartTrial","Good")
	-- 	Tushita_Quest1 = true
	-- 	toTarget(CFrame.new(-6127.5712890625, 16.446542739868164, -2247.595703125))
	-- 	wait(60)
	-- 	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","BoatQuest", workspace.NPCs:FindFirstChild("Luxury Boat Dealer"))
	-- 	wait(1)
	-- 	toTarget(CFrame.new(-127.23313903808594, 6.755744934082031, 5259.51025390625))    
	-- 	wait(60)
	-- 	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","BoatQuest", workspace.NPCs:FindFirstChild("Luxury Boat Dealer"))
	-- 	wait(1)
	-- 	toTarget(CFrame.new(-2067.349365234375, 4.701088905334473, -9890.4501953125))
	-- 	wait(60)
	-- 	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest","BoatQuest", workspace.NPCs:FindFirstChild("Luxury Boat Dealer"))
	-- 	Tushita_Quest1 = false
	-- end})

	Tabs.Main:AddSection("Serpent Bow")

	local Toggle = Tabs.Main:AddToggle("Auto_Serpent_Bow", {Title = "Auto Serpent Bow", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Serpent_Bow = Options.Auto_Serpent_Bow.Value
		if Options.Auto_Serpent_Bow.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Serpent_Bow:SetValue(_G.Auto_Serpent_Bow)

	task.spawn(function()
		while wait() do
			if _G.Auto_Serpent_Bow then
				if game:GetService("Workspace").Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if v.Name == ("Island Empress [Lv. 1675] [Boss]" or v.Name == "Island Empress [Lv. 1675] [Boss]") and v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
							repeat wait()
								StartMagnet = true
								AutoHaki()
								EquipWeapon(_G.Select_Weapon)
								PosMon = v.HumanoidRootPart.CFrame
								v.HumanoidRootPart.Size = Vector3.new(60,60,60)
								v.Humanoid.JumpPower = 0
								v.Humanoid.WalkSpeed = 0
								v.HumanoidRootPart.CanCollide = false
								v.Humanoid:ChangeState(11)
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
							until not _G.Auto_Serpent_Bow or not v.Parent or v.Humanoid.Health <= 0
							StartMagnet = false
						end
					end
				else
					if _G.Auto_Serpent_Bow_Hop and not game:GetService("Workspace").Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
						Hop()
					else
						if (CFrame.new(5543.86328125, 668.97399902344, 199.0341796875).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
							BTP(CFrame.new(5543.86328125, 668.97399902344, 199.0341796875))
							return
						end
						getgenv().ToTarget(CFrame.new(5543.86328125, 668.97399902344, 199.0341796875))
					end
				end
			end
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Serpent_Bow_Hop", {Title = "Auto Serpent Bow Hop", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Serpent_Bow_Hop = Options.Auto_Serpent_Bow_Hop.Value
		SaveSettings()
	end)

	Options.Auto_Serpent_Bow_Hop:SetValue(_G.Auto_Serpent_Bow_Hop)

	Tabs.Main:AddSection("Dark Dagger")

	local Toggle = Tabs.Main:AddToggle("Auto_Dark_Dagger", {Title = "Auto Dark Dagger", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Dark_Dagger = Options.Auto_Dark_Dagger.Value
		if Options.Auto_Dark_Dagger.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Dark_Dagger:SetValue(_G.Auto_Dark_Dagger)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Dark_Dagger then
					if game:GetService("Workspace").Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == ("rip_indra True Form [Lv. 5000] [Raid Boss]" or v.Name == "rip_indra True Form [Lv. 5000] [Raid Boss]") and v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
								repeat wait()
									StartMagnet = true
									AutoHaki()
									EquipWeapon(_G.Select_Weapon)
									PosMon = v.HumanoidRootPart.CFrame
									v.HumanoidRootPart.Size = Vector3.new(60,60,60)
									v.Humanoid.JumpPower = 0
									v.Humanoid.WalkSpeed = 0
									v.HumanoidRootPart.CanCollide = false
									v.Humanoid:ChangeState(11)
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
								until not _G.Auto_Dark_Dagger or not v.Parent or v.Humanoid.Health <= 0
								StartMagnet = false
							end
						end
					else
						if _G.Auto_Dark_Dagger_Hop and not game:GetService("Workspace").Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
							Hop()
						else
							if (CFrame.new(-5344.822265625, 423.98541259766, -2725.0930175781).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
								BTP(CFrame.new(-5344.822265625, 423.98541259766, -2725.0930175781))
								return
							end
							getgenv().ToTarget(CFrame.new(-5344.822265625, 423.98541259766, -2725.0930175781))
						end
					end
				end
			end)
		end
	end)	

	local Toggle = Tabs.Main:AddToggle("Auto_Dark_Dagger_Hop", {Title = "Auto Dark Dagger Hop", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Dark_Dagger_Hop = Options.Auto_Dark_Dagger_Hop.Value
		SaveSettings()
	end)

	Options.Auto_Dark_Dagger_Hop:SetValue(_G.Auto_Dark_Dagger_Hop)

	Tabs.Main:AddSection("Rainbow Haki")

	local Toggle = Tabs.Main:AddToggle("Auto_Rainbow_Haki", {Title = "Auto Rainbow Haki", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Rainbow_Haki = Options.Auto_Rainbow_Haki.Value
		if Options.Auto_Rainbow_Haki.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Rainbow_Haki:SetValue(_G.Auto_Rainbow_Haki)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Rainbow_Haki then
					if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
						getgenv().ToTarget(CFrame.new(-11892.0703125, 930.57672119141, -8760.1591796875))
						if (Vector3.new(-11892.0703125, 930.57672119141, -8760.1591796875) - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 30 then
							wait(1.5)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("HornedMan","Bet")
						end
					elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true and string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Stone") then
						if game:GetService("Workspace").Enemies:FindFirstChild("Stone [Lv. 1550] [Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Stone [Lv. 1550] [Boss]" then
									repeat wait()
										StartMagnet = true
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										PosMon = v.HumanoidRootPart.CFrame
										v.HumanoidRootPart.Size = Vector3.new(60,60,60)
										v.Humanoid.JumpPower = 0
										v.Humanoid.WalkSpeed = 0
										v.HumanoidRootPart.CanCollide = false
										v.Humanoid:ChangeState(11)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until not _G.Auto_Rainbow_Haki or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
									StartMagnet = false
								end
							end
						else
							if _G.Auto_Rainbow_Haki_Hop and not game:GetService("Workspace").Enemies:FindFirstChild("Stone [Lv. 1550] [Boss]") then
								wait(10)
								Hop()
							else
								if (CFrame.new(-1086.11621, 38.8425903, 6768.71436, 0.0231462717, -0.592676699, 0.805107772, 2.03251839e-05, 0.805323839, 0.592835128, -0.999732077, -0.0137055516, 0.0186523199).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
									BTP(CFrame.new(CFrame.new(-1086.11621, 38.8425903, 6768.71436, 0.0231462717, -0.592676699, 0.805107772, 2.03251839e-05, 0.805323839, 0.592835128, -0.999732077, -0.0137055516, 0.0186523199)))
									return
								end
								getgenv().ToTarget(CFrame.new(-1086.11621, 38.8425903, 6768.71436, 0.0231462717, -0.592676699, 0.805107772, 2.03251839e-05, 0.805323839, 0.592835128, -0.999732077, -0.0137055516, 0.0186523199))
							end
						end
					elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true and string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Island Empress") then
						if game:GetService("Workspace").Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Island Empress [Lv. 1675] [Boss]" then
									repeat wait()
										StartMagnet = true
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										PosMon = v.HumanoidRootPart.CFrame
										v.HumanoidRootPart.Size = Vector3.new(60,60,60)
										v.Humanoid.JumpPower = 0
										v.Humanoid.WalkSpeed = 0
										v.HumanoidRootPart.CanCollide = false
										v.Humanoid:ChangeState(11)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until not _G.Auto_Rainbow_Haki or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
									StartMagnet = false
								end
							end
						else
							if _G.Auto_Rainbow_Haki_Hop and not game:GetService("Workspace").Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
								wait(10)
								Hop()
							else
								if (CFrame.new(5713.98877, 601.922974, 202.751251, -0.101080291, -0, -0.994878292, -0, 1, -0, 0.994878292, 0, -0.101080291).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
									BTP(CFrame.new(5713.98877, 601.922974, 202.751251, -0.101080291, -0, -0.994878292, -0, 1, -0, 0.994878292, 0, -0.101080291))
									return
								end
								getgenv().ToTarget(CFrame.new(5713.98877, 601.922974, 202.751251, -0.101080291, -0, -0.994878292, -0, 1, -0, 0.994878292, 0, -0.101080291))
							end
						end
					elseif string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Kilo Admiral") then
						if game:GetService("Workspace").Enemies:FindFirstChild("Kilo Admiral [Lv. 1750] [Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Kilo Admiral [Lv. 1750] [Boss]" then
									repeat wait()
										StartMagnet = true
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										PosMon = v.HumanoidRootPart.CFrame
										v.HumanoidRootPart.Size = Vector3.new(60,60,60)
										v.Humanoid.JumpPower = 0
										v.Humanoid.WalkSpeed = 0
										v.HumanoidRootPart.CanCollide = false
										v.Humanoid:ChangeState(11)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until not _G.Auto_Rainbow_Haki or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
									StartMagnet = false
								end
							end
						else
							if _G.Auto_Rainbow_Haki_Hop and not game:GetService("Workspace").Enemies:FindFirstChild("Kilo Admiral [Lv. 1750] [Boss]") then
								wait(10)
								Hop()
							else
								if (CFrame.new(2877.61743, 423.558685, -7207.31006, -0.989591599, -0, -0.143904909, -0, 1.00000012, -0, 0.143904924, 0, -0.989591479).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
									BTP(CFrame.new(2877.61743, 423.558685, -7207.31006, -0.989591599, -0, -0.143904909, -0, 1.00000012, -0, 0.143904924, 0, -0.989591479))
									return
								end
								getgenv().ToTarget(CFrame.new(2877.61743, 423.558685, -7207.31006, -0.989591599, -0, -0.143904909, -0, 1.00000012, -0, 0.143904924, 0, -0.989591479))
							end
						end
					elseif string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Captain Elephant") then
						if game:GetService("Workspace").Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Captain Elephant [Lv. 1875] [Boss]" then
									repeat wait()
										StartMagnet = true
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										PosMon = v.HumanoidRootPart.CFrame
										v.HumanoidRootPart.Size = Vector3.new(60,60,60)
										v.Humanoid.JumpPower = 0
										v.Humanoid.WalkSpeed = 0
										v.HumanoidRootPart.CanCollide = false
										v.Humanoid:ChangeState(11)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until not _G.Auto_Rainbow_Haki or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
									StartMagnet = false
								end
							end
						else
							if _G.Auto_Rainbow_Haki_Hop and not game:GetService("Workspace").Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
								wait(10)
								Hop()
							else
								if (CFrame.new(-13485.0283, 331.709259, -8012.4873, 0.714521289, 7.98849911e-08, 0.69961375, -1.02065748e-07, 1, -9.94383065e-09, -0.69961375, -6.43015241e-08, 0.714521289).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
									BTP(CFrame.new(-13485.0283, 331.709259, -8012.4873, 0.714521289, 7.98849911e-08, 0.69961375, -1.02065748e-07, 1, -9.94383065e-09, -0.69961375, -6.43015241e-08, 0.714521289))
									return
								end
								getgenv().ToTarget(CFrame.new(-13485.0283, 331.709259, -8012.4873, 0.714521289, 7.98849911e-08, 0.69961375, -1.02065748e-07, 1, -9.94383065e-09, -0.69961375, -6.43015241e-08, 0.714521289))
							end
						end
					elseif string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Beautiful Pirate") then
						if game:GetService("Workspace").Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Beautiful Pirate [Lv. 1950] [Boss]" then
									repeat wait()
										StartMagnet = true
										AutoHaki()
										EquipWeapon(_G.Select_Weapon)
										PosMon = v.HumanoidRootPart.CFrame
										v.HumanoidRootPart.Size = Vector3.new(60,60,60)
										v.Humanoid.JumpPower = 0
										v.Humanoid.WalkSpeed = 0
										v.HumanoidRootPart.CanCollide = false
										v.Humanoid:ChangeState(11)
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
									until not _G.Auto_Rainbow_Haki or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
									StartMagnet = false
								end
							end
						else
							if _G.Auto_Rainbow_Haki_Hop and not game:GetService("Workspace").Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
								wait(10)
								Hop()
							else
								if (CFrame.new(5312.3598632813, 20.141201019287, -10.158538818359).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
									BTP(CFrame.new(5312.3598632813, 20.141201019287, -10.158538818359))
									return
								end
								getgenv().ToTarget(CFrame.new(5312.3598632813, 20.141201019287, -10.158538818359))
							end
						end
					else
						if (CFrame.new(-11892.0703125, 930.57672119141, -8760.1591796875).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
							BTP(CFrame.new(-11892.0703125, 930.57672119141, -8760.1591796875))
							return
						end
						getgenv().ToTarget(CFrame.new(-11892.0703125, 930.57672119141, -8760.1591796875))
						if (Vector3.new(-11892.0703125, 930.57672119141, -8760.1591796875) - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 30 then
							wait(1.5)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("HornedMan","Bet")
						end
					end
				end
			end)
		end
	end)

	local Toggle = Tabs.Main:AddToggle("Auto_Rainbow_Haki_Hop", {Title = "Auto Rainbow Haki Hop", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Rainbow_Haki_Hop = Options.Auto_Rainbow_Haki_Hop.Value
		SaveSettings()
	end)

	Options.Auto_Rainbow_Haki_Hop:SetValue(_G.Auto_Rainbow_Haki_Hop)

	Tabs.Main:AddSection("Musketeer")

	local Toggle = Tabs.Main:AddToggle("Auto_Musketeer_Hat", {Title = "Auto Musketeer Hati", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Musketeer_Hat = Options.Auto_Musketeer_Hat.Value
		if Options.Auto_Musketeer_Hat.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Musketeer_Hat:SetValue(_G.Auto_Musketeer_Hat)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Musketeer_Hat then
					if game:GetService("Players").LocalPlayer.Data.Level.Value >= 1800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress").KilledBandits == false then
						if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Forest Pirate") and string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50") and game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
							if game:GetService("Workspace").Enemies:FindFirstChild("Forest Pirate [Lv. 1825]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Forest Pirate [Lv. 1825]" then
										repeat wait()
											StartMagnet = true
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											PosMon = v.HumanoidRootPart.CFrame
											v.HumanoidRootPart.Size = Vector3.new(60,60,60)
											v.Humanoid.JumpPower = 0
											v.Humanoid.WalkSpeed = 0
											v.HumanoidRootPart.CanCollide = false
											v.Humanoid:ChangeState(11)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										until not _G.Auto_Musketeer_Hat or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
										StartMagnet = false
									end
								end
							else
								if (CFrame.new(-13206.452148438, 425.89199829102, -7964.5537109375).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
									BTP(CFrame.new(-13206.452148438, 425.89199829102, -7964.5537109375))
									return
								end
								getgenv().ToTarget(CFrame.new(-13206.452148438, 425.89199829102, -7964.5537109375))
							end
						else
							if (CFrame.new(-12443.8671875, 332.40396118164, -7675.4892578125).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
								BTP(CFrame.new(-12443.8671875, 332.40396118164, -7675.4892578125))
								return
							end
							getgenv().ToTarget(CFrame.new(-12443.8671875, 332.40396118164, -7675.4892578125))
							if (Vector3.new(-12443.8671875, 332.40396118164, -7675.4892578125) - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 30 then
								wait(1.5)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest","CitizenQuest",1)
							end
						end
					elseif game:GetService("Players").LocalPlayer.Data.Level.Value >= 1800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress").KilledBoss == false then
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible and string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Captain Elephant") and game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
							if game:GetService("Workspace").Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Captain Elephant [Lv. 1875] [Boss]" then
										OldCFrameElephant = v.HumanoidRootPart.CFrame
										repeat wait()
											StartMagnet = true
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											PosMon = v.HumanoidRootPart.CFrame
											v.HumanoidRootPart.Size = Vector3.new(60,60,60)
											v.Humanoid.JumpPower = 0
											v.Humanoid.WalkSpeed = 0
											v.HumanoidRootPart.CanCollide = false
											v.Humanoid:ChangeState(11)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										until not  _G.Auto_Musketeer_Hat or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
										StartMagnet = false
									end
								end
							else
								if  _G.Auto_Musketeer_Hat_Hop and not game:GetService("Workspace").Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
									wait(10)
									Hop()
								else
									getgenv().ToTarget(CFrame.new(-13374.889648438, 421.27752685547, -8225.208984375))
								end
							end
						else
							getgenv().ToTarget(CFrame.new(-12443.8671875, 332.40396118164, -7675.4892578125))
							if (CFrame.new(-12443.8671875, 332.40396118164, -7675.4892578125).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4 then
								wait(1.5)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen")
							end
						end
					elseif game:GetService("Players").LocalPlayer.Data.Level.Value >= 1800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen") == 2 then
						if (CFrame.new(-12512.138671875, 340.39279174805, -9872.8203125).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
							BTP(CFrame.new(-12512.138671875, 340.39279174805, -9872.8203125))
							return
						end
						getgenv().ToTarget(CFrame.new(-12512.138671875, 340.39279174805, -9872.8203125))
					end
				end
			end)
		end
	end)


	local Toggle = Tabs.Main:AddToggle("Auto_Musketeer_Hat_Hop", {Title = "Auto Musketeer Hat Hop", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Musketeer_Hat_Hop = Options.Auto_Musketeer_Hat_Hop.Value
		SaveSettings()
	end)

	Options.Auto_Musketeer_Hat_Hop:SetValue(_G.Auto_Musketeer_Hat_Hop)

	Tabs.Main:AddSection("Other Function")

	local Toggle = Tabs.Main:AddToggle("Auto_Ken_Haki_V2", {Title = "Auto Ken Haki V2", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Ken_Haki_V2 = Options.Auto_Ken_Haki_V2.Value
		if Options.Auto_Ken_Haki_V2.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Ken_Haki_V2:SetValue(_G.Auto_Ken_Haki_V2)

	local Toggle = Tabs.Main:AddToggle("Teleport_to_Sea_Beast", {Title = "Teleport to Sea Beast", Default = false })

	Toggle:OnChanged(function()
		_G.Teleport_to_Sea_Beast = Options.Teleport_to_Sea_Beast.Value
		if Options.Teleport_to_Sea_Beast.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Teleport_to_Sea_Beast:SetValue(_G.Teleport_to_Sea_Beast)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Teleport_to_Sea_Beast then
					for i,v in pairs(game.Workspace.SeaBeasts:GetChildren()) do
						if v:FindFirstChild("HumanoidRootPart") then
							getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(1,500,1))
						end
					end
				end
			end)
		end
	end)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Ken_Haki_V2 then
					if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
						repeat 
							if (CFrame.new(-12444.78515625, 332.40396118164, -7673.1806640625).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
								BTP(CFrame.new(-12444.78515625, 332.40396118164, -7673.1806640625))
								return
							end
							getgenv().ToTarget(CFrame.new(-12444.78515625, 332.40396118164, -7673.1806640625)) 
							wait() 
						until not _G.Auto_Ken_Haki_V2 or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-12444.78515625, 332.40396118164, -7673.1806640625)).Magnitude <= 10
						wait(.5)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen")
						wait(1)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest","CitizenQuest",1)
					else
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Banana") and  game.Players.LocalPlayer.Backpack:FindFirstChild("Apple") and game.Players.LocalPlayer.Backpack:FindFirstChild("Pineapple") then
							repeat 
								getgenv().ToTarget(CFrame.new(-12444.78515625, 332.40396118164, -7673.1806640625)) 
								wait() 
							until not _G.Auto_Ken_Haki_V2 or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-12444.78515625, 332.40396118164, -7673.1806640625)).Magnitude <= 10
							wait(.5)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen")
						elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Fruit Bowl") or game.Players.LocalPlayer.Character:FindFirstChild("Fruit Bowl") then
							repeat 
								getgenv().ToTarget(CFrame.new(-10920.125, 624.20275878906, -10266.995117188)) 
								wait() 
							until not _G.Auto_Ken_Haki_V2 or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-10920.125, 624.20275878906, -10266.995117188)).Magnitude <= 10
							wait(.5)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk2","Start")
							wait(1)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk2","Buy")
						elseif string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,"Defeat 50 Forest Pirates") then
							if game:GetService("Workspace").Enemies:FindFirstChild("Forest Pirate [Lv. 1825]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Forest Pirate [Lv. 1825]" then
										repeat wait()
											StartMagnet = true
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											PosMon = v.HumanoidRootPart.CFrame
											v.HumanoidRootPart.Size = Vector3.new(60,60,60)
											v.Humanoid.JumpPower = 0
											v.Humanoid.WalkSpeed = 0
											v.HumanoidRootPart.CanCollide = false
											v.Humanoid:ChangeState(11)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										until not _G.Auto_Ken_Haki_V2 or v.Humanoid.Health <= 0
										StartMagnet = false
									end
								end
							else
								repeat 
									getgenv().ToTarget(CFrame.new(-13277.568359375, 370.34185791016, -7821.1572265625)) 
									wait() 
								until not _G.Auto_Ken_Haki_V2 or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-13277.568359375, 370.34185791016, -7821.1572265625)).Magnitude <= 10
							end
						elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text ==  "Defeat  Captain Elephant (0/1)" then 
							if game:GetService("Workspace").Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if v.Name == "Captain Elephant [Lv. 1875] [Boss]" then
										repeat wait()
											StartMagnet = true
											AutoHaki()
											EquipWeapon(_G.Select_Weapon)
											PosMon = v.HumanoidRootPart.CFrame
											v.HumanoidRootPart.Size = Vector3.new(60,60,60)
											v.Humanoid.JumpPower = 0
											v.Humanoid.WalkSpeed = 0
											v.HumanoidRootPart.CanCollide = false
											v.Humanoid:ChangeState(11)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
										until not _G.Auto_Ken_Haki_V2 or v.Humanoid.Health <= 0
										StartMagnet = false
									end
								end
							else
								repeat 
									getgenv().ToTarget(CFrame.new(-13493.12890625, 318.89553833008, -8373.7919921875)) 
									wait() 
								until not _G.Auto_Ken_Haki_V2 or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-13493.12890625, 318.89553833008, -8373.7919921875)).Magnitude <= 10
							end
						else
							for i,v in pairs(game.Workspace:GetDescendants()) do
								if v.Name == "Apple" or v.Name == "Banana" or v.Name == "Pineapple" then
									v.Handle.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,1,10)
									wait()
									firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart,v.Handle,0)    
									wait()
								end
							end  
						end
					end
				end
			end)
		end
	end)

end

Tabs.Main:AddSection("Fighting Style")

local Toggle = Tabs.Main:AddToggle("AutoSuperhuman", {Title = "Auto Superhuman", Default = false })

Toggle:OnChanged(function()
	_G.AutoSuperhuman = Options.AutoSuperhuman.Value
	if Options.AutoSuperhuman.Value == false then
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
	SaveSettings()
end)

Options.AutoSuperhuman:SetValue(_G.AutoSuperhuma)


task.spawn(function()
	while wait() do
		pcall(function()
			if _G.AutoSuperhuman then
				if game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
					if not game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") and not game.Players.LocalPlayer.Character:FindFirstChild("Combat") then
						if not game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and not game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") then
							if not game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and not game.Players.LocalPlayer.Character:FindFirstChild("Electro") then
								if not game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and not game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") then
									if not game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and not game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") then
										if not game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman") and not game.Players.LocalPlayer.Character:FindFirstChild("Superhuman") then
											local args = {
												[1] = "BuyElectro"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
									end
								end
							end
						end
					end

					_G.Select_Weapon = "Melee"

					if game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") or game.Players.LocalPlayer.Character:FindFirstChild("Combat") then
						local args = {
							[1] = "BuyElectro"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 300 then
						local args = {
							[1] = "BuyBlackLeg"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 300 then
						local args = {
							[1] = "BuyBlackLeg"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 300 then
						local args = {
							[1] = "BuyFishmanKarate"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 300 then
						local args = {
							[1] = "BuyFishmanKarate"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 300  then
						local args = {
							[1] = "BlackbeardReward",
							[2] = "DragonClaw",
							[3] = "2"
						}
						HaveDragonClaw = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						if _G.AutoSuperhuman and game.Players.LocalPlayer.Data.Fragments.Value <= 1500 and HaveDragonClaw == 0 then
							if game.Players.LocalPlayer.Data.Level.Value > 1100 then
								_G.Select_Dungeon = "Flame"
								_G.Auto_Buy_Chips_Dungeon = true
								_G.Auto_Start_Dungeon = true
								_G.Auto_Next_Island = true
								if _G.Auto_Farm_Level then _G.Auto_Farm_Level = false end
							end
						else
							_G.Auto_Start_Dungeon = false
							_G.Auto_Next_Island = false
							_G.Auto_Buy_Chips_Dungeon = false
							if _G.Auto_Farm_Level then _G.Auto_Farm_Level = true end
							local args = {
								[1] = "BlackbeardReward",
								[2] = "DragonClaw",
								[3] = "2"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							_G.Auto_Start_Dungeon = false
							if _G.Auto_Farm_Level then _G.Auto_Farm_Level = true end
						end
					end
					if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 300  then
						local args = {
							[1] = "BlackbeardReward",
							[2] = "DragonClaw",
							[3] = "2"
						}
						HaveDragonClaw = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						if _G.AutoSuperhuman and game.Players.LocalPlayer.Data.Fragments.Value <= 1500 and HaveDragonClaw == 0 then
							if game.Players.LocalPlayer.Data.Level.Value > 1100 then
								_G.Select_Dungeon = "Flame"
								_G.Auto_Buy_Chips_Dungeon = true
								_G.Auto_Start_Dungeon = true
								_G.Auto_Next_Island = true
								if _G.Auto_Farm_Level then _G.Auto_Farm_Level = false end
							end
						else
							_G.Auto_Start_Dungeon = false
							_G.Auto_Next_Island = false
							_G.Auto_Buy_Chips_Dungeon = false
							if _G.Auto_Farm_Level then _G.Auto_Farm_Level = true end
							local args = {
								[1] = "BlackbeardReward",
								[2] = "DragonClaw",
								[3] = "2"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							_G.Auto_Start_Dungeon = false
							_G.Auto_Next_Island = false
							_G.Auto_Buy_Chips_Dungeon = false
							if _G.Auto_Farm_Level then _G.Auto_Farm_Level = true end
						end
					end

					if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 300 then
						_G.Auto_Farm_Level = _G.Auto_Farm_Level
						local args = {
							[1] = "BuySuperhuman"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 300 then
						_G.Auto_Farm_Level = _G.Auto_Farm_Level
						local args = {
							[1] = "BuySuperhuman"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end 
				end
			end
		end)
	end
end)

local Toggle = Tabs.Main:AddToggle("AutoDeathStep", {Title = "Auto Death Step", Default = false })

Toggle:OnChanged(function()
	_G.AutoDeathStep = Options.AutoDeathStep.Value
	SaveSettings()
end)

Options.AutoDeathStep:SetValue(_G.AutoDeathStep)

task.spawn(function()
	while wait() do
		pcall(function()
			if _G.AutoDeathStep then
				if game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 400 then
						local args = {
							[1] = "BuyDeathStep"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						_G.Select_Weapon = "Death Step"
					end  
					if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 400 then
						local args = {
							[1] = "BuyDeathStep"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))

						_G.Select_Weapon = "Death Step"
					end  
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value < 400 then
						_G.Select_Weapon = "Black Leg"
					end 
				end
			elseif _G.Auto_Fully_DeathStep then
				if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 400 or game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 400 then
					if game:GetService("Workspace").Map.IceCastle.Hall.LibraryDoor.PhoeyuDoor.Transparency == 0 then  
						if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Library Key") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Library Key") then
							EquipWeapon("Library Key")
							repeat wait() getgenv().ToTarget(CFrame.new(6371.2001953125, 296.63433837890625, -6841.18115234375)) until (CFrame.new(6371.2001953125, 296.63433837890625, -6841.18115234375).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.AutoDeathStep
							if (CFrame.new(6371.2001953125, 296.63433837890625, -6841.18115234375).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
								wait(1.2)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep",true)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
								wait(0.5)
							end
						elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 450 or game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 450 then   
							if game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
								if game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then 	
									for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
										if v.Name == "Awakened Ice Admiral [Lv. 1400] [Boss]" then    
											repeat wait()
												if game.Workspace.Enemies:FindFirstChild(v.Name) then
													if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 200 then
														Farmtween = getgenv().ToTarget(v.HumanoidRootPart.CFrame)
													elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 200 then
														if Farmtween then Farmtween:Stop() end
														AutoHaki()
														EquipWeapon(_G.Select_Weapon)
														v.HumanoidRootPart.Size = Vector3.new(60,60,60)
														v.Humanoid.JumpPower = 0
														v.Humanoid.WalkSpeed = 0
														v.HumanoidRootPart.CanCollide = false

														getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
													end
												end
											until not v.Parent or v.Humanoid.Health <= 0 or _G.AutoDeathStep == false or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Library Key") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Library Key")
										end
									end
								else
									getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]").HumanoidRootPart.CFrame)
								end
							end
						end
					end
				else
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBlackLeg")
				end
			end
		end)
	end
end)

local Toggle = Tabs.Main:AddToggle("AutoSharkManKarate", {Title = "Auto SharkMan Karate", Default = false })

Toggle:OnChanged(function()
	_G.AutoSharkManKarate = Options.AutoSharkManKarate.Value
	SaveSettings()
end)

Options.AutoSharkManKarate:SetValue(_G.AutoSharkManKarate)

task.spawn(function()
	while wait() do
		pcall(function()
			if _G.AutoSharkManKarate then
				if game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
					if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Fishman Karate") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fishman Karate") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Sharkman Karate") then
						if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 400 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
							_G.Select_Weapon = "Sharkman Karate"
						end  
						if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fishman Karate") and game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 400 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
							_G.Select_Weapon = "Sharkman Karate"
						end  
						if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 400 then
							_G.Select_Weapon = "Fishman Karate"
						end 
					else 
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
					end
				end
			elseif _G.Auto_Fully_SharkMan_Karate then
				if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 400 or game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 400 then
					if string.find(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate"), "keys") then  
						if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Water Key") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Water Key") then
							repeat wait() getgenv().ToTarget(-2604.6958, 239.432526, -10315.1982, 0.0425701365, 0, -0.999093413, 0, 1, 0, 0.999093413, 0, 0.0425701365) until (CFrame.new(-2604.6958, 239.432526, -10315.1982, 0.0425701365, 0, -0.999093413, 0, 1, 0, 0.999093413, 0, 0.0425701365).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_Fully_SharkMan_Karate
							if (CFrame.new(-2604.6958, 239.432526, -10315.1982, 0.0425701365, 0, -0.999093413, 0, 1, 0, 0.999093413, 0, 0.0425701365).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
								wait(1.2)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
								wait(0.5)
							end
						elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 400 or game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 400 then   
							if game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
								if game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then 	
									for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
										if v.Name == "Tide Keeper [Lv. 1475] [Boss]" then    
											repeat wait()
												if game.Workspace.Enemies:FindFirstChild(v.Name) then
													if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 200 then
														Farmtween = getgenv().ToTarget(v.HumanoidRootPart.CFrame)
													elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 200 then
														if Farmtween then Farmtween:Stop() end
														FastAttack = true
														AutoHaki()
														EquipWeapon(_G.Select_Weapon)
														v.HumanoidRootPart.Size = Vector3.new(60,60,60)
														v.Humanoid.JumpPower = 0
														v.Humanoid.WalkSpeed = 0
														v.HumanoidRootPart.CanCollide = false
														v.Humanoid:ChangeState(11)
														getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
													end
												end
											until not v.Parent or v.Humanoid.Health <= 0 or _G.AutoDeathStep == false or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Library Key") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Library Key")
										end
									end
								else
									getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]").HumanoidRootPart.CFrame)
								end
							end
						end
					else 
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
					end
				else
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
				end
			end
		end)
	end
end)

if World2 then

	Tabs.Main:AddSection("Fully Fighting Style")


	local Toggle = Tabs.Main:AddToggle("Auto_Fully_SharkMan_Karate", {Title = "Auto Fully SharkMan Karate", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Fully_SharkMan_Karate = Options.Auto_Fully_SharkMan_Karate.Value
		if Options.Auto_Fully_SharkMan_Karate.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Fully_SharkMan_Karate:SetValue(_G.Auto_Fully_SharkMan_Karate)

	local Toggle = Tabs.Main:AddToggle("Auto_Fully_DeathStep", {Title = "Auto Fully DeathStep", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Fully_DeathStep = Options.Auto_Fully_DeathStep.Value
		if Options.Auto_Fully_DeathStep.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Fully_DeathStep:SetValue(_G.Auto_Fully_DeathStep)

end

if World3 then
	local Toggle = Tabs.Main:AddToggle("Auto_Electric_Claw", {Title = "Auto Electric Claw", Default = false })

	Toggle:OnChanged(function()
		_G.Auto_Electric_Claw = Options.Auto_Electric_Claw.Value
		if Options.Auto_Electric_Claw.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Auto_Electric_Claw:SetValue(_G.Auto_Electric_Claw)

	spawn(function()
		while task.wait() do 
			pcall(function()
				if _G.Auto_Electric_Claw then
					if game.Players.LocalPlayer.Character:FindFirstChild("Superhuman") and game.Players.LocalPlayer.Character:FindFirstChild("Superhuman").Level.Value >= 300 and _G.Auto_Superhuman == false then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
					end
					if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro") then
						if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro") and game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400 then
							if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw",true) == 1 then
								if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electric Claw") or game:GetService("Players").LocalPlayer.backpack:FindFirstChild("Electric Claw") then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
								end
							else
								repeat task.wait() getgenv().ToTarget(CFrame.new(-10371.4717, 330.764496, -10131.4199)) until not _G.Auto_Electric_Claw or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position - CFrame.new(-10371.4717, 330.764496, -10131.4199).Position).Magnitude <= 10
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw","Start")
								wait(2)
								repeat task.wait() getgenv().ToTarget(CFrame.new(-12550.532226563, 336.22631835938, -7510.4233398438)) until not _G.Auto_Electric_Claw or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position - CFrame.new(-12550.532226563, 336.22631835938, -7510.4233398438).Position).Magnitude <= 10
								wait(1)
								repeat task.wait() getgenv().ToTarget(CFrame.new(-10371.4717, 330.764496, -10131.4199)) until not _G.Auto_Electric_Claw or (game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position - CFrame.new(-10371.4717, 330.764496, -10131.4199).Position).Magnitude <= 10
								wait(1)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
								wait(0.5)
							end
						end
					end
				end
			end)
		end
	end)
end

local Toggle = Tabs.Main:AddToggle("Auto_Dragon_Talon", {Title = "Auto Dragon Talon", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Dragon_Talon = Options.Auto_Dragon_Talon.Value
	if Options.Auto_Dragon_Talon.Value == false then
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
	SaveSettings()
end)

Options.Auto_Dragon_Talon:SetValue(_G.Auto_Dragon_Talon)

task.spawn(function()
	while wait() do
		pcall(function()
			if _G.Auto_Dragon_Talon then
				if game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 399 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
						_G.Select_Weapon = "Dragon Claw"
					end
					if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value <= 399 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
						_G.Select_Weapon = "Dragon Claw"
					end
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
						_G.Select_Weapon = "Dragon Claw"
						if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 3 then
							local string_1 = "Bones";
							local string_2 = "Buy";
							local number_1 = 1;
							local number_2 = 1;
							local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
							Target:InvokeServer(string_1, string_2, number_1, number_2);

							local string_1 = "BuyDragonTalon";
							local bool_1 = true;
							local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
							Target:InvokeServer(string_1, bool_1);
						elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 1 then
							game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
						else
							local string_1 = "BuyDragonTalon";
							local bool_1 = true;
							local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
							Target:InvokeServer(string_1, bool_1);
							local string_1 = "BuyDragonTalon";
							local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
							Target:InvokeServer(string_1);
						end 
					end

					if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
						_G.Select_Weapon = "Dragon Claw"
						if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 3 then
							local string_1 = "Bones";
							local string_2 = "Buy";
							local number_1 = 1;
							local number_2 = 1;
							local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
							Target:InvokeServer(string_1, string_2, number_1, number_2);

							local string_1 = "BuyDragonTalon";
							local bool_1 = true;
							local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
							Target:InvokeServer(string_1, bool_1);
						elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 1 then
							game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
						else
							local string_1 = "BuyDragonTalon";
							local bool_1 = true;
							local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
							Target:InvokeServer(string_1, bool_1);
							local string_1 = "BuyDragonTalon";
							local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
							Target:InvokeServer(string_1);
						end 
					end
				end
			end
		end)
	end
end)

if not World1 then

	local Toggle = Tabs.Main:AddToggle("Teleport_to_Sea_Beast", {Title = "Teleport to Sea Beast", Default = false })

	Toggle:OnChanged(function()
		_G.Teleport_to_Sea_Beast = Options.Teleport_to_Sea_Beast.Value
		if Options.Teleport_to_Sea_Beast.Value == false then
			getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
		SaveSettings()
	end)

	Options.Teleport_to_Sea_Beast:SetValue(_G.Teleport_to_Sea_Beast)

	task.spawn(function()
		while wait() do
			pcall(function()
				if _G.Teleport_to_Sea_Beast then
					for i,v in pairs(game.Workspace.SeaBeasts:GetChildren()) do
						if v:FindFirstChild("HumanoidRootPart") then
							getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(1,500,1))
						end
					end
				end
			end)
		end
	end)

end

Tabs.Settings:AddSection("Settings")

task.spawn(function()
	while wait() do
		pcall(function()
			if SelectWeapon == "Melee" then
				for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v.ToolTip == "Melee" then
						if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
							_G.Select_Weapon = v.Name
						end
					end
				end
			elseif SelectWeapon == "Sword" then
				for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v.ToolTip == "Sword" then
						if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
							_G.Select_Weapon = v.Name
						end
					end
				end
			elseif SelectWeapon == "Fruit" then
				for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v.ToolTip == "Blox Fruit" then
						if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
							_G.Select_Weapon = v.Name
						end
					end
				end
			else
				for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v.ToolTip == "Melee" then
						if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
							_G.Select_Weapon = v.Name
						end
					end
				end
			end
		end)
	end
end)

local Weapon = Tabs.Settings:AddDropdown("Weapon", {
	Title = "Select Weapon",
	Values = {"Melee","Sword","Fruit"},
	Multi = false,
	Default = 1,
})

Weapon:SetValue("Melee")

Weapon:OnChanged(function(Value)
	SelectWeapon = Value
end)

Tabs.Settings:AddSection("Set up Function")

local Toggle = Tabs.Settings:AddToggle("Disabled_Damage_Text", {Title = "Disabled Damage Text", Default = false })

_G.PlayerName = game.Players.LocalPlayer.Name
Toggle:OnChanged(function()
	_G.Disabled_Damage_Text = Options.Disabled_Damage_Text.Value
	if Options.Disabled_Damage_Text.Value then
		game:GetService("Players")[_G.PlayerName].PlayerGui.Notifications.Enabled = false
	else
		game:GetService("Players")[_G.PlayerName].PlayerGui.Notifications.Enabled = true
	end
end)

Options.Disabled_Damage_Text:SetValue(_G.Disabled_Damage_Text)

local Toggle = Tabs.Settings:AddToggle("Fast", {Title = "Fast Attack", Default = false })

Toggle:OnChanged(function()
	_G.FastAttack = Options.Fast.Value
	SaveSettings()
end)

function getHits(Size)
	local Hits = {}
	local nearbymon = false

	if nearbymon then
		local Enemies = workspace.Enemies:GetChildren()
		local Characters = workspace.Characters:GetChildren()

		for i = 1, #Enemies do
			local v = Enemies[i]
			local Human = v:FindFirstChildOfClass("Humanoid")

			if Human and Human.RootPart and Human.Health > 0 and dist(Human.RootPart.Position) < Size + 5 then
				table.insert(Hits, Human.RootPart)
			end
		end

		for i = 1, #Characters do
			local v = Characters[i]

			if v ~= Client.Character then
				local Human = v:FindFirstChildOfClass("Humanoid")

				if Human and Human.RootPart and Human.Health > 0 and dist(Human.RootPart.Position) < Size + 5 then
					table.insert(Hits, Human.RootPart)
				end
			end
		end
	end

	return Hits
end

Players = game.Players
Client = Players.LocalPlayer
Character = Client.Character:GetChildren()
Char = Client.Character
Root = Char.HumanoidRootPart
RunService = game:GetService("RunService")
vim = game:GetService('VirtualInputManager')
CollectionService = game:GetService("CollectionService")

CurrentAllMob = {}
canHits = {}

local CameraShaker = require(game.ReplicatedStorage.Util.CameraShaker)
CameraShaker:Stop()

local PC = require(Client.PlayerScripts.CombatFramework.Particle)
local RL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
local RigC = getupvalue(require(Client.PlayerScripts.CombatFramework.RigController), 2)
local Combat = getupvalue(require(Client.PlayerScripts.CombatFramework), 2)

task.spawn(function()
	pcall(function()
		local stacking = 0
		local printCooldown = 0

		while wait(0.075) do
			nearbymon = false
			CurrentAllMob = {}
			canHits = {}
			local mobs = CollectionService:GetTagged("ActiveRig")

			for i = 1, #mobs do
				local v = mobs[i]
				Human = v:FindFirstChildOfClass("Humanoid")

				if Human and Human.Health > 0 and Human.RootPart and v ~= Char then
					local IsPlayer = game.Players:GetPlayerFromCharacter(v)
					local IsAlly = IsPlayer and CollectionService:HasTag(IsPlayer, "Ally" .. Client.Name)

					if not IsAlly then
						CurrentAllMob[#CurrentAllMob + 1] = v

						if not nearbymon and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 50 then
							nearbymon = true
						end
					end
				end
			end

			if nearbymon then
				local Enemies = workspace.Enemies:GetChildren()
				local Players = Players:GetPlayers()

				for i = 1, #Enemies do
					local v = Enemies[i]
					local Human = v:FindFirstChildOfClass("Humanoid")

					if Human and Human.RootPart and Human.Health > 0 and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 50 then
						canHits[#canHits + 1] = Human.RootPart
					end
				end

				for i = 1, #Players do
					local v = Players[i].Character

					if not Players[i]:GetAttribute("PvpDisabled") and v and v ~= Client.Character then
						local Human = v:FindFirstChildOfClass("Humanoid")

						if Human and Human.RootPart and Human.Health > 0 and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 50 then
							canHits[#canHits + 1] = Human.RootPart
						end
					end
				end
			end
		end
	end)
end)

local Data = Combat
local Blank = function() end
local RigEvent = game:GetService("ReplicatedStorage").RigControllerEvent
local Validator = game.ReplicatedStorage.Remotes.Validator
local Animation = Instance.new("Animation")
local RecentlyFired = 0
local AttackCD = 0
local Controller
local lastFireValid = 0
local MaxLag = 350
local fucker = 0.07
local TryLag = 0

local resetCD = function()
	local WeaponName = Controller.currentWeaponModel.Name
	local Cooldown = {
		combat = 0.07
	}
	AttackCD = tick() + (fucker and Cooldown[WeaponName:lower()] or fucker or 0.285) + ((TryLag / MaxLag) * 0.3)
	RigEvent:FireServer("weaponChange", WeaponName)
	TryLag = TryLag + 0.8
	task.delay((fucker or 0.285) + (TryLag + 0.5 / MaxLag) * 0.3, function()
		TryLag = TryLag - 0.8
	end)
end

if not shared.orl then
	shared.orl = RL.wrapAttackAnimationAsync
end

if not shared.cpc then
	shared.cpc = PC.play
end

if not shared.dnew then
	shared.dnew = DMG.new
end

if not shared.attack then
	shared.attack = RigC.attack
end

RL.wrapAttackAnimationAsync = function(a, b, c, d, func)
	if not _G.FastAttack then
		PC.play = shared.cpc
		return shared.orl(a, b, c, 65, func)
	end

	local Radius = (_G.FastAttack and _G.FastAttack) or 50

	if canHits and #canHits > 0 then
		PC.play = function() end
		a:Play(0.02, 0.02, 0.02)
		func(canHits)
		wait(a.length * 0.5)
		a:Stop()
	end
end

task.spawn(function()
	pcall(function()
		local Data = Combat
		local Blank = function() end
		local RigEvent = game:GetService("ReplicatedStorage").RigControllerEvent
		local Animation = Instance.new("Animation")
		local RecentlyFired = 0
		local AttackCD = 0
		local Controller
		local lastFireValid = 0
		local MaxLag = 350
		local fucker = 0.07
		local TryLag = 0

		local resetCD = function()
			local WeaponName = Controller.currentWeaponModel.Name
			local Cooldown = {
				combat = 0.07
			}
			AttackCD = tick() + (fucker and Cooldown[WeaponName:lower()] or fucker or 0.285) + ((TryLag / MaxLag) * 0.3)
			RigEvent:FireServer("weaponChange", WeaponName)
			TryLag = TryLag + 0.8
			task.delay((fucker or 0.285) + (TryLag + 0.5 / MaxLag) * 0.3, function()
				TryLag = TryLag - 0.8
			end)
		end

		if not shared.orl then
			shared.orl = RL.wrapAttackAnimationAsync
		end

		if not shared.cpc then
			shared.cpc = PC.play
		end

		if not shared.dnew then
			shared.dnew = DMG.new
		end

		if not shared.attack then
			shared.attack = RigC.attack
		end

		RL.wrapAttackAnimationAsync = function(a, b, c, d, func)
			if not _G.FastAttack then
				PC.play = shared.cpc
				return shared.orl(a, b, c, 50, func)
			end

			local Radius = _G.FastAttack or 50

			if canHits and #canHits > 0 then
				PC.play = function() end
				a:Play(0.02, 0.02, 0.02)
				func(canHits)
				wait(a.length * 0.5)
				a:Stop()
			end
		end

		while RunService.Stepped:Wait() do
			if #canHits > 0 then
				Controller = Data.activeController

				if Controller and Controller.equipped and Controller.currentWeaponModel then
					if _G.FastAttack then
						if _G.FastAttack and tick() > AttackCD then
							resetCD()
						end

						if tick() - lastFireValid > 0.5 or not _G.FastAttack then
							Controller.timeToNextAttack = 0
							Controller.hitboxMagnitude = 65
							pcall(task.spawn, Controller.attack, Controller)
							lastFireValid = tick()
							for i = 1, 10 do
								if i % 2 == 0 then
									break
								end
							end
						end

						local AID3 = Controller.anims.basic[3]
						local AID2 = Controller.anims.basic[2]
						local ID = AID3 or AID2
						Animation.AnimationId = ID
						local Playing = Controller.humanoid:LoadAnimation(Animation)
						Playing:Play(0.02, 0.02, 0.02)
						RigEvent:FireServer("hit", canHits, AID3 and 3 or 2, "")
						-- AttackSignal:Fire()
						delay(0.5, function()
							Playing:Stop()
						end)
					end
				end
			end
		end
	end)
end)


Options.Fast:SetValue(_G.FastAttack)

local Toggle = Tabs.Settings:AddToggle("Brimob", {Title = "Bring Mob", Default = false })

Toggle:OnChanged(function()
	_G.Bring_Mob = Options.Brimob.Value
	SaveSettings()
end)

Options.Brimob:SetValue(_G.Bring_Mob)


spawn(function()
	while task.wait() do
		pcall(function()
			if _G.Bring_Mob then
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if _G.Auto_Farm_Level and BringMobFarm and v.Name == QuestCheck()[3] and (v.HumanoidRootPart.Position - PosMon.Position).Magnitude <= 225 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then	
						getgenv().ToTarget(v.HumanoidRootPart.CFrame == PosMon)
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
					elseif _G.Auto_Farm_Bone and PosMonBone and (v.Name == "Reborn Skeleton [Lv. 1975]" or v.Name == "Living Zombie [Lv. 2000]" or v.Name == "Demonic Soul [Lv. 2025]" or v.Name == "Posessed Mummy [Lv. 2050]") and (v.HumanoidRootPart.Position - PosMonBone.Position).magnitude <= 225 then
						getgenv().ToTarget(v.HumanoidRootPart.CFrame == PosMonBone)
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					elseif _G.Auto_Cake_Prince and StartCakeMagnet and (v.Name == "Cookie Crafter [Lv. 2200]" or v.Name == "Cake Guard [Lv. 2225]" or v.Name == "Baking Staff [Lv. 2250]" or v.Name == "Head Baker [Lv. 2275]") and (v.HumanoidRootPart.Position - POSCAKE.Position).magnitude <= 225 then
						getgenv().ToTarget(v.HumanoidRootPart.CFrame == POSCAKE)
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					elseif _G.Auto_Musketeer_Hat and (v.HumanoidRootPart.Position - PosMon.Position).magnitude <= 225 then
						getgenv().ToTarget(v.HumanoidRootPart.CFrame == PosMon)
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					elseif _G.Auto_Farm_Mob_Aura and (v.HumanoidRootPart.Position - PosMonAura.Position).magnitude <= 225 then
						getgenv().ToTarget(v.HumanoidRootPart.CFrame == PosMonAura)
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					elseif _G.Auto_Rengoku and StartMagnet and (v.Name == "Snow Lurker [Lv. 1375]" or v.Name == "Arctic Warrior [Lv. 1350]") and (v.HumanoidRootPart.Position - PosMon.Position).Magnitude <= 250 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
						v.Humanoid:ChangeState(14)
						v.HumanoidRootPart.CanCollide = false
						v.Head.CanCollide = false
						v.HumanoidRootPart.CFrame = PosMon
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
					elseif _G.Auto_EvoRace and StartEvoMagnet and v.Name == "Zombie [Lv. 950]" and (v.HumanoidRootPart.Position - PosMonEvo.Position).Magnitude <= 250 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
						v.Humanoid:ChangeState(14)
						v.HumanoidRootPart.CanCollide = false
						v.Head.CanCollide = false
						v.HumanoidRootPart.CFrame = PosMonEvo
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
					elseif _G.Auto_Bartilo and StartMagnet and v.Name == "Swan Pirate [Lv. 775]" and (v.HumanoidRootPart.Position - PosMonBarto.Position).Magnitude <= 250 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
						v.Humanoid:ChangeState(14)
						v.HumanoidRootPart.CanCollide = false
						v.Head.CanCollide = false
						v.HumanoidRootPart.CFrame = PosMon
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
					elseif _G.Auto_Farm_Gun_Mastery and StartMasteryGunMagnet and v.Name == "Monkey [Lv. 14]" and (v.HumanoidRootPart.Position - PosMonMasteryGun.Position).Magnitude <= 225 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						v.Humanoid:ChangeState(14)
						v.HumanoidRootPart.CanCollide = false
						v.Head.CanCollide = false
						getgenv().ToTarget(v.HumanoidRootPart.CFrame == PosMonMasteryGun)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
					elseif v.Name == "Factory Staff [Lv. 800]" and (v.HumanoidRootPart.Position - PosMonMasteryGun.Position).Magnitude <= 225 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						v.Humanoid:ChangeState(14)
						v.HumanoidRootPart.CanCollide = false
						v.Head.CanCollide = false
						getgenv().ToTarget(v.HumanoidRootPart.CFrame == PosMonMasteryGun)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
					elseif v.Name == QuestCheck()[3] and (v.HumanoidRootPart.Position - PosMonMasteryGun.Position).Magnitude <= 225 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						v.Humanoid:ChangeState(14)
						v.HumanoidRootPart.CanCollide = false
						v.Head.CanCollide = false
						getgenv().ToTarget(v.HumanoidRootPart.CFrame == PosMonMasteryGun)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
					elseif _G.Auto_Farm_BF_Mastery and StartMasteryFruitMagnet and v.Name == "Monkey [Lv. 14]" and (v.HumanoidRootPart.Position - PosMonMasteryFruit.Position).Magnitude <= 225 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						v.Humanoid:ChangeState(14)
						v.HumanoidRootPart.CanCollide = false
						v.Head.CanCollide = false
						getgenv().ToTarget(v.HumanoidRootPart.CFrame == PosMonMasteryFruit)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
					elseif v.Name == "Factory Staff [Lv. 800]" and (v.HumanoidRootPart.Position - PosMonMasteryFruit.Position).Magnitude <= 225 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						v.Humanoid:ChangeState(14)
						v.HumanoidRootPart.CanCollide = false
						v.Head.CanCollide = false
						getgenv().ToTarget(v.HumanoidRootPart.CFrame == PosMonMasteryFruit)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
					elseif v.Name == QuestCheck()[3] and (v.HumanoidRootPart.Position - PosMonMasteryFruit.Position).Magnitude <= 225 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						v.Humanoid:ChangeState(14)
						v.HumanoidRootPart.CanCollide = false
						v.Head.CanCollide = false
						getgenv().ToTarget(v.HumanoidRootPart.CFrame == PosMonMasteryFruit)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
					end
				end
			end
		end)
	end
end)

local Toggle = Tabs.Settings:AddToggle("DisnableDame", {Title = "Disabled Damage", Default = false })

Toggle:OnChanged(function()
	_G.DisnableDame = Options.DisnableDame.Value
	if Options.DisnableDame.Value then
		game:GetService("ReplicatedStorage").Assets.GUI.DamageCounter.Enabled = false
	else
		game:GetService("ReplicatedStorage").Assets.GUI.DamageCounter.Enabled = true
	end
	SaveSettings()
end)

Options.DisnableDame:SetValue(_G.DisnableDame)


function UseCode(Text)
	game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(Text)
end


local x2Code = {
	"3BVISITS",
	"UPD16",
	"FUDD10",
	"BIGNEWS",
	"THEGREATACE",
	"SUB2GAMERROBOT_EXP1",
	"StrawHatMaine",
	"Sub2OfficialNoobie",
	"SUB2NOOBMASTER123",
	"Sub2Daigrock",
	"Axiore",
	"TantaiGaming",
	"STRAWHATMAINE",
	"Enyu_is_Pro",
	"Sub2Fer999",
	"Bluxxy",
	"JCWK",
	"Magicbus",
	"Starcodeheo",
	"SUB2UNCLEKIZARU"
}

Tabs.Settings:AddButton({
	Title = "Redeem Code All",
	Description = "Redeem Code All",
	Callback = function()
		for i,v in pairs(x2Code) do
			UseCode(v)
		end
	end
})

local Toggle = Tabs.Settings:AddToggle("AutoRejoin", {Title = "Auto Rejoin", Default = false })

Toggle:OnChanged(function()
	_G.AutoRejoin = Options.AutoRejoin.Value
	SaveSettings()
end)

Options.AutoRejoin:SetValue(_G.AutoRejoin)

spawn(function()
	while wait() do
		if _G.AutoRejoin then
			_G.AutoRejoin = game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(child)
				if child.Name == 'ErrorPrompt' and child:FindFirstChild('MessageArea') and child.MessageArea:FindFirstChild("ErrorFrame") then
					game:GetService("TeleportService"):Teleport(game.PlaceId)
				end
			end)
		end
	end
end)

Tabs.Settings:AddSection("Use Skill")

local Toggle = Tabs.Settings:AddToggle("Skill_Z", {Title = "Skill Z", Default = false })

Toggle:OnChanged(function()
	_G.Skill_Z = Options.Skill_Z.Value
	SaveSettings()
end)

Options.Skill_Z:SetValue(_G.Skill_Z)

local Toggle = Tabs.Settings:AddToggle("Skill_X", {Title = "Skill X", Default = false })

Toggle:OnChanged(function()
	_G.Skill_X = Options.Skill_X.Value
	SaveSettings()
end)

Options.Skill_X:SetValue(_G.Skill_X)

local Toggle = Tabs.Settings:AddToggle("Skill_C", {Title = "Skill C", Default = false })

Toggle:OnChanged(function()
	_G.Skill_C = Options.Skill_C.Value
	SaveSettings()
end)

Options.Skill_C:SetValue(_G.Skill_C)

local Toggle = Tabs.Settings:AddToggle("Skill_V", {Title = "Skill V", Default = false })

Toggle:OnChanged(function()
	_G.Skill_V = Options.Skill_V.Value
	SaveSettings()
end)

Options.Skill_V:SetValue(_G.Skill_V)

--------------------------------------------------------------------------------------------------------------------

Tabs.Stats:AddSection("Rage Kill Player")


PlayerName = {}
for i,v in pairs(game.Players:GetChildren()) do  
	if v.Name ~= game.Players.LocalPlayer.Name then
		table.insert(PlayerName ,v.Name)
	end
end


spawn(function()
	while wait() do
		pcall(function()
			table.clear(PlayerName)
			for i,v in pairs(game.Players:GetChildren()) do  
				if v.Name ~= game.Players.LocalPlayer.Name then
					table.insert(PlayerName ,v.Name)
				end
			end
		end)
	end
end)

local SelectPlayers = Tabs.Stats:AddDropdown("Select_Players", {
	Title = "Select Players",
	Values = PlayerName,
	Multi = false,
	Default = 1,
})

SelectPlayers:SetValue("Select Players")

SelectPlayers:OnChanged(function(Value)
	_G.Select_Player = Value
	SaveSettings()
end)


Tabs.Stats:AddButton({
	Title = "Rest Players",
	Description = "Rest Players",
	Callback = function()
		for i,v in pairs(game.Players:GetChildren()) do  
			if v.Name ~= game.Players.LocalPlayer.Name then
				table.insert(PlayerName ,v.Name)
			end
		end
	end
})

local Toggle = Tabs.Stats:AddToggle("Spectate_Player", {Title = "Spectate Player", Default = false })

Toggle:OnChanged(function()
	_G.Spectate_Player = Options.Spectate_Player.Value
	SaveSettings()
end)

Options.Spectate_Player:SetValue(_G.Spectate_Player)

spawn(function()
	while wait() do
		if _G.Spectate_Player then
			pcall(function()
				if game.Players:FindFirstChild(_G.Select_Player) then
					game.Workspace.Camera.CameraSubject = game.Players:FindFirstChild(_G.Select_Player).Character.Humanoid
				end
			end)
		else
			game.Workspace.Camera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
		end
	end
end)

local Toggle = Tabs.Stats:AddToggle("Teleport_to_Player", {Title = "Teleport to Player", Default = false })

Toggle:OnChanged(function()
	_G.Teleport_to_Player = Options.Spectate_Player.Value
	if Options.Teleport_to_Player.Value == false then
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
	SaveSettings()
end)

Options.Teleport_to_Player:SetValue(_G.Teleport_to_Player)


spawn(function()
	while wait() do
		if _G.Teleport_to_Player then
			pcall(function()
				if game.Players:FindFirstChild(_G.Select_Player) then
					getgenv().ToTarget(game.Players[_G.Select_Player].Character.HumanoidRootPart.CFrame)
				end
			end)
		end
	end
end)


local Toggle = Tabs.Stats:AddToggle("Enabled_PvP", {Title = "Enabled PvP", Default = false })

Toggle:OnChanged(function()
	_G.Enabled_PvP = Options.Enabled_PvP.Value
	SaveSettings()
end)

Options.Enabled_PvP:SetValue(_G.Enabled_PvP)

spawn(function()
	pcall(function()
		while wait() do
			if _G.Enabled_PvP then
				if game:GetService("Players").LocalPlayer.PlayerGui.Main.PvpDisabled.Visible == true then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EnablePvp")
				end
			end
		end
	end)
end)

Tabs.Stats:AddSection("Stats")

local Toggle = Tabs.Stats:AddToggle("Auto_Stats_Melee", {Title = "Auto Stats Melee", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Stats_Melee = Options.Auto_Stats_Melee.Value
	SaveSettings()
end)

Options.Auto_Stats_Melee:SetValue(_G.Auto_Stats_Melee)

spawn(function()
	while wait() do
		pcall(function()
			if _G.Auto_Stats_Melee then
				local args = {
					[1] = "AddPoint",
					[2] = "Melee",
					[3] = _G.Point
				}

				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))

			end
		end)
	end
end)

local Toggle = Tabs.Stats:AddToggle("Auto_Stats_Defense", {Title = "Auto Stats Defense", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Stats_Defense = Options.Auto_Stats_Defense.Value
	SaveSettings()
end)

Options.Auto_Stats_Defense:SetValue(_G.Auto_Stats_Defense)

spawn(function()
	while wait() do
		pcall(function()
			if _G.Auto_Stats_Defense then
				local args = {
					[1] = "AddPoint",
					[2] = "Melee",
					[3] = _G.Point
				}

				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))

			end
		end)
	end
end)


local Toggle = Tabs.Stats:AddToggle("Auto_Stats_Sword", {Title = "Auto Stats Sword", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Stats_Sword = Options.Auto_Stats_Sword.Value
	SaveSettings()
end)

Options.Auto_Stats_Sword:SetValue(_G.Auto_Stats_Sword)


spawn(function()
	while wait() do
		if _G.Auto_Stats_Sword then
			local args = {
				[1] = "AddPoint",
				[2] = "Sword",
				[3] = _G.Point
			}

			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end
	end
end)

local Toggle = Tabs.Stats:AddToggle("Auto_Stats_Gun", {Title = "Auto Stats Gun", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Stats_Gun = Options.Auto_Stats_Gun.Value
	SaveSettings()
end)

Options.Auto_Stats_Gun:SetValue(_G.Auto_Stats_Gun)

spawn(function()
	while wait() do
		if _G.Auto_Stats_Gun then
			local args = {
				[1] = "AddPoint",
				[2] = "Gun",
				[3] = _G.Point
			}

			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end
	end
end)

local Toggle = Tabs.Stats:AddToggle("Auto_Stats_Devil_Fruit", {Title = "Auto Stats Devil Fruit", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Stats_Devil_Fruit = Options.Auto_Stats_Devil_Fruit.Value
	SaveSettings()
end)

Options.Auto_Stats_Devil_Fruit:SetValue(_G.Auto_Stats_Devil_Fruit)


spawn(function()
	while wait() do
		if _G.Auto_Stats_Devil_Fruit then
			local args = {
				[1] = "AddPoint",
				[2] = "Demon Fruit",
				[3] = _G.Point
			}

			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end
	end
end)

local Point = Tabs.Stats:AddDropdown("Select_Point", {
	Title = "Select Point",
	Values = {"10","15","20","25","30","35","40","45","50"},
	Multi = false,
	Default = 1,
})

Point:SetValue("25")

Point:OnChanged(function(Value)
	_G.Point = Value
	SaveSettings()
end)

Tabs.Dungeon:AddSection("Main Dungeon")

Dungeon = {
	"Flame", 
	"Ice", 
	"Quake", 
	"Light",
	"Dark",
	"String",
	"Rumble",
	"Magma",
	"Human: Buddha",
	"Sand",
	"Bird: Phoenix"
}

local Select_Dungeon = Tabs.Dungeon:AddDropdown("Select_Dungeon", {
	Title = "Select Dungeon",
	Values = Dungeon,
	Multi = false,
	Default = 1,
})

Select_Dungeon:SetValue("Flame")

Select_Dungeon:OnChanged(function(Value)
	_G.Select_Dungeon = Value
	SaveSettings()
end)


local Toggle = Tabs.Dungeon:AddToggle("Auto_Buy_Chip_Dungeon", {Title = "Auto Buy Chip Dungeon", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Buy_Chip_Dungeon = Options.Auto_Buy_Chip_Dungeon.Value
	SaveSettings()
end)

Options.Auto_Buy_Chip_Dungeon:SetValue(_G.Auto_Buy_Chip_Dungeon)


spawn(function()
	while wait() do
		if _G.Auto_Buy_Chips_Dungeon then
			pcall(function()
				local args = {
					[1] = "RaidsNpc",
					[2] = "Select",
					[3] = _G.Select_Dungeon
				}

				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end)
		end
	end
end)

local Toggle = Tabs.Dungeon:AddToggle("Auto_Start_Dungeon", {Title = "Auto Dungeon", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Start_Dungeon = Options.Auto_Start_Dungeon.Value
	SaveSettings()
end)

Options.Auto_Start_Dungeon:SetValue(G.Auto_Start_Dungeon)

spawn(function()
	while wait() do
		if _G.Auto_Start_Dungeon then
			pcall(function()
				if World2 then
					if not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Special Microchip") then 
							fireclickdetector(game.Workspace.Map.CircleIsland.RaidSummon2.Button.Main.ClickDetector)
						end
					end
				elseif World3 then
					if not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Special Microchip") then
							fireclickdetector(game.Workspace.Map["Boat Castle"].RaidSummon2.Button.Main.ClickDetector)
						end
					end
				end
			end)
		end
	end
end)

local Toggle = Tabs.Dungeon:AddToggle("Auto_Next_Island", {Title = "Auto Next Island", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Next_Island = Options.Auto_Next_Island.Value
	if Options.Auto_Next_Island.Value == false then
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
	SaveSettings()
end)

Options.Auto_Next_Island:SetValue(_G.Auto_Next_Island)


spawn(function()
	while wait() do
		if _G.Auto_Next_Island then
			if World2 or World3 and game.Players.localPlayer.data.level.value > 1100 then
				if not game.Players.LocalPlayer.PlayerGui.Main.Timer.Visible == false then
					if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
						if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
							getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame * CFrame.new(0,70,100))
						end
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
						if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
							getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame * CFrame.new(0,70,100))
						end
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
						if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
							getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame * CFrame.new(0,70,100))
						end
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
						if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
							getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame * CFrame.new(0,70,100))
						end
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
						if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
							getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame * CFrame.new(0,70,100))
						end
					end
				end
			end
		end
	end
end)

local Toggle = Tabs.Dungeon:AddToggle("Kill_Aura", {Title = "Kill Aura", Default = false })

Toggle:OnChanged(function()
	_G.Kill_Aura = Options.Kill_Aura.Value
	SaveSettings()
end)

Options.Kill_Aura:SetValue(_G.Kill_Aura)


spawn(function()
	while wait() do
		if _G.Kill_Aura then
			for i,v in pairs(game.Workspace.Enemies:GetDescendants()) do
				if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
					pcall(function()
						repeat wait(.1)
							v.Humanoid.Health = 0
							v.HumanoidRootPart.CanCollide = false
							sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
						until not _G.Kill_Aura  or not v.Parent or v.Humanoid.Health <= 0
					end)
				end
			end
		end
	end
end)

local Toggle = Tabs.Dungeon:AddToggle("Auto_Awake", {Title = "Auto Awake", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Awake = Options.Auto_Awake.Value
	SaveSettings()
end)

Options.Auto_Awake:SetValue(_G.Auto_Awake)

spawn(function()
	while wait(.1) do
		if _G.Auto_Awake then
			pcall(function()
				local args = {
					[1] = "Awakener",
					[2] = "Check"
				}

				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				local args = {
					[1] = "Awakener",
					[2] = "Awaken"
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end)
		end
	end
end)

------------------------------------------------------------------

Tabs.Dungeon:AddSection("Law Dungeon")

local Toggle = Tabs.Dungeon:AddToggle("Auto_Buy_Law_Chip", {Title = "Auto Buy Law Chip", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Buy_Law_Chip = Options.Auto_Buy_Law_Chip.Value
	SaveSettings()
end)

Options.Auto_Buy_Law_Chip:SetValue(_G.Auto_Buy_Law_Chip)


spawn(function()
	while wait() do
		if _G.Auto_Buy_Law_Chip then
			if World2 then
				pcall(function()
					if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Microchip") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Microchip") or game:GetService("Workspace").Enemies:FindFirstChild("Order [Lv. 1250] [Raid Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Order [Lv. 1250] [Raid Boss]") then

					else
						local args = {
							[1] = "BlackbeardReward",
							[2] = "Microchip",
							[3] = "2"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
				end)
			end
		end
	end
end)

local Toggle = Tabs.Dungeon:AddToggle("Auto_Start_Law_Dungeon", {Title = "Auto Start Law Dungeon", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Start_Law_Dungeon = Options.Auto_Start_Law_Dungeon.Value
	SaveSettings()
end)

Options.Auto_Start_Law_Dungeon:SetValue(_G.Auto_Start_Law_Dungeon)

spawn(function()
	while wait() do
		if _G.Auto_Start_Law_Dungeon then
			pcall(function()
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Microchip") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Microchip") then
					fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon.Button.Main.ClickDetector)
				end
			end)
		end
	end
end)

local Toggle = Tabs.Dungeon:AddToggle("Auto_Kill_Law", {Title = "Auto Kill Law", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Kill_Law = Options.Auto_Kill_Law.Value
	if Options.Auto_Kill_Law.Value == false then
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
	SaveSettings()
end)

Options.Auto_Kill_Law:SetValue(_G.Auto_Kill_Law)


spawn(function()
	while wait() do
		if _G.Auto_Kill_Law then
			pcall(function()
				if game:GetService("ReplicatedStorage"):FindFirstChild("Order [Lv. 1250] [Raid Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Order [Lv. 1250] [Raid Boss]") then
					for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
						if _G.Auto_Kill_Law and v.Name == "Order [Lv. 1250] [Raid Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
							repeat task.wait()
								AutoHaki()
								EquipWeapon(_G.Select_Weapon)
								v.HumanoidRootPart.CanCollide = false
								v.HumanoidRootPart.Size = Vector3.new(50,50,50)
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * MethodFarm)
							until not _G.Auto_Kill_Law or v.Humanoid.Health <= 0 or not v.Parent
						end
					end
				else
					if (CFrame(-6127.654296875, 15.951762199402, -5040.2861328125).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 2000 then
						BTP(CFrame(-6127.654296875, 15.951762199402, -5040.2861328125))
						return
					end
					getgenv().ToTarget(CFrame(-6127.654296875, 15.951762199402, -5040.2861328125))
				end
			end)
		end
	end
end)

Tabs.Dungeon:AddSection("Devil Fruit Shop")


local Remote_GetFruits = game.ReplicatedStorage:FindFirstChild("Remotes").CommF_:InvokeServer("GetFruits");

Table_DevilFruitSniper = {}
ShopDevilSell = {}

for i,v in next,Remote_GetFruits do
	table.insert(Table_DevilFruitSniper,v.Name)
	if v.OnSale then 
		table.insert(ShopDevilSell,v.Name)
	end
end

local Select_Devil_Fruit = Tabs.Dungeon:AddDropdown("Select_Devil_Fruit", {
	Title = "Select Devil Fruit",
	Values = Table_DevilFruitSniper,
	Multi = false,
	Default = 1,
})

Select_Devil_Fruit:SetValue("Select Devil Fruit")

Select_Devil_Fruit:OnChanged(function(Value)
	_G.Select_Devil_Fruit = Value
	SaveSettings()
end)

local Toggle = Tabs.Dungeon:AddToggle("Auto_Buy_Devil_Fruit", {Title = "Auto Buy Devil Fruit", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Buy_Devil_Fruit = Options.Auto_Buy_Devil_Fruit.Value
	SaveSettings()
end)

Options.Auto_Buy_Devil_Fruit:SetValue(_G.Auto_Buy_Devil_Fruit)

spawn(function()
	while wait() do
		if _G.Auto_Buy_Devil_Fruit then
			pcall(function()
				local string_1 = "PurchaseRawFruit";
				local string_2 = _G.Select_Devil_Fruit;
				local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
				Target:InvokeServer(string_1, string_2);
			end)
		end                              
	end
end)

local Toggle = Tabs.Dungeon:AddToggle("Auto_Random_Fruit", {Title = "Auto Random Fruit", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Random_Fruit = Options.Auto_Random_Fruit.Value
	SaveSettings()
end)

Options.Auto_Random_Fruit:SetValue(_G.Auto_Random_Fruit)

spawn(function()
	while wait() do
		if _G.Auto_Random_Fruit then	
			local args = {
				[1] = "Cousin",
				[2] = "Buy"
			}
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end
	end
end)


local Toggle = Tabs.Dungeon:AddToggle("Auto_Bring_Fruit", {Title = "Auto Bring Fruit", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Bring_Fruit = Options.Auto_Bring_Fruit.Value
	SaveSettings()
end)

Options.Auto_Bring_Fruit:SetValue(_G.Auto_Bring_Fruit)


spawn(function()
	while wait() do
		if _G.Auto_Bring_Fruit then
			pcall(function()
				for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
					if v:IsA("Tool") and string.find(v.Name,"Fruit") then 
						if (v.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
							BTP(v.Name,"Fruit")  
						end
					end
				end
			end)
		end
	end
end)

local Toggle = Tabs.Dungeon:AddToggle("Auto_Store_Fruit", {Title = "Auto Store Fruit", Default = false })

Toggle:OnChanged(function()
	_G.Auto_Store_Fruit = Options.Auto_Store_Fruit.Value
	SaveSettings()
end)

Options.Auto_Store_Fruit:SetValue(_G.Auto_Store_Fruit)

spawn(function()
	while wait() do
		if _G.Auto_Store_Fruit then
			pcall(function()
				wait()
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bomb Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bomb Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bomb-Bomb",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bomb Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bomb Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spike Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spike Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spike-Spike",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spike Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spike Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Chop Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Chop Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Chop-Chop",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Chop Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Chop Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spring Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spring Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spring-Spring",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spring Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spring Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Kilo Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Kilo Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Kilo-Kilo",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Kilo Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Kilo Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Smoke Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Smoke Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Smoke-Smoke",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Smoke Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Smoke Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spin Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spin Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spin-Spin",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spin Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spin Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flame Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flame Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Flame-Flame",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flame Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flame Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Falcon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Falcon Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bird-Bird: Falcon",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Falcon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Falcon Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Ice Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Ice Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Ice-Ice",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Ice Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Ice Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Sand Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Sand Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Sand-Sand",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Sand Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Sand Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dark Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dark Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dark-Dark",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dark Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dark Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Revive Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Revive Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Revive-Revive",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Revive Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Revive Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Diamond Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Diamond Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Diamond-Diamond",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Diamond Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Diamond Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Light Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Light Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Light-Light",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Light Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Light Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Love Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Love Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Love-Love",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Love Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Love Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rubber Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rubber Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Rubber-Rubber",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rubber Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rubber Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Barrier Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Barrier Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Barrier-Barrier",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Barrier Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Barrier Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Magma Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Magma Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Magma-Magma",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Magma Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Magma Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Door Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Door Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Door-Door",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Door Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Door Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Quake Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Quake Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Quake-Quake",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Quake Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Quake Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Human-Human: Buddha Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Human-Human: Buddha",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Human-Human: Buddha Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("String Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("String Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","String-String",game:GetService("Players").LocalPlayer.Character:FindFirstChild("String Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("String Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Phoenix Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Phoenix Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bird-Bird: Phoenix",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Phoenix Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Phoenix Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rumble Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rumble Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Rumble-Rumble",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rumble Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rumble Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Paw Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Paw Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Paw-Paw",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Paw Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Paw Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Gravity Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Gravity Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Gravity-Gravity",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Gravity Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Gravity Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dough Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dough Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dough-Dough",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dough Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dough Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Shadow Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Shadow Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Shadow-Shadow",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Shadow Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Shadow Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Venom Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Venom Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Venom-Venom",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Venom Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Venom Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Control Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Control Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Control-Control",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Control Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Control Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dragon-Dragon",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Fruit"))
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Leopard Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Leopard Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Leopard-Leopard",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Leopard Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Leopard Fruit"))
				end
			end)
		end
	end
end)

Tabs.Teleport:AddSection("Teleport World")

Tabs.Teleport:AddButton({
	Title = "Teleport to First World",
	Description = "Teleport to First World",
	Callback = function()
		Window:Dialog({
			Title = "New World",
			Content = "You're going to World 1, right?",
			Buttons = {
				{
					Title = "Yes",
					Callback = function()
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
					end
				},
				{
					Title = "No",
					Callback = function()
						print("")
					end
				}
			}
		})
	end
})

Tabs.Teleport:AddButton({
	Title = "Teleport to Second World",
	Description = "Teleport to Second World",
	Callback = function()
		Window:Dialog({
			Title = "New World",
			Content = "You're going to World 2, right?",
			Buttons = {
				{
					Title = "Yes",
					Callback = function()
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
					end
				},
				{
					Title = "No",
					Callback = function()
						print("")
					end
				}
			}
		})
	end
})

Tabs.Teleport:AddButton({
	Title = "Teleport to Third World",
	Description = "Teleport to Third World",
	Callback = function()
		Window:Dialog({
			Title = "New World",
			Content = "You're going to World 3, right?",
			Buttons = {
				{
					Title = "Yes",
					Callback = function()
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
					end
				},
				{
					Title = "No",
					Callback = function()
						print("")
					end
				}
			}
		})
	end
})

Tabs.Teleport:AddSection("Teleport Island")


if World1 then
	Island = {
		"nil",
		"WindMill",
		"Marine",
		"Middle Town",
		"Jungle",
		"Pirate Village",
		"Desert",
		"Snow Island",
		"MarineFord",
		"Colosseum",
		"Sky Island 1",
		"Sky Island 2",
		"Sky Island 3",
		"Prison",
		"Magma Village",
		"Under Water Island",
		"Fountain City",
		"Shank Room",
		"Mob Island"
	}
elseif World2 then  
	Island = {
		"nil",
		"The Cafe",
		"Frist Spot",
		"Dark Area",
		"Flamingo Mansion",
		"Flamingo Room",
		"Green Zone",
		"Factory",
		"Colossuim",
		"Zombie Island",
		"Two Snow Mountain",
		"Punk Hazard",
		"Cursed Ship",
		"Ice Castle",
		"Forgotten Island",
		"Ussop Island",
		"Mini Sky Island"
	}
else
	Island = {
		"nil",
		"Mansion",
		"Port Town",
		"Great Tree",
		"Castle On The Sea",
		"MiniSky", 
		"Hydra Island",
		"Floating Turtle",
		"Haunted Castle",
		"Ice Cream Island",
		"Peanut Island",
		"Cake Island"
	}	
end

local Point = Tabs.Teleport:AddDropdown("Select_Island", {
	Title = "Select Island",
	Values = Island,
	Multi = false,
	Default = 1,
})

Point:SetValue("Select Island")

Point:OnChanged(function(Value)
	_G.Select_Island = Value
	SaveSettings()
end)

local Toggle = Tabs.Teleport:AddToggle("Start_Tween_Island", {Title = "Start Tween Island", Default = false })

Toggle:OnChanged(function()
	_G.Start_Tween_Island = Options.Start_Tween_Island.Value
	if _G.Start_Tween_Island == true then
		repeat wait()
			if _G.Select_Island == "WindMill" then
				getgenv().ToTarget(CFrame.new(979.79895019531, 16.516613006592, 1429.0466308594))
			elseif _G.Select_Island == "Marine" then
				getgenv().ToTarget(CFrame.new(-2566.4296875, 6.8556680679321, 2045.2561035156))
			elseif _G.Select_Island == "Middle Town" then
				getgenv().ToTarget(CFrame.new(-690.33081054688, 15.09425163269, 1582.2380371094))
			elseif _G.Select_Island == "Jungle" then
				getgenv().ToTarget(CFrame.new(-1612.7957763672, 36.852081298828, 149.12843322754))
			elseif _G.Select_Island == "Pirate Village" then
				getgenv().ToTarget(CFrame.new(-1181.3093261719, 4.7514905929565, 3803.5456542969))
			elseif _G.Select_Island == "Desert" then
				getgenv().ToTarget(CFrame.new(944.15789794922, 20.919729232788, 4373.3002929688))
			elseif _G.Select_Island == "Snow Island" then
				getgenv().ToTarget(CFrame.new(1347.8067626953, 104.66806030273, -1319.7370605469))
			elseif _G.Select_Island == "MarineFord" then
				getgenv().ToTarget(CFrame.new(-4914.8212890625, 50.963626861572, 4281.0278320313))
			elseif _G.Select_Island == "Colosseum" then
				getgenv().ToTarget( CFrame.new(-1427.6203613281, 7.2881078720093, -2792.7722167969))
			elseif _G.Select_Island == "Sky Island 1" then
				getgenv().ToTarget(CFrame.new(-4869.1025390625, 733.46051025391, -2667.0180664063))
			elseif _G.Select_Island == "Sky Island 2" then  
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
			elseif _G.Select_Island == "Sky Island 3" then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
			elseif _G.Select_Island == "Prison" then
				getgenv().ToTarget( CFrame.new(4875.330078125, 5.6519818305969, 734.85021972656))
			elseif _G.Select_Island == "Magma Village" then
				getgenv().ToTarget(CFrame.new(-5247.7163085938, 12.883934020996, 8504.96875))
			elseif _G.Select_Island == "Under Water Island" then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
			elseif _G.Select_Island == "Fountain City" then
				getgenv().ToTarget(CFrame.new(5127.1284179688, 59.501365661621, 4105.4458007813))
			elseif _G.Select_Island == "Shank Room" then
				getgenv().ToTarget(CFrame.new(-1442.16553, 29.8788261, -28.3547478))
			elseif _G.Select_Island == "Mob Island" then
				getgenv().ToTarget(CFrame.new(-2850.20068, 7.39224768, 5354.99268))
			elseif _G.Select_Island == "The Cafe" then
				getgenv().ToTarget(CFrame.new(-380.47927856445, 77.220390319824, 255.82550048828))
			elseif _G.Select_Island == "Frist Spot" then
				getgenv().ToTarget(CFrame.new(-11.311455726624, 29.276733398438, 2771.5224609375))
			elseif _G.Select_Island == "Dark Area" then
				getgenv().ToTarget(CFrame.new(3780.0302734375, 22.652164459229, -3498.5859375))
			elseif _G.Select_Island == "Flamingo Mansion" then
				getgenv().ToTarget(CFrame.new(-483.73370361328, 332.0383605957, 595.32708740234))
			elseif _G.Select_Island == "Flamingo Room" then
				getgenv().ToTarget(CFrame.new(2284.4140625, 15.152037620544, 875.72534179688))
			elseif _G.Select_Island == "Green Zone" then
				getgenv().ToTarget( CFrame.new(-2448.5300292969, 73.016105651855, -3210.6306152344))
			elseif _G.Select_Island == "Factory" then
				getgenv().ToTarget(CFrame.new(424.12698364258, 211.16171264648, -427.54049682617))
			elseif _G.Select_Island == "Colossuim" then
				getgenv().ToTarget( CFrame.new(-1503.6224365234, 219.7956237793, 1369.3101806641))
			elseif _G.Select_Island == "Zombie Island" then
				getgenv().ToTarget(CFrame.new(-5622.033203125, 492.19604492188, -781.78552246094))
			elseif _G.Select_Island == "Two Snow Mountain" then
				getgenv().ToTarget(CFrame.new(753.14288330078, 408.23559570313, -5274.6147460938))
			elseif _G.Select_Island == "Punk Hazard" then
				getgenv().ToTarget(CFrame.new(-6127.654296875, 15.951762199402, -5040.2861328125))
			elseif _G.Select_Island == "Cursed Ship" then
				getgenv().ToTarget(CFrame.new(923.40197753906, 125.05712890625, 32885.875))
			elseif _G.Select_Island == "Ice Castle" then
				getgenv().ToTarget(CFrame.new(6148.4116210938, 294.38687133789, -6741.1166992188))
			elseif _G.Select_Island == "Forgotten Island" then
				getgenv().ToTarget(CFrame.new(-3032.7641601563, 317.89672851563, -10075.373046875))
			elseif _G.Select_Island == "Ussop Island" then
				getgenv().ToTarget(CFrame.new(4816.8618164063, 8.4599885940552, 2863.8195800781))
			elseif _G.Select_Island == "Mini Sky Island" then
				getgenv().ToTarget(CFrame.new(-288.74060058594, 49326.31640625, -35248.59375))
			elseif _G.Select_Island == "Great Tree" then
				getgenv().ToTarget(CFrame.new(2681.2736816406, 1682.8092041016, -7190.9853515625))
			elseif _G.Select_Island == "Castle On The Sea" then
				getgenv().ToTarget(CFrame.new(-5074.45556640625, 314.5155334472656, -2991.054443359375))
			elseif _G.Select_Island == "MiniSky" then
				getgenv().ToTarget(CFrame.new(-260.65557861328, 49325.8046875, -35253.5703125))
			elseif _G.Select_Island == "Port Town" then
				getgenv().ToTarget(CFrame.new(-290.7376708984375, 6.729952812194824, 5343.5537109375))
			elseif _G.Select_Island == "Hydra Island" then
				getgenv().ToTarget(CFrame.new(5228.8842773438, 604.23400878906, 345.0400390625))
			elseif _G.Select_Island == "Floating Turtle" then
				getgenv().ToTarget(CFrame.new(-13274.528320313, 531.82073974609, -7579.22265625))
			elseif _G.Select_Island == "Mansion" then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-12471.169921875, 374.94024658203, -7551.677734375))
			elseif _G.Select_Island == "Haunted Castle" then
				getgenv().ToTarget(CFrame.new(-9515.3720703125, 164.00624084473, 5786.0610351562))
			elseif _G.Select_Island == "Ice Cream Island" then
				getgenv().ToTarget(CFrame.new(-902.56817626953, 79.93204498291, -10988.84765625))
			elseif _G.Select_Island == "Peanut Island" then
				getgenv().ToTarget(CFrame.new(-2062.7475585938, 50.473892211914, -10232.568359375))
			elseif _G.Select_Island == "Cake Island" then
				getgenv().ToTarget(CFrame.new(-1884.7747802734375, 19.327526092529297, -11666.8974609375))
			end
		until not _G.Start_Tween_Island
	end
	if Options.Start_Tween_Island.Value == false then
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
end)

Options.Start_Tween_Island:SetValue(_G.Start_Tween_Island)


Tabs.Teleport:AddSection("Server")

JobiJoin = ""
local JOJ_ID = Tabs.Teleport:AddInput("JOJ_ID", {
	Title = "JOJ ID",
	Default = "",
	Placeholder = "ID Server",
	Numeric = false, -- Only allows numbers
	Finished = false, -- Only calls callback when you press enter
	Callback = function(value)
		JobiJoin = value
	end
})

Tabs.Teleport:AddButton({
	Title = "Join Server",
	Description = "Join Server",
	Callback = function()
		Window:Dialog({
			Title = "Join Server",
			Content = "Will you join the server?",
			Buttons = {
				{
					Title = "Yes",
					Callback = function()
						game:GetService("TeleportService"):TeleportToPlaceInstance(game.placeId, JobiJoin, game.Players.LocalPlayer)
					end
				},
				{
					Title = "No",
					Callback = function()
						print("")
					end
				}
			}
		})
	end
})


Tabs.Teleport:AddButton({
	Title = "Rejoin Server",
	Description = "Rejoin Server",
	Callback = function()
		Window:Dialog({
			Title = "Rejoin Server",
			Content = "Will you refresh this server?",
			Buttons = {
				{
					Title = "Yes",
					Callback = function()
						local ts = game:GetService("TeleportService")
						local p = game:GetService("Players").LocalPlayer
						ts:Teleport(game.PlaceId, p)
					end
				},
				{
					Title = "No",
					Callback = function()
						print("")
					end
				}
			}
		})
	end
})

Tabs.Teleport:AddButton({
	Title = "Server Hop",
	Description = "Server Hop",
	Callback = function()
		Window:Dialog({
			Title = "Server Hop",
			Content = "Will you hop server?",
			Buttons = {
				{
					Title = "Yes",
					Callback = function()
						Hop()
					end
				},
				{
					Title = "No",
					Callback = function()
						print("")
					end
				}
			}
		})
	end
})

Tabs.Misc:AddSection("Haki State")

local SelectStateHaki = Tabs.Misc:AddDropdown("SelectStateHaki", {
	Title = "Select Haki State",
	Values = {"State 0","State 1","State 2","State 3","State 4","State 5"},
	Multi = false,
	Default = 1,
})

SelectStateHaki:SetValue("Select Haki State")

SelectStateHaki:OnChanged(function(Value)
	_G.SelectStateHaki = Value
end)


Tabs.Misc:AddButton({
	Title = "Change Buso Haki State",
	Description = "Change Buso Haki State",
	Callback = function()
		if _G.SelectStateHaki == "State 0" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",0)
		elseif _G.SelectStateHaki == "State 1" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",1)
		elseif _G.SelectStateHaki == "State 2" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",2)
		elseif _G.SelectStateHaki == "State 3" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",3)
		elseif _G.SelectStateHaki == "State 4" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",4)
		elseif _G.SelectStateHaki == "State 5" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",5)
		end
	end
})


Number = math.random(1, 1000000)
function isnil(L_426_arg0)
	return (L_426_arg0 == nil)
end
local function L_52_func(L_427_arg0)
	return math.floor(tonumber(L_427_arg0) + 0.5)
end

spawn(function()
	while wait() do
		for L_428_forvar0, L_429_forvar1 in pairs(game:GetService'Players':GetChildren()) do
			pcall(function()
				if not isnil(L_429_forvar1.Character) then
					if _G.EspPlayer then
						if not isnil(L_429_forvar1.Character.Head) and not L_429_forvar1.Character.Head:FindFirstChild('NameEsp' .. Number) then
							local L_430_ = Instance.new('BillboardGui', L_429_forvar1.Character.Head)
							L_430_.Name = 'NameEsp' .. Number
							L_430_.ExtentsOffset = Vector3.new(0, 1, 0)
							L_430_.Size = UDim2.new(1, 200, 1, 30)
							L_430_.Adornee = L_429_forvar1.Character.Head
							L_430_.AlwaysOnTop = true
							local L_431_ = Instance.new('TextLabel', L_430_)
							L_431_.Font = Enum.Font.SourceSansSemibold
							L_431_.FontSize = "Size14"
							L_431_.TextSize = 14.000
							L_431_.TextWrapped = true
							L_431_.Text = (L_429_forvar1.Name .. ' : '..L_429_forvar1.Character.Humanoid.Health..' : ' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_429_forvar1.Character.Head.Position).Magnitude / 3) .. ' M')
							L_431_.Size = UDim2.new(1, 0, 1, 0)
							L_431_.TextYAlignment = 'Top'
							L_431_.BackgroundTransparency = 1
							L_431_.TextStrokeTransparency = 0.5
							if L_429_forvar1.Team == game:GetService("Teams").Pirates then
								L_431_.TextColor3 = Color3.new(255, 0, 0)
							else
								L_431_.TextColor3 = Color3.new(0, 255, 255)
							end
						else
							L_429_forvar1.Character.Head['NameEsp' .. Number].TextLabel.Text = (L_429_forvar1.Name .. ' | ' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_429_forvar1.Character.Head.Position).Magnitude / 3) .. ' M : Health : ' .. L_52_func(L_429_forvar1.Character.Humanoid.Health * 100 / L_429_forvar1.Character.Humanoid.MaxHealth) .. '%')
						end
					else
						if L_429_forvar1.Character.Head:FindFirstChild('NameEsp' .. Number) then
							L_429_forvar1.Character.Head:FindFirstChild('NameEsp' .. Number):Destroy()
						end
					end
				end
			end)
		end
	end
end)

spawn(function()
	while wait() do
		for L_436_forvar0, L_437_forvar1 in pairs(game.Workspace:GetChildren()) do
			pcall(function()
				if L_437_forvar1.Name == "Chest1" or L_437_forvar1.Name == "Chest2" or L_437_forvar1.Name == "Chest3" then
					if _G.EspChest then
						if (L_437_forvar1.Name == "Chest1" or L_437_forvar1.Name == "Chest2" or L_437_forvar1.Name == "Chest3") and (L_437_forvar1.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 60000 then
							if not L_437_forvar1:FindFirstChild("ChestESP" .. Number) then
								local L_438_ = Instance.new("BillboardGui", L_437_forvar1)
								L_438_.Name = "ChestESP" .. Number
								L_438_.ExtentsOffset = Vector3.new(0, 1, 0)
								L_438_.Size = UDim2.new(1, 200, 1, 30)
								L_438_.Adornee = L_437_forvar1
								L_438_.AlwaysOnTop = true
								local L_439_ = Instance.new("TextLabel", L_438_)
								L_439_.Font = Enum.Font.SourceSansSemibold
								L_439_.TextSize = 14.000
								L_439_.FontSize = "Size14"
								L_439_.Size = UDim2.new(1, 0, 1, 0)
								L_439_.BackgroundTransparency = 1
								L_439_.TextStrokeTransparency = 0.5
								if L_437_forvar1.Name == "Chest1" then
									L_439_.TextColor3 = Color3.fromRGB(174, 123, 47)
									L_439_.Text = "Bronze Chest" .. "\n" .. math.round((L_437_forvar1.Position - game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.Position).Magnitude / 3) .. " m."
								end
								if L_437_forvar1.Name == "Chest2" then
									L_439_.TextColor3 = Color3.fromRGB(255, 255, 127)
									L_439_.Text = "Gold Chest" .. "\n" .. math.round((L_437_forvar1.Position - game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.Position).Magnitude / 3) .. " m."
								end
								if L_437_forvar1.Name == "Chest3" then
									L_439_.Text = "Diamond Chest" .. "\n" .. math.round((L_437_forvar1.Position - game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.Position).Magnitude / 3) .. " m."
									L_439_.TextColor3 = Color3.fromRGB(5, 243, 255)
								end
							else
								L_437_forvar1["ChestESP" .. Number].TextLabel.Text = L_437_forvar1.Name .. "\n" .. math.round((L_437_forvar1.Position - game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.Position).Magnitude / 3) .. " m."
							end
						end
					else
						if L_437_forvar1:FindFirstChild("ChestESP" .. Number) then
							L_437_forvar1:FindFirstChild("ChestESP" .. Number):Destroy()
						end
					end
				end
			end)
		end
	end
end)

spawn(function()
	while wait() do
		for L_432_forvar0, L_433_forvar1 in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
			pcall(function()
				if _G.EspIsland then
					if L_433_forvar1.Name ~= "Sea" then
						if not L_433_forvar1:FindFirstChild('NameEsp') then
							local L_434_ = Instance.new('BillboardGui', L_433_forvar1)
							L_434_.Name = 'NameEsp'
							L_434_.ExtentsOffset = Vector3.new(0, 1, 0)
							L_434_.Size = UDim2.new(1, 200, 1, 30)
							L_434_.Adornee = L_433_forvar1
							L_434_.AlwaysOnTop = true
							local L_435_ = Instance.new('TextLabel', L_434_)
							L_435_.Font = Enum.Font.SourceSansSemibold
							L_435_.FontSize = "Size14"
							L_435_.TextSize = 14.00
							L_435_.TextWrapped = true
							L_435_.Size = UDim2.new(1, 0, 1, 0)
							L_435_.TextYAlignment = 'Top'
							L_435_.BackgroundTransparency = 1
							L_435_.TextStrokeTransparency = 0.5
							L_435_.TextColor3 = Color3.fromRGB(80, 245, 245)
						else
							L_433_forvar1['NameEsp'].TextLabel.Text = (L_433_forvar1.Name .. '   \n' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_433_forvar1.Position).Magnitude / 3) .. ' M')
						end
					end
				else
					if L_433_forvar1:FindFirstChild('NameEsp') then
						L_433_forvar1:FindFirstChild('NameEsp'):Destroy()
					end
				end
			end)
		end
	end
end)

spawn(function()
	while wait() do
		for L_440_forvar0, L_441_forvar1 in pairs(game:GetService("Workspace"):GetChildren()) do
			pcall(function()
				if _G.EspFruit then
					if string.find(L_441_forvar1.Name, "Fruit") then
						if not L_441_forvar1.Handle:FindFirstChild('NameEsp' .. Number) then
							local L_442_ = Instance.new('BillboardGui', L_441_forvar1.Handle)
							L_442_.Name = 'NameEsp' .. Number
							L_442_.ExtentsOffset = Vector3.new(0, 1, 0)
							L_442_.Size = UDim2.new(1, 200, 1, 30)
							L_442_.Adornee = L_441_forvar1.Handle
							L_442_.AlwaysOnTop = true
							local L_443_ = Instance.new('TextLabel', L_442_)
							L_443_.Font = Enum.Font.SourceSansSemibold
							L_443_.FontSize = "Size14"
							L_443_.TextSize = 14.00
							L_443_.TextWrapped = true
							L_443_.Size = UDim2.new(1, 0, 1, 0)
							L_443_.TextYAlignment = 'Top'
							L_443_.BackgroundTransparency = 1
							L_443_.TextStrokeTransparency = 0.5
							L_443_.TextColor3 = Color3.fromRGB(255, 0, 0)
							L_443_.Text = (L_441_forvar1.Name .. ' \n' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_441_forvar1.Handle.Position).Magnitude / 3) .. ' M')
						else
							L_441_forvar1.Handle['NameEsp' .. Number].TextLabel.Text = (L_441_forvar1.Name .. '   \n' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_441_forvar1.Handle.Position).Magnitude / 3) .. ' M')
						end
					end
				else
					if L_441_forvar1.Handle:FindFirstChild('NameEsp' .. Number) then
						L_441_forvar1.Handle:FindFirstChild('NameEsp' .. Number):Destroy()
					end
				end
			end)
		end
	end
end)

spawn(function()
	while wait() do
		for L_444_forvar0, L_445_forvar1 in pairs(game:GetService("Workspace"):GetChildren()) do
			pcall(function()
				if L_445_forvar1.Name == "Flower2" or L_445_forvar1.Name == "Flower1" then
					if _G.EspFower then
						if not L_445_forvar1:FindFirstChild('NameEsp' .. Number) then
							local L_446_ = Instance.new('BillboardGui', L_445_forvar1)
							L_446_.Name = 'NameEsp' .. Number
							L_446_.ExtentsOffset = Vector3.new(0, 1, 0)
							L_446_.Size = UDim2.new(1, 200, 1, 30)
							L_446_.Adornee = L_445_forvar1
							L_446_.AlwaysOnTop = true
							local L_447_ = Instance.new('TextLabel', L_446_)
							L_447_.Font = Enum.Font.SourceSansSemibold
							L_447_.FontSize = "Size14"
							L_447_.TextSize = 14.00
							L_447_.TextWrapped = true
							L_447_.Size = UDim2.new(1, 0, 1, 0)
							L_447_.TextYAlignment = 'Top'
							L_447_.BackgroundTransparency = 1
							L_447_.TextStrokeTransparency = 0.5
							L_447_.TextColor3 = Color3.fromRGB(255, 0, 0)
							if L_445_forvar1.Name == "Flower1" then
								L_447_.Text = ("Blue Flower" .. ' \n' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_445_forvar1.Position).Magnitude / 3) .. ' M')
								L_447_.TextColor3 = Color3.fromRGB(255, 0, 0)
							end
							if L_445_forvar1.Name == "Flower2" then
								L_447_.Text = ("Red Flower" .. ' \n' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_445_forvar1.Position).Magnitude / 3) .. ' M')
								L_447_.TextColor3 = Color3.fromRGB(255, 0, 0)
							end
						else
							L_445_forvar1['NameEsp' .. Number].TextLabel.Text = (L_445_forvar1.Name .. '   \n' .. L_52_func((game:GetService('Players').LocalPlayer.Character.Head.Position - L_445_forvar1.Position).Magnitude / 3) .. ' M')
						end
					else
						if L_445_forvar1:FindFirstChild('NameEsp' .. Number) then
							L_445_forvar1:FindFirstChild('NameEsp' .. Number):Destroy()
						end
					end
				end
			end)
		end
	end
end)



Tabs.Misc:AddSection("Esp")

local Toggle = Tabs.Misc:AddToggle("EspPlayer", {Title = "Esp Players", Default = false })

Toggle:OnChanged(function()
	_G.EspPlayer = Options.EspPlayer.Value
	SaveSettings()
end)

Options.EspPlayer:SetValue(_G.EspPlayer)

local Toggle = Tabs.Misc:AddToggle("EspIsland", {Title = "Esp Island", Default = false })

Toggle:OnChanged(function()
	_G.EspIsland = Options.EspIsland.Value
	SaveSettings()
end)

Options.EspIsland:SetValue(_G.EspIsland)


local Toggle = Tabs.Misc:AddToggle("EspFruit", {Title = "Esp Fruit", Default = false })

Toggle:OnChanged(function()
	_G.EspFruit = Options.EspFruit.Value
	SaveSettings()
end)

Options.EspFruit:SetValue(_G.EspFruit)



local Toggle = Tabs.Misc:AddToggle("EspFlower", {Title = "Esp Flower", Default = false })

Toggle:OnChanged(function()
	_G.EspFlower = Options.EspFlower.Value
	SaveSettings()
end)

Options.EspFlower:SetValue(_G.EspFlower)



local Toggle = Tabs.Misc:AddToggle("EspChest", {Title = "Esp Chest", Default = false })

Toggle:OnChanged(function()
	_G.EspChest = Options.EspChest.Value
	SaveSettings()
end)

Options.EspChest:SetValue(_G.EspChest)

Tabs.Misc:AddSection("Misc")

local Toggle = Tabs.Misc:AddToggle("No_clip", {Title = "No clip", Default = false })

Toggle:OnChanged(function()
	_G.No_clip = Options.No_clip.Value
	SaveSettings()
end)

Options.No_clip:SetValue(_G.No_clip)


spawn(function()
	pcall(function()
		game:GetService("RunService").Stepped:Connect(function()
			if _G.No_clip or _G.Auto_Farm_Level or _G.Auto_Farm_Mob_Aura or _G.Auto_New_World or _G.Auto_Farm_BF_Mastery or _G.Auto_Farm_Gun_Mastery or _G.Auto_Third_World or _G.AutoFarmChest or _G.Start_Tween_Island or _G.Auto_Farm_Boss or _G.Auto_Elite_Hunter or _G.Auto_Cake_Prince or _G.Auto_Farm_All_Boss or _G.AutoSaber or _G.Auto_Pole or _G.Auto_Factory_Farm or _G.Auto_Farm_Ectoplasm or _G.Auto_Bartilo_Quest or _G.Auto_Rengoku or _G.Auto_Evo_Race_V2 or _G.Auto_Swan_Glasses or _G.Auto_Dragon_Trident or _G.Auto_Farm_Bone or  _G.Auto_Rainbow_Haki or _G.Auto_Holy_Torch or _G.Auto_Canvander or _G.Auto_Twin_Hook or _G.Auto_Serpent_Bow or _G.AutoFarmMaterial or _G.Auto_Fully_Death_Step or _G.Auto_Fully_SharkMan_Karate or _G.Teleport_to_Player or _G.Auto_Kill_Player_Melee or _G.Auto_Kill_Player_Gun or _G.Auto_Next_Island or _G.AutoFarmSelectMonster or _G.Auto_Factory_Farm or _G.Auto_Tushita or _G.Auto_Yama then
				for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
					if v:IsA("BasePart") then
						v.CanCollide = false    
					end
				end
			end
		end)
	end)
end)

local Toggle = Tabs.Misc:AddToggle("Infinit_Energy", {Title = "Infinit Energy", Default = false })

Toggle:OnChanged(function()
	_G.Infinit_Energy = Options.Infinit_Energy.Value
	SaveSettings()
end)

Options.Infinit_Energy:SetValue(_G.Infinit_Energy)

if _G.Infinit_Energy then
	game:GetService("Players").LocalPlayer.Character.Energy.Changed:connect(function()
		if _G.Infinit_Energy then
			game:GetService("Players").LocalPlayer.Character.Energy.Value = game:GetService("Players").LocalPlayer.Character.Energy.MaxValue
		end 
	end)
end

local Toggle = Tabs.Misc:AddToggle("CameraMaxZoom", {Title = "Infinit CameraMaxZoom", Default = false })

Toggle:OnChanged(function()
	_G.CameraMaxZoom = Options.CameraMaxZoom.Value
	SaveSettings()
end)

Options.CameraMaxZoom:SetValue(_G.CameraMaxZoom)

game.Players.LocalPlayer.CameraMinZoomDistance = 10
if _G.CameraMaxZoom then
	game.Players.LocalPlayer.CameraMaxZoomDistance = (math.huge^math.huge^math.huge)
else
	game.Players.LocalPlayer.CameraMaxZoomDistance = 200
end


local Toggle = Tabs.Misc:AddToggle("WalkWater", {Title = "Walk on Water", Default = false })

Toggle:OnChanged(function()
	_G.WalkWater = Options.WalkWater.Value
	SaveSettings()
end)

Options.WalkWater:SetValue(_G.WalkWater)

spawn(function()
	while task.wait() do
		pcall(function()
			if _G.WalkWater then
				game:GetService("Workspace").Map["WaterBase-Plane"].Size = Vector3.new(1000,112,1000)
			else
				game:GetService("Workspace").Map["WaterBase-Plane"].Size = Vector3.new(1000,80,1000)
			end
		end)
	end
end)

Tabs.Misc:AddSection("Pirates / Marines")


Tabs.Misc:AddButton({
	Title = "Join Pirates Team",
	Description = "Join Pirates Team",
	Callback = function()
		local args = {
			[1] = "SetTeam",
			[2] = "Pirates"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args)) 
		local args = {
			[1] = "BartiloQuestProgress"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end
})

Tabs.Misc:AddButton({
	Title = "Join Marines Team",
	Description = "Join Marines Team",
	Callback = function()
		local args = {
			[1] = "SetTeam",
			[2] = "Marines"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		local args = {
			[1] = "BartiloQuestProgress"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end
})

Tabs.Misc:AddSection("Other")

Tabs.Misc:AddButton({
	Title = "Click TP Tool",
	Description = "Click TP Tool",
	Callback = function()
		ClickTpTool()
	end
})

Tabs.Misc:AddButton({
	Title = "Fps Boost",
	Description = "Fps Boost",
	Callback = function()
		Window:Dialog({
			Title = "Fps Boost",
			Content = "Do you want to increase FPS?",
			Buttons = {
				{
					Title = "Yes",
					Callback = function()
						FPSBooster()
					end
				},
				{
					Title = "No",
					Callback = function()
						print("")
					end
				}
			}
		})
	end
})

SaveManager:SetLibrary(Fluent)
InterfaceManager:SetLibrary(Fluent)
SaveManager:IgnoreThemeSettings()
SaveManager:SetIgnoreIndexes({})
InterfaceManager:SetFolder("FluentScriptHub")
SaveManager:SetFolder("FluentScriptHub/specific-game")
InterfaceManager:BuildInterfaceSection(Tabs.Settings)
SaveManager:BuildConfigSection(Tabs.Settings)
Window:SelectTab(1)
Fluent:Notify({
	Title = "Welcome To Manake Hub",
	Content = "By Hub Maruko and Sal ",
	Duration = 8
})
SaveManager:LoadAutoloadConfig()


if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Death") then
	game:GetService("ReplicatedStorage").Effect.Container.Death:Destroy()
end
if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Respawn") then
	game:GetService("ReplicatedStorage").Effect.Container.Respawn:Destroy()
end

while wait() do
	if _G.Auto_Farm_Level or _G.Auto_Farm_Mob_Aura or _G.Auto_New_World or _G.Auto_Farm_BF_Mastery or _G.Auto_Farm_Gun_Mastery or _G.Auto_Third_World or _G.AutoFarmChest or _G.Start_Tween_Island or _G.Auto_Farm_Boss or _G.Auto_Elite_Hunter or _G.Auto_Cake_Prince or _G.Auto_Farm_All_Boss or _G.AutoSaber or _G.Auto_Pole or _G.Auto_Factory_Farm or _G.Auto_Farm_Ectoplasm or _G.Auto_Bartilo_Quest or _G.Auto_Rengoku or _G.Auto_Evo_Race_V2 or _G.Auto_Swan_Glasses or _G.Auto_Dragon_Trident or _G.Auto_Farm_Bone or  _G.Auto_Rainbow_Haki or _G.Auto_Holy_Torch or _G.Auto_Canvander or _G.Auto_Twin_Hook or _G.Auto_Serpent_Bow or _G.AutoFarmMaterial or _G.Auto_Fully_Death_Step or _G.Auto_Fully_SharkMan_Karate or _G.Teleport_to_Player or _G.Auto_Kill_Player_Melee or _G.Auto_Kill_Player_Gun or _G.Auto_Next_Island or _G.AutoFarmSelectMonster or _G.Auto_Factory_Farm or _G.Auto_Tushita or _G.Auto_Yama or _G.Auto_Kill_Law or _G.Auto_Soul_Guitar or _G.Auto_Farm_Chest_Fast then
		if not game.Players.LocalPlayer.Character:FindFirstChild('MAKEHI') then
			local Test = Instance.new('Highlight')
			Test.Name = "MAKEHI"
			Test.Enabled = true
			Test.FillColor = Color3.fromRGB(140, 255, 211)
			Test.OutlineColor = Color3.fromRGB(39, 255, 154)
			Test.FillTransparency = 0.2
			Test.OutlineTransparency = 0.1
			Test.Parent = game.Players.LocalPlayer.Character
		end
	else
		if game.Players.LocalPlayer.Character:FindFirstChild('MAKEHI') then
			game.Players.LocalPlayer.Character:FindFirstChild('MAKEHI'):Destroy()
		end
	end
end
