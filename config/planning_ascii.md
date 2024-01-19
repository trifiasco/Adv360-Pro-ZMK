# Planning for layout in ASCII format
See the [Research.md](Research.md) for more info.

# Rationale:
- no major changes to the default layout
    - major changes go to the experimental layout
- comfort over speed
    - optimize around the homerow and the thumb cluster
    - instead of pressing one hard to reach key, press two easy to reach keys
- optimize for low learning curve on each iteration. Big changes go to the experimental layout or broken down into smaller steps.
- no compromise with vim bindings
- symmetrical layout: if a modifier key is on the left, it should be on the right too.


Crazy stuff that I am yet to decide on:
- home row mods vs callum-style mods
    - HMR: https://precondition.github.io/home-row-mods
    - callum style mods: https://github.com/callum-oakley/qmk_firmware/tree/master/users/callum
- time to ditch qwerty? :p
- really liked rtshd
 
# Current Layers:
0. default layer:                                 (no color) normal typing
1. symbols layer:          (toggled layer):       (white) symbols around the home row
2. number layer:           (momentary layer):     (blue) number row on the home row
    - TODO: eventually I would like to convert this to a smart layer that would auto deactivate if I press enter/space/alpha keys.
          - This behaviour is like capsword behaviour but for number.
          - See this PR for details: https://github.com/zmkfirmware/zmk/pull/1451
3. kp layer:               (toggled layer):       (green) Came with the keyboard. No change. keypad style on the right hand side like a traditional numpad
4. mods layer:             (momentary layer):     (red) Came with the keyboard. No change. kinesis mods
5. magic layer:            (momentary layer):     (pink) fn + nav keys + Macos shortcuts + volume keys

==============================================================================================================================================================
Layer: DEFAULT_NORMAL
Layer: DEFAULT_NORMAL
Changes:
TMUX: Tmux prefix(ctrl+a), on both sides thumb cluster.
NUM: layer toggle to number layer on left thumb.
LGUI and LGUI: (Macos CMD) on both sides thumb cluster.
Mod-tap ESC and quote on both sides: Tap for ESC and quote, hold for CTRL.
  - experimenting with default mod-tap and hold-tap behaviour.
ltsym: Momentary layer switch to symbols layer. Again symmetrical.
up/down/left/right: arrow keys are moved to the magic layer in place of the hjkl keys to mimick vim style navigation.

    -----------------------------------------------------------------------           ---------------------------------------------------------------------
    |   =/+     |    1    |    2    |    3    |    4    |    5    | &tog KP|           |&mo MOD |    6    |    7    |    8    |    9    |    0     |  -/_       |
    |   TAB     |    Q    |    W    |    E    |    R    |    T    |  None  |           | None   |    Y    |    U    |    I    |    O    |    P     |  \/|       |
    |&mt LC(ESC)|    A    |    S    |    D    |    F    |    G    |  None  |           | None   |    H    |    J    |    K    |    L    |    ;     |  &hm RC '/"|
    |  LSHIFT   |    Z    |    X    |    C    |    V    |    B    |---------           -------  |    N    |    M    |    ,    |    .    |    /     |  RSHIFT    |
    |   fn      |    ~    | &trans  |  &trans |  ltsym  |----------                           ----------|  ltsym  | &trans  |   [/{   |   ]/}      |  fn        |
    ----------------------------------------------------                                                ----------------------------------------------------

                                                                       Thumb Cluster
                                                      -----------------              ------------------
                                                      | TMUX | LALT |                | ESC | TMUX |
                                              -------------------------              ---------------------------
                                              |       |       | HOME  |              | PG UP |        |         |
                                              | BSPC  |  NUM  |--------              --------|  ENTER |  SPACE  |
                                              |       |       | LGUI  |              | RGUI  |        |         |
                                              -------------------------              ---------------------------

