# A list of borderline sketchy things you can do in AutoHotkey

#### Call multiple functions without spaces.

```autohotkey
f1() {
    msgbox % A_ThisFunc
}
f2() {
    msgbox % A_ThisFunc
}

f1()f2()
```

#### Writing code inside continuation sections.

```autohotkey
msgb
( LTrim Join
o
x % A
_UserN
ame
)
```

#### Using multiple continuation sections for one string

```
MsgBox,
(
Hello
) World
(
!
)
```

#### Using expression continuation in plain text mode

```autohotkey
MsgBox, When writing in plain text
, you can continue your line onto the next
. Just make sure to punctuate at the start
! For some reason commas, when used in this manner
, don't cause leading whitespace
, but all other punctuation does
. Isn't that great
? This feature was designed for use with expressions
, but it works fine without them too!
```

#### Converting a pure JSON string to an ahk object.

Okay, this one is actually kind of cool. Obviously doesn't handle JSON
types like `null`.

```autohotkey
obj :=
( LTrim Join
{
    "key": "value",
    "list": [
        "item1",
        "item2"
    ]
}
)

for k, v in obj {
    msgbox % k " " v
}
```

#### Single-equals sometimes does expression assignment

In some situations, the dual purpose single-equals operator (normally plain-text
assignment or case-insensitive equality) can take on a third purpose: expression
assignment.

```autohotkey
MsgBox, % "Test: "
. (a = 1      ; Comparison
,  b = 2      ; Expression assignment
,  c = b + 1) ; Expression assignment
. "," a "," b "," c
```

#### AutoHotkey can click its own Hotkeys
Just why?
```autohotkey
#MaxHotkeysPerInterval, 9140
#MaxThreadsPerHotkey 255
#MaxThreads 255
SetBatchLines, -1
SetKeyDelay -1, -1
SendInput, a
~a::SendInput bb
~b::SendInput cc
~c::SendInput dd
~d::SendInput ee
~e::SendInput aa
```
