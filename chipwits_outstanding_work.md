# ChipWits Implementation - Outstanding Work and Bug Fixes

## Key Outstanding Work

### 1. Missing Graphics Functions (`graphics_manager.c`)

**Status:** CRITICAL - Multiple undefined function calls

**Missing Functions:**

- `DrawRegisterDisplay()`
- `DrawKeyDisplay()`  
- `DrawStackIndicator()`
- `DrawObjectSprite()`
- `DrawPanelGrid()` - Referenced in workshop
- `DrawSocket()`, `DrawJunction()`, `DrawChipIcon()` - Workshop functions

**Work Required:**

- Implement all missing drawing functions
- Create register display rendering (damage, fuel, range bars)
- Implement stack visualization functions
- Add object sprite rendering with proper masking

### 2. Missing Constants and Definitions

**Status:** HIGH - Many undefined constants used throughout code

**Missing Constants:**

```c
// Graphics positioning (graphics_manager.c)
#define DAM_X, DAM_Y, FUEL_X, FUEL_Y, RNG_X, RNG_Y, KEY_X, KEY_Y
#define MOV_X, MOV_Y, OBJ_X, OBJ_Y, NUM_X, NUM_Y

// Icon resource IDs (graphics_manager.c)  
#define ICN_CHIPWIT_BASE, ICN_PIE, ICN_COFFEE, etc.

// Workshop constants (workshop_editor.c)
#define ACTION_TYPE_NONE, ACTION_COUNT
#define ARG_NONE

// Rectangle definitions for workshop palettes
Rect gCommandRect, gActionRect, gPanelSelectRect, etc.
```

**Work Required:**

- Define all missing constants in appropriate headers
- Create comprehensive resource ID definitions
- Add workshop UI layout constants

### 3. Room Manager Implementation Gap

**Status:** CRITICAL - Core game functionality missing

**Missing Functions:**

- `GetSquareObject()` - Core function called throughout
- `SetSquareObject()` - Room modification
- `HandleRoomTransition()` - Level progression
- `MoveAllBaddies()` - Enemy AI
- Complete room loading and saving logic

**Work Required:**

- Implement complete room data management
- Add enemy movement algorithms
- Create room transition system
- Implement object placement and removal

## Memory Management and Resource Bugs

### 4. Resource Leaks (`workshop_editor.c`)

**Issue:** Workshop allocates patterns and cursors but never releases them

**Work Required:**

- Implement proper resource cleanup in `CloseWorkshop()`
- Add error handling for resource allocation failures
- Ensure all allocated resources are properly disposed

## Logic and Flow Control Bugs

### 5. Stack Display Functions (`robot_state.c`)

```c
DrawNumStack(); /* Update display */
```

**Issue:** Functions called during push/pop but not implemented

**Work Required:**

- Implement `DrawNumStack()`, `DrawObjStack()`, `DrawMovStack()`
- Create stack visualization rendering
- Add proper error handling for display updates

### 6. Sound System Issues (`sound_manager.c`)

**Location:** `PlayZapSound()`

**Issue:** Plays 8 tones sequentially without delays, causing buffer issues

**Work Required:**

- Add proper timing delays between sound effects
- Implement sound queue system for multi-tone effects
- Add sound buffer management

### 7. Flow Control Parameter Handling (`robot_actions.c`)

**Location:** `ExecuteDetectionOperation()`

**Issue:** `flowCode` parameter modified but calling code doesn't handle return properly

**Work Required:**

- Fix flow control parameter passing
- Ensure proper branching behavior for detection operations
- Add validation for flow direction values

## Workshop System Completion

### 8. Workshop Helper Functions (`workshop_editor.c`)

**Status:** HIGH - Workshop partially implemented

**Missing Functions:**

- `SetupActionPalette()` - Initialize action palette rectangles
- `SetupThingPalette()` - Initialize argument palette
- `IsActionLegal()` - Validate operations for current context
- `IsThingLegal()` - Validate arguments for operations
- `DrawActionIcon()`, `DrawThingIcon()` - Icon rendering
- `MatchWireType()` - Wire connection logic
- `RequiresArgument()` - Operation analysis

**Work Required:**

- Complete all workshop UI functions
- Implement drag-and-drop chip editing
- Add wire connection validation
- Create palette management system

### 9. Workshop State Management

**Missing Components:**

- Panel switching logic
- Chip validation for different panel types
- Copy/paste buffer management
- Undo/redo functionality

## Mac Toolbox Compatibility Issues

### 10. API Usage Corrections

**Issues:**

- Incorrect parameter types for Toolbox functions
- Missing error checking for Mac API calls
- Outdated calling conventions

**Work Required:**

- Verify all Toolbox function signatures
- Add proper error handling for file system calls
- Update deprecated API usage

### 11. Event Handling Improvements

**Missing:**

- Proper cursor management during workshop operations
- Menu state synchronization
- Window activation handling

## Testing and Validation Requirements

### 12. Core Functionality Testing

**Required Test Cases:**

- ChipWit program loading/saving
- Room transitions and object interactions
- Workshop editing operations
- Sound system functionality
- Graphics rendering on different Mac systems

### 13. Error Condition Testing

**Required:**

- Memory allocation failures
- File system errors
- Invalid ChipWit programs
- Corrupted save files

## Immediate Next Steps

1. **Complete file_manager.c** - Fix cut-off implementation
2. **Define all missing constants** - Enable compilation
3. **Implement core graphics functions** - Enable visual output
4. **Complete room manager** - Enable basic gameplay
5. **Fix Handle usage** - Prevent crashes
6. **Implement workshop helpers** - Enable program editing

## Notes

- Workshop system is the most complex incomplete component
- Would benefit from incremental testing as components are completed
