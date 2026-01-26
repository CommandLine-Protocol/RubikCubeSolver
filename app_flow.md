# Rubik's Cube Solver App flow Document
# 1. Overview
The rubik's cube solver helps users solve a standard 3x3 rubik's cube by inputting thier cube current state and recieving a step by step solution.
The app is designed for beginners and intermediate users who want clear guidance without needing prior solving knowledge.

# 2. The user goals
- Quickly input the current state of rubik's cube
- Validate the cube configuration
- Receive a correct, easy-to follow solution
- Navigate the steps at their own pace

# 3. User flow 
### 3.1 Launch App
- User opens the app to its home screen
- The user sees app title, brief description, and primary action
 - The primary action: "Start solving"
### 3.2 Cube input
User selects one of the follwing input methods:
- Manual Color input(tap faces)
- Camera scan 
- The system validates the cube's state and will only display an error if the configuration is invalid
### 3.3 Confirmation
- The users reviews the cube state
- There is an option to edit or confirm
- The actions: "Edit Cube" and "Solve Cube"
### 3.4 Calculation(solution generation)
- The app procees the cube's state
- Loading indicator displayed
### 3.5 Solution display
- Step-by-step instructions shown
- Visual cube representaion updates per page 
- Controls: 'next step','previous step' and 'reset'
### 3.6 Completion
- Final solved cube will be dispayed
- Users can:
 - Restart
 - Input a new cube

### 4. Errors & Edge cases
- Incomplete input
- Invalid cube configuration
- The app wil provide a clear error message and guidance 