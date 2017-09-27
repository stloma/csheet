# Vim cheatsheet

> This is my personal cheatsheet of commands I use most often.

## Selection examples

```
dl -> x
diw / diW
daw / daW
dd
dis
das / dap
dit
Dib → ()
DiB → {}
dw, cw
de, ce
db
cj, c2j
C+,d+,y+ → next line
2c) → 2nd sen, c} → prev parag
ct,dt,yt /x → c,d,y up to x
cf,df,yf /x → c,d,y up to and including x
c13G
>ap → indent a paragraph
```

## Insert Mode

```
<c-w> delete word back
<c-u> delete to start of line
<c-o> normal for one move
<c-r>0 → paste
<c-r> =6*35<cr> → do math
```

## Movement

```
zz/zh/zl/zt/zb → scroll center/left/
right/top/bottom
42G → go to line #
^f^b →  forward/back one screen
^d^u → down/up 1/2 screen
^e^y scroll u/d
H/M/L → top/middle/low screen
nH,nL → move to n lines from top/bottom
^ first non-whitespace of line
() → beg. of sentence
{} → beg. of paragraph
fx/Fx → find x/find x backwards,
 tx/Tx → find letter before/after x
 '’ or `` → last position
`. → goto last edit
% -> goto marking ([{
*/# → highlight word, find next/prev
4$ → EOL 4th line down
:norm 5j; @: → repeat movement
15| → goto column 15
[[/[{ → jump to function/block start
```

## Marks & Buffers

```
:marks → show all marks
mx → marks position x
'x → goto 1st char of line
`x → goto char by x
:delmarks a / a-d → del a / a-d
```

## Working with files

```
:e call in newfile
:f find file
:ls, then :b to select buffer
:bnext[n] next buffer
:bNext[n] prev buffer
```

## Buffers

```
"a7yy → yank +7 into buffer a
"ayy/"add → yank/delete into buffer
"Ay append to buffer A
"ap → paste from buffer
```

## Visual Mode

```
v,V,<c-v>,gv
O → goto other end of selection
vit
<c-v>3jI#<esc> → # 3 lines down
:<,'>t0 - copy v select to BOF
gv → reselect last block
:’<,’>normal A;
```

## Set options

```
:set all → show all options
:set → show all set options
:set option? → current value
foldcolumn=5
```

## Folding

```
V{motion}zf / zf3j → create fold
za/zR/zM → toggle/collapse/open
```

## Ex Commands

```
RANGE   COMMAND NUM | ADDRESS
1,3 delete, d   1 → 1st line
20,.    yank, y $ → last line
5,$ put, p  0 → above 1st line
%   copy, t . → cursor loc.
:$  move, m 'm → mark m
.,  join, j '< → beg. vis
.,’x    norm    '> → end vis
    substitute  % → whole file
:3,18d → delete lines 3-18
:20,.m$ → move from line 20 to
    current line to EOF
:%t$ → copy all lines to EOF
:226,$m.-2 → move lines 226-EOF to two lines above current line
:-,+t$ copy 3 lines to EOF
/pattern/,/pattern2/d → delete line(s)
:.,/pattern/m23 → move from current line to pattern to line 23
d/while → delete up to while
:.,/while/d → delete from current line to while
:.,+5s/old/new/gc → sub w/ confirm
:%s/ *//g → delete all whitespace
:-,+s/^/#/g → comment 3 lines
:%s/$/;/g → add ; to end of lines
%normali// #comment out whole file
```

## Misc

```
U → undoes all edits on current line
25a*<ESC>
50:*[ESC]
2r& → replaces 2 chars w &&
vim scp://host:/home/1.txt
:ab → abbreviation
:map → current mappings
:map! → insert mode
:map e ea → normal mode
noremap gV `[v`] -> stay in visual mode after indenting
g~(swap case),gu(lower),gU(upper
10<C-a>,180<c-x> auto increment will also goto number on line
C-a, C-x → increment/decrement
:%normal i# → comment all
from shell → ctags -R .
c-] → jump to definition
c-o → jump back
q/ → show search history
q: → show command history

