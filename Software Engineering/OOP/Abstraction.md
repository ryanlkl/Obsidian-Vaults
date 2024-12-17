- Like a flashlight with an on and off switch
	- You expect light to shine when on and no light when off
- Hide the implementation and only show necessary details to the user
- You only have to call the attribute or method to call it instead of understanding the background
``` python3
class Enemy:
	type_of_enemy: str
	health_points: int  = 10
	attack_damage: int = 1

	def talk(self):
		print("I am an Enemy")
```