==============================================================================================================================================================
Layer: DEFAULT_SYMBOLS
Layer: DEFAULT_SYMBOLS
Changes:
 - Top row symbols are moved down one row. The order doesn't change, so no learning curve. Just a little easier to reach.
 - Frequently used symbols are moved to the home row. Symmetrical braces and brackets. 

    -----------------------------------------------------------------------           ---------------------------------------------------------------------
    |          |    1   |    2   |    3    |    4    |    5    |  None  |           | None |    6    |    7    |    8    |    9    |    0     |          |
    |          |    !   |    @   |    #    |    $    |    %    |  None  |           | None |    ^    |    &    |    *    |    \    |          |          |
    |          |    =   |    [   |    {    |    (    |    +    |  None  |           | None |    -    |    )    |    }    |    ]    |    _     |          |
    |          |        |        |         |         |         |---------           -------|         |    |    |         |         |          |          |
    |          |        |        |         |         |----------                           ----------|         |         |         |          |          |
    ----------------------------------------------------                                                ----------------------------------------------------

                                                                       Thumb Cluster
                                                      -----------------              ------------------
                                                      | TMUX | LALT |                | ESC | TMUX |
                                              -------------------------              ---------------------------
                                              |       |       | HOME  |              | PG UP |        |         |
                                              | BSPC  |  NUM  |--------              --------| ENTER  |  SPACE  |
                                              |       |       | LGUI  |              | RGUI  |        |         |
                                              -------------------------              ---------------------------

==============================================================================================================================================================
Layer: NUMBER
Layer: NUMBER
NUM
Numbers on the home row.
With additional 3 keys: J, K, Shift+G
 - To accomodate the vim vertical navigation without switching from number and default layer. I constantly do like "5j" or "5k" to move 5 lines up or down. Also "34G" to go to the line number 34

    -----------------------------------------------------------------------           ---------------------------------------------------------------------
    |          |    1   |    2   |    3    |    4    |    5    |  None  |           | None |    6    |    7    |    8    |    9    |    0     |          |
    |          |        |        |    K    |         |         |  None  |           | None |         |         |         |         |          |          |
    |          |    1   |    2   |    3    |    4    |    5    |  None  |           | None |    6    |    7    |    8    |    9    |    0     |          |
    |          |        |        |  SFT G  |         |         |---------           -------|         |    J    |         |         |          |          |
    |          |        |        |         |  ltsym  |----------                           ----------|  ltsym  |         |         |          |          |
    ----------------------------------------------------                                                ----------------------------------------------------

                                                                       Thumb Cluster
                                                      -----------------              ------------------
                                                      | TMUX | LALT |                | ESC | TMUX |
                                              -------------------------              ---------------------------
                                              |       |       | HOME  |              | PG UP |        |         |
                                              | BSPC  |  NUM  |--------              --------|ENTER   | SPACE   |
                                              |       |       | LGUI  |              | RGUI  |        |         |
                                              -------------------------              ---------------------------

=============================================================================================================================================================
Magic Layer: fn + nav keys + Macos shortcuts + volume keys
Magic Layer: fn + nav keys + Macos shortcuts + volume keys
Changes:
- arrow keys are moved to the magic layer in place of the hjkl keys to mimick vim style navigation.
- vol up/down: to top right column
TODO:
- Copy: In place of Y key(like vim yank)
- Paste: In place of P key(like vim paste)
- Cut: In place of X key(like vim cut)
- Window and space management

    -----------------------------------------------------------------------           ---------------------------------------------------------------------
    |    F1    |   F2   |   F3   |   F4    |   F5    |   F6    |  None  |           | None |   F7    |   F8    |   F9    |   F10   |   F11    |  F12     |
    |   TAB    |        |        |         |         |         |  None  |           | None | selcopy |         |         |         |   paste  |  VOL_UP  |
    |  LCTRL   |        |        |         |         |         |  None  |           | None |  left   | down    |   up    | right   |          |  VOL_DOWN|
    |  LSHIFT  |        | selcut |         |         |         |---------           -------|         |         |         |         |          |  RSHIFT  |
    |          |        |        |         |         |----------                           ----------|         |         |         |          |          |
    ----------------------------------------------------                                                ----------------------------------------------------

                                                                       Thumb Cluster
                                                      -----------------              ------------------
                                                      | TMUX | LALT |                | ESC | TMUX |
                                              -------------------------              ---------------------------
                                              |       |       | HOME  |              | PG UP |        |         |
                                              | BSPC  |  NUM  |--------              --------| ENTER  |  SPACE  |
                                              |       |       | LGUI  |              | RGUI  |        |         |
                                              -------------------------              ---------------------------

