# Open Sans Vietnamese SpriteFonts

The three `.xnb` files in this directory are MonoGame SpriteFont builds derived
from `OpenSans-Regular.ttf`. They are used only to add missing Vietnamese glyphs
to Stardew Valley's active fonts at runtime; existing game glyphs remain intact.

- Upstream: https://github.com/googlefonts/opensans
- Font source SHA-256: `c53aceea2dcf5b4098099c0c4d0a061d17e178a049317b42a422b1a9f7f8eb59`
- License: SIL Open Font License 1.1 (`OpenSans-OFL.txt`)
- Content builder: MonoGame MGCB 3.8.4.1, Windows / HiDef (`XNBw`), matching
  the cross-platform XNB format shipped by Stardew Valley

Build sizes are 17 px (`AliveNpcsSmall`), 24 px (`AliveNpcsDialogue`), and
11 px (`AliveNpcsTiny`). The checked-in `.spritefont` files define the exact
character regions, including `U+1EA0–U+1EF9`, `Ă/ă`, `Đ/đ`, `Ơ/ơ`, and `Ư/ư`.

The font source, SpriteFont definitions, and generated XNB font assets remain
under the SIL OFL. This does not change the license of the rest of AliveNpcs.
