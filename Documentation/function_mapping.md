# ChipWits C Functions to Forth Code Mapping

## chipwits_types.h
**Purpose**: Core data structures and constants
- **Source**: ChipWits.forth.txt, screens 2-11
- **No functions** - Pure type definitions

## game_constants.c
| C Function | Forth Source | Line Reference |
|------------|--------------|----------------|
| `InitGameConstants()` | Not directly mapped | General initialization |
| `GetAdventureName()` | `adventure$(` access | Screen 10, lines 2-9 |
| `GetCycleLimit()` | `cycle(` array | Screen 10, lines 13-14 |
| `GetTripCount()` | `trip.count(` array | Screen 10, line 15 |
| `GetObjectCount()` | `Scenario.play(` access | Screen 11, lines 1-11 |
| `GetObjectPoints()` | `Scenario.play(` access | Screen 11, lines 1-11 |

## robot_state.c
| C Function | Forth Source | Line Reference |
|------------|--------------|----------------|
| `InitRobotState()` | Variable initialization | Screen 2, lines 3-11 |
| `ResetRobot()` | `init.game` | Screen 69, lines 1-15 |
| `GetCurrentInstruction()` | `@chip` | Screen 15, lines 10-12 |
| `ExecuteInstruction()` | `Execute.robot.instruction` | Screen 68, lines 1-15 |
| `AdvanceToNextInstruction()` | `calc.next.instruction` | Screen 66, lines 2-12 |
| `CanMoveToSquare()` | Movement collision logic | Screen 48, lines 1-8 |
| `MoveRobotToSquare()` | `Move` | Screen 48, lines 1-15 |
| `TurnRobot()` | Turn logic in `Move.robot` | Screen 49, lines 6-8 |
| `CalculateNextSquare()` | `next.square` | Screen 42, lines 2-15 |
| `UpdateDamage()` | `Update.damage` | Screen 152, lines 7-11 |
| `UpdateFuel()` | `Update.fuel` | Screen 152, lines 1-6 |
| `UpdateRange()` | `Update.range` | Screen 153, lines 1-3 |
| `IsRobotDead()` | Death condition check | Screen 74, lines 3-4 |
| `PushToMovStack()` | `On.mov.st` | Screen 154, lines 8-11 |
| `PopFromMovStack()` | Stack access logic | Screen 154, lines 1-7 |
| `ClearAllStacks()` | `Clear.stacks` | Screen 157, lines 12-15 |

## robot_actions.c
| C Function | Forth Source | Line Reference |
|------------|--------------|----------------|
| `ExecuteGotoOperation()` | `Goto` | Screen 65, lines 2-8 |
| `ExecuteActionOperation()` | `Act.on.world` | Screen 58, lines 13-15 |
| `ExecuteDetectionOperation()` | `Detect.&.branch` | Screen 61, lines 12-15 |
| `ExecuteSpecialOperation()` | `Special` | Screen 63, lines 8-12 |
| `ExecuteStackOperation()` | `Stacker` | Screen 159, lines 2-15 |
| `ExecuteMove()` | `Move.robot` | Screen 49, lines 1-15 |
| `PerformMovement()` | Movement logic | Screen 48-49, various |
| `HandleCollision()` | `Bump` | Screen 47, lines 1-15 |
| `ExecutePickup()` | `Pick.up` | Screen 58, lines 1-12 |
| `ExecuteQRay()` | `zap` | Screen 54, lines 1-15 |
| `ExecuteSing()` | `Sing` | Screen 57, lines 1-13 |
| `ExecuteFeelFor()` | `feel.for` | Screen 59, lines 1-15 |
| `ExecuteLookFor()` | `look.for` | Screen 60, lines 1-15 |
| `ExecuteSmellFor()` | `Smell.for` | Screen 61, lines 1-11 |
| `ExecuteSubpanel()` | `Subpanel` | Screen 64, lines 4-8 |
| `ExecuteBoomerang()` | `Boomerang` | Screen 64, lines 10-13 |
| `ExecuteFlipCoin()` | `Flip.coin` | Screen 63, lines 2-6 |
| `ExecuteKeypress()` | `Keypress` | Screen 62, lines 1-8 |
| `CompareNumberEqual()` | `Num=` | Screen 157, lines 1-2 |
| `CompareNumberLess()` | `Num<` | Screen 157, lines 3-4 |
| `CompareObjectEqual()` | `Obj=` | Screen 157, lines 5 |
| `CompareMoveEqual()` | `Mov=` | Screen 157, lines 6 |

