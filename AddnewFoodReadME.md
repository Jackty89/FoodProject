# FoodProject
NMS community mod. One makes you able to add new foods other to changes the flavour texts

<b>ADDNEWFOOD.LUA</b>

To add new food you'll need to follow this template

* AddNewFood structure
	* NewFoodID, (fe. NipNip_Tea)
	* Ingredients{{ingredient1, amount,type},{ingredient2, amount,type},{ingredient3, amount, type}},  (max 3 ingredients)
	* RecipeCookingTime, (time in seconds)
	* RecipeCookingAmount, (how many will get produced per cycle)
	* StackSize,
	* Price,
	* NewFoodTextureFileLocation, (TEXTURES/UI/FRONTEND/ICONS/COOKINGPRODUCTS/...), make sure the file structure in FilesToInclude ressembles this
	* RecipeCookingMethod[X], (RecipeCookingMethod[1] = "UI_COOK_STEW" ....)
	* NewFoodConsumeReward[X], (see variable above, works the same way)
	* Language {{languages[X], LanguageFileLoc[X], Name, custom description},...}"languagefile location" doesn't really matter as the code is adding a brand new ID unless you want to keep things organized
* end structure

THIS is how it looks in the code:

	{
		"YourNewFoodName", 
		{
			{"LAUNCHSUB","5", SubstanceOrProduct[1]}, --Ingame ingredient/product (max3)
			{"NIPNIPBUDS", "2", SubstanceOrProduct[2]} --Ingame ingredient/product (max3)

		},
		"2", --(time in seconds)
		"1", --(how many will get produced per cycle)
		"15", --StackSize
		"100", --Price
		"PATH/YOURICON.DDS", --custom icon OR reuse an existing ico make sure path is right
		RecipeCookingMethod[2], --Cooking method
		NewFoodConsumeReward[9], --Consume Reward
		{
			{Languages[1], LanguageFileLoc[4], "Tea", "Some Fancy text correspoding with the language"},
			{Languages[2], LanguageFileLoc[4], "FlavourText"}
		}		
	},
 
  
When you've made this you can add this to  AddNewFood Array  
