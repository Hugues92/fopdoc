ACTI Record
===========

Activator

## Format

Count | Field | Name | Type | Info
------|-------|------|------|-----
+ | EDID | Editor ID | cstring | Editor ID
+ | [OBND](Fields/OBND.md) | Object Bounds | struct |
- | FULL | Name | cstring | Activator name
- | MODL | Model Filename | cstring | Model data
- | MODB | Unknown | uint8[4] | Model data
- | MODT | Texture File Hashes | ?? | Model data
- | [MODS](Fields/MODS.md) | Alternate Textures | struct | Model data
- | [MODD](Fields/MODD.md) | FaceGen Model Flags | uint8 | Model data
- | SCRI | Script | formid | FormID of a SCPT record.
- | | Destruction Data | | This is a complex arrangement of fields, see below for details
- | SNAM | Sound - Looping | formid | FormID of a SOUN record.
- | VNAM | Sound - Activation | formid | FormID of a SOUN record.
- | RNAM | Radio Station | formid | FormID of a TACT record.
- | WNAM | Water Type | formid | FormID of a WATR record.

### Destruction Data


Count | Field | Name | Type | Info
------|-------|------|------|-----
+ | DEST | Header | struct |
-* | DSTD | Stage Data | struct | Required for each stage.
-* | DMDL | Stage Model Filename | cstring |
-* | DMDT | Stage Model Texture Files Hashes | ?? | ??
-* | DSTF | Stage End Marker | null | Required for each stage.

The stage fields form a repeated block, rather than the individual fields being repeated.

#### DEST

Count | Name | Type | Info
------|------|------|-----
+ | Health | int32 |
+ | Count | uint8 |
+ | Flags | uint8 | See below for values.
+ | unknown | uint8[2] | ??

##### DEST Flag Values

Flag | Meaning
-----|--------
0x00000001 | VATS Targetable

#### DSTD

Count | Name | Type | Info
------|------|------|-----
+ | Health Percentage | int32 |
+ | Index | uint8 |
+ | Damage Stage | uint8 |
+ | Flags | uint8 | See below for values.
+ | Self Damage per Second | int32 |
+ | Explosion | formid | FormID of a EXPL record or null.
+ | Debris | formid | FormID of a DEBR record or null.
+ | Debris Count | int32 |

##### DSTD Flag Values

Flag | Meaning
-----|--------
0x00000001 | Cap Damage
0x00000002 | Disable
0x00000004 | Destroy
