# Copy-paste reference for links and code

## USDA links for project data

https://www.ars.usda.gov/ARSUserFiles/80400530/apps/2019-2020%20FNDDS%20At%20A%20Glance%20-%20FNDDS%20Nutrient%20Values.xlsx

https://www.ars.usda.gov/ARSUserFiles/80400530/apps/2019-2020%20FNDDS%20At%20A%20Glance%20-%20Ingredient%20Nutrient%20Values.xlsx

https://www.ars.usda.gov/ARSUserFiles/80400530/apps/2019-2020%20FNDDS%20At%20A%20Glance%20-%20FNDDS%20Ingredients.xlsx

## M formula for list of dates (Ex. 4)

= List.Dates(#date(2022,11,25),160,#duration(1,0,0,0))

## DAX formulas (Ex. 5)

**First new measure**

Unique Foods Eaten = DISTINCTCOUNT('Food Journal Data'[Foods])

**Second new measure**

Total Foods Tried = 
CALCULATE(
    DISTINCTCOUNT('Food Journal Data'[Foods]),
FILTER(
        ALL('Food Journal Data'),
        'Food Journal Data'[Date] <= MAX ('Food Journal Data'[Date])
    )
  )


**New calculated column**

Meal Number = SWITCH(
    'Food Journal Data'[Meal], 
    "Breakfast", 1, 
    "Lunch", 2, 
    "Dinner", 3, 
    "Snack", 4)
