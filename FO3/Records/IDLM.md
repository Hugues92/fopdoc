IDLM
====

Idle Marker

## Format

Count | Field | Name | Type | Info
------|-------|------|------|-----
+ | EDID | Editor ID | cstring |
+ | [OBND](Fields/OBND.md) | Object Bounds | struct |
+ | IDLF | Flags | uint8 | See below for values.
+ | IDLC | | struct | 
+ | IDLT | Idle Timer Setting | float32 |
+* | IDLA | Animation | float32 | FormID of a [IDLE](IDLE.md) record, or null.

### IDLF Flag Values

Value | Meaning
------|--------
0x01 | Run In Sequence
0x02 | ??
0x04 | Do Once

### IDLC

Count | Name | Type | Info
------|------|------|-----
 | Animation Count | uint8 |
 | Unused | uint8[3] |
 