## room_manager.c
| C Function | Forth Source | Line Reference |
|------------|--------------|----------------|
| `LoadRoomData()` | `Load.room` | Screen 22, lines 4-10 |
| `InitializeRoom()` | Room initialization | Screen 22, lines 1-3 |
| `FurnishRoom()` | `Furnish.room` | Screen 20, lines 6-15 |
| `PlaceObjects()` | `put.objects` | Screen 20, lines 1-5 |
| `CountBaddies()` | `Count.baddies` | Screen 19, lines 5-15 |
| `GetSquareObject()` | `square.object` | Screen 18, lines 3-4 |
| `SetSquareObject()` | Room data modification | Screen 6, data access |
| `DestroyObject()` | `Destroy` | Screen 50, lines 7-12 |
| `HandleRoomTransition()` | `Goto.next.room` | Screen 45, lines 1-15 |
| `GetNextRoomNumber()` | Room transition logic | Screen 45, lines 6-11 |
| `GetEntrySquare()` | Room entry logic | Screen 45, lines 12-15 |
| `CheckForNextRoom()` | `Check.for.next.room` | Screen 46, lines 1-15 |
| `ChuckGoods()` | `chuck.goods` | Screen 21, lines 6-8 |
| `CheckGoodsVisited()` | `goods.check` | Screen 21, lines 9-15 |
| `ClearRoomsVisited()` | `clear.rooms(` | Screen 21, lines 2-3 |
| `MoveCreeps()` | Creep AI logic | Screen 139, lines 1-15 |
| `MoveBouncer()` | `Spin.bouncer` | Screen 140, lines 1-15 |
| `MoveAllBaddies()` | `Move.baddies` | Screen 141, lines 1-15 |
| `SquareToPixel()` | `square.xy` | Screen 17, lines 2-4 |

## graphics_manager.c
| C Function | Forth Source | Line Reference |
|------------|--------------|----------------|
| `InitGraphics()` | Graphics initialization | Screen 73, lines 8-15 |
| `SetupGameScreen()` | `Setup.game.screen` | Screen 27, lines 1-15 |
| `DrawGameBackground()` | `Draw.background` | Screen 34, lines 1-15 |
| `DrawRobot()` | `draw.robot` | Screen 37, lines 8-10 |
| `EraseRobot()` | `erase.robot` | Screen 37, lines 11-13 |
| `AnimateRobotMove()` | `CW.slide` | Screen 41, lines 6-8 |
| `DrawSquareObject()` | `draw.thing` | Screen 31, lines 1-10 |
| `DrawGameBoard()` | `Draw.gameboard` | Screen 38, lines 1-15 |
| `DrawFloorTile()` | `draw.floor` | Screen 28, lines 1-3 |
| `DrawWall()` | `Draw.wall` | Screen 29, lines 1-6 |
| `DrawDoor()` | `draw.door` | Screen 28, lines 5-7 |
| `AnimateCreepMovement()` | `Draw.random.creep` | Screen 138, lines 1-15 |
| `AnimateBouncerSpin()` | Bouncer animation | Screen 140, lines 1-15 |
| `FlashRobot()` | `Flash.cw` | Screen 40, lines 10-15 |
| `UpdateDamageDisplay()` | Display update logic | Screen 152, lines 7-11 |
| `UpdateFuelDisplay()` | Display update logic | Screen 152, lines 1-6 |
| `DrawMovementStack()` | `Draw.mov.st` | Screen 154, lines 1-7 |
| `DrawNumberStack()` | `Draw.num.st` | Screen 156, lines 1-7 |
| `DrawObjectStack()` | `Draw.obj.st` | Screen 155, lines 1-7 |
| `SquareToPoint()` | `square.xy` | Screen 17, lines 2-4 |

