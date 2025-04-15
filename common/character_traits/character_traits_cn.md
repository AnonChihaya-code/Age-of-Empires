	notorious = {
		type = condition														# 可以是Personality(个性)、Skill(技能)或Condition(条件)之一。每个类别都受到defines限制。可以根据特定类型应用随机特性。
		texture = "gfx/interface/icons/character_trait_icons/direct.dds"		# 特性的纹理资源
	
		character_modifier = {													# 适用于角色，无论其职位如何
			character_popularity_add = 25
		}

		command_modifier = {													# 适用于角色指挥下的任何战斗单位，假设单位已完全动员(或不需要动员)
			unit_kill_rate_mult = 0.1
		}
	
		country_modifier = {													# 如果角色是该国的统治者，则适用于该国
			state_turmoil_mult = 0.1
		}
	
		interest_group_modifier = {												# 如果角色是利益集团的领导者，则适用于该利益集团
			interest_group_pol_str_mult = -0.05
			interest_group_pop_attraction_mult = 0.1
		}
																			
		possible = {															# 用于确定此特性是否是有效的随机选择
			popularity < 0														# 一旦获得特性后，不会影响特性的有效性
		}
	
		weight = {																# 脚本值，用于确定角色随机获得此特性的可能性，与其类别中的其他特性相比。默认为1
			value = popularity
			multiply = -1
		}
	
		replace = {																# 当角色获得此特性时，将移除以下列表中的任何特性
			famous
			wicked
		}
	
		value = 2																# 此特性在经验等级特性中的"价值"。默认为1
																				# 用于确定角色是否应获得更多特性，以及哪些特性类别被过度代表
	}
