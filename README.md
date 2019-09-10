PressAndHold hacked plist
-------------------------

PressAndHold is a neat MacOSX feature that let's you do a long press and get a little menu with accent options for a character.

You can get it up and running by using the command

```
defaults write -g ApplePressAndHoldEnabled -bool true
```

Since the accent list is in a `.plist` file, you can edit it to change or extend the characters offered.

I have done just that here. This `.plist` file provides

1. 𝔹𝕝𝕒𝕔𝕜𝕓𝕠𝕒𝕣𝕕 bold letters and digits - digits are handled by the key right underneath (in QWERTY) - so to get a 𝟛 you'll press and hold E. You also get ℼ, ℿ, ⅀, ℽ and ℾ.
2. More greek letters. You can usually get µ and π easily, and I know how to also get ∑ and Ω straightforwardly. But this gives press and hold access to 
   * 𝜔, 𝜛 (on w)
   * 𝜀, 𝜂 (on e)
   * 𝜌, 𝜚 (on r)
   * 𝜏, 𝜃, 𝜗 (on t)
   * 𝜄 (on i)
   * 𝜓 (on p)
   * 𝛼 (on a)
   * 𝜎 and ς (on s)
   * 𝛿 (on d)
   * 𝜑 and 𝜙 (on f)
   * 𝛾 (on g)
   * ϰ (on k)
   * 𝜆 (on l)
   * 𝜁 (on z)
   * 𝜉 and 𝜒 (on x)
   * 𝛽 (on b)
as well as
   * 𝛩 (on T)
   * ∏ and 𝛹 (on P)
   * ∑ (on S)
   * 𝛷 (on F)
   * 𝛤 (on G)
   * 𝛬 (on L)
   * 𝛯 (on X)
3. Arrows! Since S had a lot of letters assigned, arrows are 
   * a/A - ←⇐↚↢↞↤
   * w/W - ↑⇑↥⤉↟
   * d/D - →⇒↛↣↠↦
   * x/X - ↓⇓↧⤈↡ (not S - we don't get WASD arrows alas)
   * s/S - ↔︎⇔
4. A few miscellaneous useful symbols hiding under q/Q - ∀∃∄ℵ∝

To use this, find out where your computer has PressAndHold.app. On High Sierra, this is in `/System/Library/Input Methods/`. Inside the app (which is actually a directory), there is a directory with a lot of `.plist` files. It used to - on earlier versions - be in `PressAndHold.app/Contents/Resources` if I remember correctly. On High Sierra, the `.plist` definitions can be found in `PressAndHold.app/Contents/PlugIns/PAH_Extension.appex/Contents/Resources`.

1. **Back up** the file `Keyboard-en.plist`. It's probably possible to recover it, but don't take any risks here...
2. If on High Sierra or later, shut off SIP (system integrity protection):
   * Reboot
   * Hold Cmd+R as you boot it up. This gets you into rescue mode
   * Open a terminal
   * Run `csrutil disable` - this removes the integrity protection, making system files readable. This protection is there to protect from malicious software going in and messing with your system - but also stops _you_ from messing with your system
   * Reboot
3. Copy this `Keyboard-en.plist` into the directory holding all the `.plist` files
4. Test it immediately to make sure nothing's gone wrong
5. Reenable SIP by:
   * Reboot
   * Hold Cmd+R as you boot it up. This gets you into rescue mode
   * Open a terminal
   * Run `csrutil enable`
   * Reboot
