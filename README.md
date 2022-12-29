#Corne 3x5_2
I'm using a 3x5_2 layout
Corne supports normaly 3x5_3 or 3x6_3 layout.

I added to `rev1.h`

```rev1.h

#define LAYOUT_split_3x5_2(                             \
  L00, L01, L02, L03, L04,           R00, R01, R02, R03, R04, \
  L10, L11, L12, L13, L14,           R10, R11, R12, R13, R14, \
  L20, L21, L22, L23, L24,           R20, R21, R22, R23, R24, \
                  L31, L32, R30, R31 \
  ) \
  { \
    { KC_NO, L00, L01, L02, L03, L04 }, \
    { KC_NO, L10, L11, L12, L13, L14 }, \
    { KC_NO, L20, L21, L22, L23, L24 }, \
    { KC_NO, KC_NO, KC_NO, KC_NO, L31, L32 }, \
    { KC_NO, R04, R03, R02, R01, R00 }, \
    { KC_NO, R14, R13, R12, R11, R10 }, \
    { KC_NO, R24, R23, R22, R21, R20 }, \
    { KC_NO, KC_NO, KC_NO, KC_NO, R31, R30 } \
  }
  ```

## linking
Go into the qmk repository and in the folder you will link a folder or file to
Then use the symlink command (*nix os only, windows ¯\_(ツ)_/¯)
`ln -s <path_to_this_repository> file/folder_name`
the symlink should of course the path to the folder of this repository

Or copy the file in the expected folder

### linking the  keymap

```
cd qmk/keybords/crkbd/keymaps/
ln -s ../../../../corne/inkone inkone
```

## build the firmware

`make crkbd:inkone:flash`