## sound_manager.c
| C Function | Forth Source | Line Reference |
|------------|--------------|----------------|
| `InitSoundManager()` | Sound system setup | Screen 23, initialization |
| `PlayMoveSound()` | `Move.sound` | Screen 24, lines 3-4 |
| `PlayPickupSound()` | `arm.sound` | Screen 55, line 15 |
| `PlayZapSound()` | `Zap.sound` | Screen 24, lines 8-9 |
| `PlayExplosionSound()` | `boom.sound` | Screen 24, lines 11-12 |
| `PlayCreepSound()` | `creep.sound` | Screen 24, lines 5-7 |
| `PlayBumpSound()` | `bump.sound` | Screen 24, line 10 |
| `PlayBeepSound()` | `boop` | Screen 24, line 10 |
| `PlaySeeSound()` | `See.sound` | Screen 24, lines 1-2 |
| `PlayEatSound()` | `crunch` | Screen 24, line 13 |
| `PlayNoteSound()` | `Sing` note playing | Screen 57, lines 6-10 |
| `PlayTone()` | `tone` primitive | Screen 23, sound generation |

## file_manager.c
| C Function | Forth Source | Line Reference |
|------------|--------------|----------------|
| `InitializeFileSystem()` | `Files.name` | Screen 9, lines 5-11 |
| `LoadChipWitProgram()` | `CW.load` | Screen 13, lines 7-10 |
| `SaveChipWitProgram()` | `CW.save` | Screen 13, lines 11-15 |
| `LoadChipWitStatistics()` | `Load.stats` | Screen 172, lines 4-7 |
| `SaveChipWitStatistics()` | `Save.stats` | Screen 172, lines 9-12 |
| `ReadAdventureData()` | Room file reading | Screen 22, lines 4-6 |

## game_controller.c
| C Function | Forth Source | Line Reference |
|------------|--------------|----------------|
| `InitializeGame()` | `Init.ChipWits` | Screen 73, lines 1-15 |
| `RunGameLoop()` | `Game` master loop | Screen 72, lines 1-15 |
| `ProcessOneGameCycle()` | Game cycle logic | Screen 72, lines 4-12 |
| `StartNewGame()` | `Start.game` | Screen 70, lines 8-15 |
| `EndCurrentGame()` | `Stop.game` | Screen 70, lines 1-7 |
| `LoadAdventure()` | Adventure loading | Screen 22, room loading |
| `LoadChipWit()` | ChipWit loading | Screen 13, CW.load |
| `AddToScore()` | `Add.points` | Screen 43, lines 1-3 |
| `ExecuteRobotCycle()` | `Execute.robot.instruction` | Screen 68, lines 1-15 |
| `HandleRobotDeath()` | `Too.bad` | Screen 74, lines 1-4 |
| `UpdateGameDisplay()` | Display coordination | Various screens |
| `UpdateScore()` | Score display | Screen 43, lines 1-3 |
| `UpdateCycleCount()` | `count.cycle` | Screen 43, lines 5-10 |
| `CheckWinCondition()` | Win condition logic | Screen 74, endgame |
| `CheckLoseCondition()` | Lose condition logic | Screen 74, too.bad |
| `HandleGameWin()` | `Endgame` | Screen 74, lines 5-8 |
| `HandleGameLoss()` | Game over handling | Screen 74, lines 1-4 |

## main.c
| C Function | Forth Source | Line Reference |
|------------|--------------|----------------|
| `main()` | `ChipWits` master program | Screen 75, lines 1-15 |
| `InitializeMac()` | Mac toolbox setup | Standard Mac initialization |
| `InitializeMenus()` | Menu setup | Screen 144, menu creation |
| `MainEventLoop()` | Event loop | Screen 75, main loop |