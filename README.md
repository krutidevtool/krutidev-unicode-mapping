# Kruti Dev 010 ↔ Unicode (Mangal) mapping

An open reference table for converting between **Kruti Dev 010** (the legacy Remington-layout Hindi font) and **Unicode Devanagari** (Mangal, Nirmala UI, Noto Sans Devanagari).

Kruti Dev is not Unicode: it maps Devanagari shapes onto Latin keyboard characters. So text typed in Kruti Dev looks like `esjk uke` when the font is missing, and becomes `मेरा नाम` once it is converted to Unicode. This repo documents that mapping so developers, typists and DTP operators can check how each character is encoded.

**Online converter (free, runs in your browser, no upload):** https://krutidevtool.com/

- Unicode → Kruti Dev: https://krutidevtool.com/unicode-to-krutidev/
- Kruti Dev → Unicode: https://krutidevtool.com/krutidev-to-unicode/
- Kruti Dev keyboard chart: https://krutidevtool.com/krutidev-keyboard/
- Kruti Dev → Mangal (for MS Word and e-Office): https://krutidevtool.com/krutidev-to-mangal/
- Kruti Dev Word file (.docx) → Unicode, no upload: https://krutidevtool.com/krutidev-word-file-to-unicode/

[![Kruti Dev 010 keyboard chart](https://krutidevtool.com/assets/kb/krutidev-010-keyboard-chart.png)](https://krutidevtool.com/krutidev-keyboard/)

## Files

| File | What it contains |
|---|---|
| `mapping.csv` | Vowels, consonants, conjuncts, matras, nukta forms, digits and punctuation, with the Kruti Dev 010 keys for each (UTF-8 with BOM, opens correctly in Excel) |
| `samples.csv` | Common words and phrases in both encodings, useful as test cases |

## Example words

| Unicode (Mangal) | Kruti Dev 010 |
|---|---|
| मेरा नाम | `esjk uke` |
| भारत सरकार | `Hkkjr ljdkj` |
| कार्यालय आदेश | `dk;kZy; vkns'k` |
| हिंदी टाइपिंग परीक्षा | `fganh Vkbfiax ijh{kk` |
| विद्यालय | `fo\|ky;` |
| प्रधानमंत्री | `iz/kkuea=h` |
| श्रीमान | `Jheku` |
| कृपया ध्यान दें | `` d`i;k è;ku nsa `` |

## How Kruti Dev differs from Unicode (the tricky parts)

1. **Short i (ि) comes first.** In Kruti Dev the `f` key (ि) is typed *before* the consonant, while Unicode stores it *after*: `fd` = कि.
2. **Reph (र्) comes last.** Kruti Dev types `Z` *after* the consonant cluster, Unicode stores र् *before* it: `dkZ` = र्का in `dk;Z` (कार्य).
3. **Half letters are separate keys inside clusters.** Many half consonants have their own key when joined to the next letter (`D;` = क्य, `Lo` = स्व). A standalone halant is typed with `~` (`d~` = क्).
4. **Digits.** Kruti Dev shows `0-9` as Devanagari digits, so ० १ २ become plain `0 1 2` and come back as ASCII digits. Convert them separately if you need Devanagari numerals.
5. **Font versions.** This table is checked against **Kruti Dev 010**. Common versions (011, 055) are very close, but test a few characters if you use another version.

## Mapping table

### Vowels

| Unicode | Kruti Dev 010 key(s) |
|---|---|
| अ | `v` |
| आ | `vk` |
| इ | `b` |
| ई | `bZ` |
| उ | `m` |
| ऊ | `Å` |
| ऋ | `_` |
| ए | `,` |
| ऐ | `,s` |
| ओ | `vks` |
| औ | `vkS` |
| अं | `va` |
| अः | `v%` |

### Consonants

| Unicode | Kruti Dev 010 key(s) |
|---|---|
| क | `d` |
| ख | `[k` |
| ग | `x` |
| घ | `?k` |
| ङ | `³` |
| च | `p` |
| छ | `N` |
| ज | `t` |
| झ | `>k` |
| ञ | `¥` |
| ट | `V` |
| ठ | `B` |
| ड | `M` |
| ढ | `<` |
| ण | `.k` |
| त | `r` |
| थ | `Fk` |
| द | `n` |
| ध | `/k` |
| न | `u` |
| प | `i` |
| फ | `Q` |
| ब | `c` |
| भ | `Hk` |
| म | `e` |
| य | `;` |
| र | `j` |
| ल | `y` |
| व | `o` |
| श | `'k` |
| ष | `"k` |
| स | `l` |
| ह | `g` |

### Conjuncts

| Unicode | Kruti Dev 010 key(s) |
|---|---|
| क्ष | `{k` |
| त्र | `=` |
| ज्ञ | `K` |
| श्र | `J` |

### Matras (with क)

| Unicode | Kruti Dev 010 key(s) |
|---|---|
| का | `dk` |
| कि | `fd` |
| की | `dh` |
| कु | `dq` |
| कू | `dw` |
| कृ | `` d` `` |
| के | `ds` |
| कै | `dS` |
| को | `dks` |
| कौ | `dkS` |
| कं | `da` |
| कः | `d%` |
| कँ | `d¡` |

### Special forms

| Unicode | Kruti Dev 010 key(s) |
|---|---|
| क्य | `D;` |
| प्र | `iz` |
| र्क | `dZ` |
| द्ध | `)` |
| द्व | `}` |
| ह्म | `g~e` |
| ट्ट | `V~V` |

### Nukta

| Unicode | Kruti Dev 010 key(s) |
|---|---|
| क़ | `d+` |
| ख़ | `[k+` |
| ग़ | `x+` |
| ज़ | `t+` |
| ड़ | `M+` |
| ढ़ | `<+` |
| फ़ | `Q+` |

### Digits & punctuation

| Unicode | Kruti Dev 010 key(s) |
|---|---|
| ० | `0` |
| १ | `1` |
| २ | `2` |
| ३ | `3` |
| ४ | `4` |
| ५ | `5` |
| ६ | `6` |
| ७ | `7` |
| ८ | `8` |
| ९ | `9` |
| । | `A` |
| ॥ | `AA` |

## License

Data in this repository (the mapping table and samples) is released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). You can use it in your own projects; please credit **KrutiDev Tool (krutidevtool.com)**.

Found a wrong mapping? Open an issue with the character, what you expected and the font version.
