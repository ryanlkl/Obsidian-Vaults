# 1. Use Case: Setting Fitness Goals

**Primary Actor**: User
**Goal**: To allow the user to set specific fitness goals, such as lifting a certain weight or running a specific distance, to provide clear objectives for their workouts

## Main Success Scenario

1. The user logs into the application
2. The user navigates to the "Goals" section within the app
3. The system displays a list of categories for fitness goals (e.g. Strength, Cardio, Flexibility)
4. The user selects a category for the goal they want to set (e.g. Strength)
5. The system prompts the user to specify the details of the goal (e.g. "Lift 100kg in Bench Press" or "Run 5km in under 30 minutes)
	1. If the user is unsure about what goal to set, the system offers suggestions based on the user's past workout data and fitness level
6. The user enters the goal details, including the target value (e.g. Weight or Distance), and optionally, a target date to achieve the goal
7. The user submits the goal
8. The system validates the input, ensuring that the goal is realistic and relevant to the selected category,
	1. If the input data is invalid (e.g. setting an unrealistic goal such as "Lift 500kg"), the system prompts the user to adjust the goal to a more achievable target
9. The system saves the goal and displays a confirmation message to the user
	1. If the user wishes to edit the goal after setting it, they can return to the "Goals" section, select the goal, and modify the details
10. The user can view the newly set goal in their profile under the "Goals" section
	1. If the user wants to set multiple goals, they can repeat the process, and the system allows for tracking several goals simultaneously
	2. The user can delete a goal if they decide it's no longer relevant or if they want to change their focus

## Preconditions

- The user must be logged into the app
- The user must have an active profile with some workout history to set relevant goals (though this may be optional for users setting goals for the first time)

## Postconditions
- The user's goal is stored in the system, associated with their profile
- The goal is displayed in the "Goals" section of the app, where the user can track progress towards it