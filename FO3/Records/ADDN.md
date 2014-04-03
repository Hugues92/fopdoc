ADDN Record
===========

Addon Node

## Format

Count | Field | Name | Type | Info
------|-------|------|------|-----
+ | EDID | Editor ID | cstring | Editor ID
+ | [OBND](Fields/OBND.md) | Object Bounds | struct |
+ | | [Model Data](Fields/Model.md) | | This is a field collection.
+ | DATA | Node Index | int32 |
+ | DNAM | Data | struct |

### DNAM

Count | Name | Type | Info
------|------|------|-----
- | Master Particle System Cap | uint16 |
- | unknown | uint8[2] |
