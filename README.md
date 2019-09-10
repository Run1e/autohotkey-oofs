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

