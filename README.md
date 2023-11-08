## How to type accents using a Korean keyboard.

1. Have a QWERTY keyboard and Windows.
2. In Language & Region, set-up Korean as the input language.
3. Download `korean-international-layout.reg` and double click on it.
4. Restart the computer.

Your keyboard now uses the **US International layout** when in Roman characters mode.

- For `áéíóú`: Type a single quote (`'`) followed by a vowel.

- For `ñ`: Type the tilde (`~`) followed by the letter n.

- For `ü`: Type a double quote (`shift` + `'`) followed by the letter u.

As a downside, typing single or double quotes, will now require pressing the space bar after the quote, or any non-vowel character, such as a closing quote.

<span style="font-size:small">\* Guess what this file does: `korean-international-layout-UNDO.reg`.</span>

## The US International Layout

![image](https://upload.wikimedia.org/wikipedia/commons/2/22/KB_US-International.svg)

With this layout, normally, you could hold down the `Alt Gr` key to access special characters, but since that's the same key used to toggle Korean/Roman mode (한/영), in this case you will be limited to the method described above.

## Keyboard Layouts

Think QWERY vs AZERTY vs DVORAK. They determine where each key is located. Thus, despite its name, the Korean keyboard layout includes **ZERO** hangul characters. It's in fact almost identical (completely identical?) to the US keyboard layout. All it does is send roman characters to the IME.

## IMEs

- An IME (Input Method Editor) is a program for typing complex characters, like those in East Asian languages, on a standard keyboard.

- IMEs have windows, such as the Hanja Candidate (Selection) Window

- An IME composition is an instance of text produced in an IME. (See javascript's compositionstart/update/end events)

## Microsoft's Korean Input Method Editor

This IME essentially intercepts the keys sent by the Korean keyboard layout, converts them to the corresponding hangul, i.e. q => ㅂ, Q => ㅃ, etc., and composes the appropriate syllable block, i.e. ㄱ + ㅏ => 가.

## The Windows Registry

```
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Keyboard Layouts\
```

The path above lists all the keyboard layouts availablein the machine, including the name of the file that implements it.

By opening the Korean layout (key name: 00000412) and changing its file name from `KBDKOR.DLL` to `KBDUSX.DLL`, we can make it use the US International layout instead, which shouldn't affect the behavior the Korean IME as they are both QWERTY anyway.

## Alternatives

- MSKLC can be used to create a custom keyboard layout (but not an IME).
  - [Download](https://www.microsoft.com/en-us/download/details.aspx?id=102134)
  - [Basic guide](http://www.fieldlinguiststoolbox.org/Creating_a_Keyboard_Using_MSKLC.pdf?i=1)
  - [Advanced guide](https://msklc-guide.github.io/)
- Autohotkey can be used to remap keys.
