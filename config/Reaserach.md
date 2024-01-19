//                                                                        Thumb Cluster
//                                                       -----------------           ------------------
//                                                               | 4 | 5 |           | 5  |  4 |
//                                               -------------------------           ---------------------------
//                                               |       |       | 0  |              | 0  |        |        |
//                                               | 1     | 2     |--------           -----|  2     |  1     |
//                                               |       |       | 3   |              | 3 |        |        |
//                                               -------------------------           ---------------------------

# Major things to consider
- with homerow mods or without
- move away from qwerty?
    - dvorak, colemak-dh, rtshd(this one is really cool)
- both side ctrl + cmd is absolutely must 
    - even though I use mac, so cmd is a frequently used key
    - my usage of tmux and vim, requires a lot of ctrl presses
- what to map left esc
    - &mt lctrl esc: 
    - &mt lc(a) esc: useful for tmux prefix but what about normal ctrl
- layer tap/toggle keys ideas
    - f
    - space: space is my vim leader key, making it layer tap would mess up my workflow
- symbol layer: I have two options
    - ergodox style: num pad on one side, symbol on another.
    - shifted option: shift top row symbol down, home row with paren, equal, operators near index
- num layer: I have two option
    - numpad: stacked one side
    - numrow: seems better but would then need layer switcher on both side or toggle
        - numword seems better choice, but space cancel would be problematic. in case I want to write spaces around operators.
- thumb cluster
    - left:  1(bspce | hold to activate layer), 2(), 3(), 4(tmux prefix), 5()
    - right: 1(space | hold to activate layer), 2(enter), 3(), 4(tmux prefix), 5()
 

# MUST
- must move (), {}, [], minus/underscore, plus/equal to somewhere nice. these are very frequently used symbols in programming
- hyp and hyper keys
# Want
- macros/shortcuts for frequently used things
    - alt/cmd + tab: tap-dance behaviour
    - copy/cut/paste

# Nice but not must
- 

# behaviour that was interesting/to checkout
- shift-lock
- capsword
- numword

# questions and things to figure out
- what to do with the additional 4 keys
- what do I use cmd for?
    - copy, paste, cut, cmd+tab, cmd+space, cmd+click, cmd+grave
    - maclock, quit, close tab, new tab


# Ideas from the internet
- bspc to cmd and del to cmd: tried it, okay, not very nice, definitely want bspc on the left most
- left and right shift with mt for paren ()
- cmd + shift + [] to navigate chrome tabs - one layers hjkl to simulate vimium
- caps word: right thumb: 
    - single tap : sticky shift
    - hold: normal shift
    - double tap: caps word zmk

# Home Row mods Order
- ctrl, opt, cmd, shift, lt | lt, shift, cmd, opt, ctrl

# Layer switching keys
- left esc
- left and right shift if I go for the HMR
- left and up arrow key
- rarely used layers like fn layers can be switched from factory grave/caps-lock or on right [] keys

# Strategies
- thumb cluster ideas
    - 1(mt bspc cmd), 4(mt esc hyper) | 4(mt tmux prfix, layer 2), 2(mt enter, opt), 1(mt spce, cmd)
    - I am almost convinced on right 4 to be tmux prefix
    - a sticky shift on left thumb cluster(where delete is) makes a lot of sense. most frequently used mod under thumb
- magic layer: fn + nav + macos
    - (tog/lt) hjkl for nav
    - (tog/lt) cut, copy, paste, sticky tab, cmd+space, cmd+grave, 
        - would be greate if space management can also be in this layer
        - in this case must be a toggle layer
    - (lt) I am happy with fn layer to be the top row as is
    - (lt but left switch) I would add vol control + brightness control to the right two column
        - right most from top to bottom: vol up, vol down, vol null
        - 2nd right most from top to bottom: brightness up, brightness down
            - do I really need this??
- symbols
    - NO change with : ; - not even considering in the remapping
    - I am happy with <> , . / ? " '
    - absolutely must remap: - _ [] {} ~ ` = +  
    - for vim having the num row(specifically numwords) is a great and must thing
    - all(23)
        | & + * - _ < > \ / #
        " ' = ` ~
        ! @ $ % ^ &
        ? .
    - gen: = ? | .
    - paren: () {} []
    - vim: $ ^ % _ ~ < >
    - prog: & ! " '
    - math: + - * /

- Final
    - Let's do it in a few iteration
        - I can use use current nav keys as layer switcher
    - first iteration
        - somewhat normal base layer
            - remap hard to reach and frequently used stuff: =+-_
                - extra 4 keys
                - in a symbol layer in place of paren
            - right ctrl on thumb = tmux prefix
            - ctrl on both side, esc and " with mod-tap behaviour
            - end and pgdn as shift or control or cmd?
            - sticky shift in place of delete?
    - Second iteration
        - experimental layer
            - homerow mods: initially temporary layer, later base layer
                - home block mode
                - cmd as hmr but not in the home row
                - ctrl and shift as hmr on left and right most keys
        - common layers: layers that I am currently not using, so there will be learning curve anyway, so I can go crazy
            - magic layer: fn + vol control + nav + wndw mgmt + macos shortcut(cut, copy, paste)
            - hyper and hype: need to decide on possible key placements
    - numwords: Need to wait for Urob's PR to get merged
        - number on home row
        - extra: . , spce, * / + -
        - escape: j k enter cancel G(go to line number in vim)
        - consider: even odd separation, 0 and 1 in middle finger, I don't have muscle memory that strong for number anyway. So learning new layout is not a huge problem
        - magic layer: fn + macos + nav + HRM on left
