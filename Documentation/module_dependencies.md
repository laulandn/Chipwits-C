# ChipWits C Module Dependencies

```
main.c
├── game_controller.h
│   ├── game_constants.h
│   │   └── chipwits_types.h
│   ├── robot_state.h
│   │   └── chipwits_types.h
│   ├── robot_actions.h
│   │   ├── chipwits_types.h
│   │   ├── robot_state.h
│   │   ├── room_manager.h
│   │   ├── game_constants.h
│   │   └── sound_manager.h
│   ├── room_manager.h
│   │   ├── chipwits_types.h
│   │   ├── game_constants.h
│   │   └── file_manager.h
│   ├── graphics_manager.h
│   │   ├── chipwits_types.h
│   │   ├── resources.h
│   │   ├── game_constants.h
│   │   ├── room_manager.h
│   │   └── robot_state.h
│   ├── sound_manager.h
│   │   ├── chipwits_types.h
│   │   └── resources.h
│   └── file_manager.h
│       ├── chipwits_types.h
│       └── game_constants.h

test_main.c (Test Harness)
├── chipwits_types.h
├── game_constants.h
├── robot_state.h
├── robot_actions.h
├── room_manager.h
└── file_manager.h

Common Dependencies:
├── chipwits_types.h (Core types and constants)
├── resources.h (Resource IDs and definitions)
└── Mac Toolbox Headers:
    ├── Types.h
    ├── QuickDraw.h
    ├── Files.h
    ├── Sound.h
    ├── Events.h
    ├── Menus.h
    ├── TextEdit.h
    ├── Dialogs.h
    ├── ToolUtils.h
    └── Memory.h
```

## Module Relationships

### Core Foundation
- **chipwits_types.h**: Defines all fundamental data structures and constants
- **resources.h**: Maps resource IDs from original Forth to Mac resources

### Game Logic Layer  
- **game_constants.c**: Static game data (adventure names, object counts, etc.)
- **robot_state.c**: Robot state management and program execution
- **robot_actions.c**: Implementation of all robot operations
- **room_manager.c**: Room loading, object management, enemy AI

### System Interface Layer
- **file_manager.c**: All file I/O operations (ChipWit programs, rooms, stats)
- **sound_manager.c**: Sound effects using Mac Sound Manager
- **graphics_manager.c**: All drawing using QuickDraw

### Application Layer
- **game_controller.c**: Main game loop and state coordination
- **main.c**: Mac application entry point and event handling
- **test_main.c**: Unit test harness for non-UI functions