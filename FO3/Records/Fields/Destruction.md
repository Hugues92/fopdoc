Destruction Field Collection
============================

The DEST, DSTD, DMDL, DMDT and DSTF fields hold destruction data, and always appear together.

## Format

Count | Field | Name | Type | Info
------|-------|------|------|-----
+ | DEST | Header | struct |
-* | | Destruction Stage | | A field collection, see below for details.

### DEST

Count | Name | Type | Info
------|------|------|-----
+ | Health | int32 |
+ | Count | uint8 |
+ | Flags | uint8 | See below for values.
+ | unknown | uint8[2] | ??

#### DEST Flag Values

Flag | Meaning
-----|--------
0x00000001 | VATS Targetable

### Destruction Stage

Count | Field | Name | Type | Info
------|-------|------|------|-----
+ | DSTD | Stage Data | struct |
- | DMDL | Stage Model Filename | cstring |
- | DMDT | Stage Model Texture Files Hashes | ?? | ??
- | DSTF | Stage End Marker | null |


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
