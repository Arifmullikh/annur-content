# An Noor content packs

Offline hadith packs used by the An Noor Quran app. Small items (Islamic Foundation Bengali translation, ayah transliteration, duas, Muslim names, and Tawzeehul Quran tafsir) stay bundled inside the app and are not stored here.

## Layout

- `manifest.json` — book list, compressed file size, SHA-256 of each pack, and any numbering gaps found in the source
- `hadith/` — Base64 parts of one gzip-compressed SQLite file per Bangla hadith book

The app downloads a pack once from this raw URL (must end with a slash):

    https://raw.githubusercontent.com/Arifmullikh/annur-content/main/

then joins any `parts`, Base64-decodes, verifies the SHA-256 (of the gzip, not the wrapper), and reads the book fully offline. A book is only offered for download when `ready` is true and `sha256` is set.

## Source

Hadith text comes from [muslimbangla.com](https://muslimbangla.com) via `hadith-api.muslimbangla.com`. This repository redistributes that material so the app can work offline. No licence is granted here; the original site remains the source.

## Integrity

Use the `sha256` and `size` fields in `manifest.json` to verify each pack. Those fields refer to the gzip-compressed SQLite file, not the Base64 wrapper. Packs are stored as Base64 text parts (`*.sqlite.gz.b64.partNN`) so they can be published through GitHub's text file API. Each gzip is kept well under GitHub's 100 MB limit.

## Books

| English | Bangla | Hadiths | Chapters | gzip | SHA-256 | Status |
| --- | --- | ---: | ---: | --- | --- | --- |
| 'Al-Jami' Al-Sahih'- Bukhari | সহীহ বুখারী | 7052 | 84 | 7.1 MB | `39ed8f71a4c7fda82a8b67938cd2a79819e57584d58a0ad00aedd71ca6718edc` | published |
| Al-Musnad Al-Sahih'- Muslim | সহীহ মুসলিম | 7292 | 58 | 5.5 MB | `023874932f891660e60a9b7959693c9deee1737e6c9dbf977f255be970e6eaa2` | published |
| Riyad-Us-Saliheen | রিয়াযুস সালিহীন | 1040 | 9 | 1.2 MB | `1edb793ab820defce4c2f301dc205ce0fdbc3e61ba7694231d1ad228870a5f05` | published |
| Mishkat al-Masabih | মিশকাতুল মাসাবীহ | 6283 | 31 | 3.7 MB | `eb9b23131639053b961ffd0509d3ae848c7fb3292e1c0b895addc1d736a7b37a` | published |
| Jami` at-Tirmidhi | জামে' তিরমিযী | 3959 | 48 | 3.6 MB | `cb2fa0878297f8c7c56cfd4e4889c06b574331e06bf28decbdb3d5b2123c5069` | published |
| Sunan Abi Dawud | সুনানে আবু দাউদ | 5202 | 36 | 4.1 MB | `39f45d0ac7e75e6a37afb0f0d48b4187787330957a3c08f4dce164e3484a18bb` | published |
| Sunan an-Nasa'i | সুনানে নাসায়ী | 5758 | 51 | 4.6 MB | `839c3d37a51e358a60429e4aa5fefa531e9e78df5717e31f2cf4b410845a54de` | published |
| Sunan Ibn Majah | সুনানে ইবনে মাজা | 4341 | 36 | 2.8 MB | `05d072dfef02919f11c79a7ef37339fbbe023d183d039b517b8b798883d1e1c2` | published |
| Al-Muwatta by Imam Malik | মুওয়াত্তা মালিক | 1889 | 61 | 1.4 MB | `5b8fd7789e993a730e2a967197291df9e16757a953eb406ca148da284d5444f2` | published |
| Ash-Shama'il Al-Muhammadiyah | শামাঈলে তিরমিযী | 401 | 2 | 184 KB | `30a7a68f02f8a5e2054217361f3c5cc75e0a0277e10776a0a3503930a55bdc2b` | published |
| Sharh Ma'ani Al-Athar -Imam Tahawi | ত্বহাবী শরীফ | 5145 | 23 | 4.2 MB | `aefd501257b5b25a0c087b3108b40e5735b44778f478e3db88004fa8ab6cc128` | published |
| Musnad al-Imam Abu Hanifa | মুসনাদে আবু হানীফা রহঃ | 523 | 28 | 513 KB | `e0823b43dc7a58d21464e6836158d3dc107378e5f55459778d299164060db6a3` | published |
| Al-Muwatta by Imam Muhammad | আল মুওয়াত্তা-ইমাম মুহাম্মাদ রহঃ | 1013 | 18 | 1.0 MB | `aadae89aff8213186946c3519b49a7d8658580d6c01fb1bcfc5fc08ba980160b` | published |
| Al-Adab Al-Mufrad | আল-আদাবুল মুফরাদ | 1330 | 1 | 841 KB | `824b1de3c4ee7ce3cf78cb82dbac099f048a6b554a1fa815df3c3bf50ea64fb8` | published |
| Fiqh-us-Sunan | ফিকহুস সুনান | 2709 | 43 | 1.5 MB | `6ac115577c7c1e11ed5474a7be8efa8773cc00308c750b3e4d08b1558596a766` | published |
| Akhlak-un-nabi  ﷺ | আখলাকুন্নবী (ﷺ) | 868 | 1 | 480 KB | `c2f05a2f9ca12f0f6c531804575dad4fefbf495852307fabd9fbb71435507657` | published |
| Al Musnad - Imam Ahmad | মুসনাদে আহমদ- ইমাম আহমদ রহঃ | 6424 | 47 | 2.9 MB | `b94f1625cb023e45047dc5afaaab16946cc87093e0d66cd7177c7c2f6a31bf7c` | published |
| At-Targhib wat-Tarhib | আত্-তারগীব ওয়াত্-তারহীব | 5793 | 26 | 2.9 MB | `e0e443115c3a5aac7b8edb2b02028be15c7fb9f5b654dd965df8c2e39541d8ab` | published |

Not included: Ma'ariful Hadith, Sahifa Hammam, Hadith Qudsi, and all Urdu books.

## Source gaps

These are properties of the source, not omissions we invented. Packed row counts follow the complete public list: the union of `/v2/hadiths?book={id}&chapter={chapter}` (deduplicated by id) when that is fuller than the book-level `/v2/hadiths?book=` pagination, otherwise the book-level list. Book metadata totals that the public API and website do not actually expose are recorded here and were not padded.

### Al-Musnad Al-Sahih'- Muslim
- Unused numbers in the source range: [4744]
- packed 7292 matches API count
- 11 rows share number 0 (source unnumbered/intro rows)
- number 4744 unused in 0..7281 (source gap)
- number 4745 appears twice (source, distinct row ids)

### Riyad-Us-Saliheen
- Unused numbers in the source range: [955]
- Packed 1040 matches both the book-level /v2/hadiths list and the union of all 9 chapter lists (zero extra rows).
- API book metadata claims 1906 hadiths and 17 sections. /book/16/chapters, a scan of all 2429 rows on /chapters, and muslimbangla.com/hadith-book/16/chapters all expose only these 9 chapters.
- Chapter 9 (id 579) advertises total_hadith 280 because its number range is 991-1270, not because 280 rows exist: /v2/hadiths?book=16&chapter=579 returns 51, already packed. Type/section/title/status filters did not yield further ids.
- The public source does not expose the remaining metadata figure; nothing was invented.
- Unused number 955 in 1..1041 (source gap).

### Mishkat al-Masabih
- Unused numbers in the source range: [4317, 4318, 4319, 4457, 4872, 4875, 4999, 5092, 5230, 5376, 5609, 5623]
- packed 6283 matches list API count
- API book metadata claims 6295 hadiths (equal to the 0..6294 range size)
- 12 unused numbers in 0..6294: 4317-4319, 4457, 4872, 4875, 4999, 5092, 5230, 5376, 5609, 5623
- one row uses number 0 (source)

### Jami` at-Tirmidhi
- 3 numbers appear more than once (815, 816, 945); unique numbers 3956 in 1..3956; packed 3959 matches list count (source numbering, not invented)
- Book metadata claims 3956 hadiths (equal to unique numbers 1..3956); packed 3959 matching the complete list payload because 815, 816 and 945 appear twice.

### Sunan Abi Dawud
- Unused numbers in the source range: [2175, 2382, 3695, 3812, 3813, 3814, 4183]
- 7 unused number(s) in 1..5184: 2175, 2382, 3695, 3812, 3813, 3814, 4183 (source gap, not invented)
- 19 numbers appear more than once (2174, 2383, 3261, 3268, 3271 x4, 3276 x3, 3278 x3, 3280 x4, 3392, 3694, 4010, 4012, 4058, 4087, 4182, 4240, 4396, 4636, 4999); unique 5177; packed 5202 matches list count (source numbering, not invented)
- Book metadata claims 5184 hadiths (the number range 1..5184); packed 5202 matching the complete list payload.

### Sunan Ibn Majah
- Unused numbers in the source range: [1502]
- 1 unused number(s) in 1..4341: 1502 (source gap, not invented)
- 1 numbers appear more than once (1503); unique 4340; packed 4341 matches list count (source numbering, not invented)

### Ash-Shama'il Al-Muhammadiyah
- Unused numbers in the source range: [82, 96, 109, 140, 166, 220, 244, 251, 255, 272, 274, 278, 294, 384, 411]
- 15 unused number(s) in 1..415: 82, 96, 109, 140, 166, 220, 244, 251, 255, 272, 274, 278, 294, 384, 411 (source gap, not invented)
- 1 numbers appear more than once (165); unique 400; packed 401 matches list count (source numbering, not invented)

### Sharh Ma'ani Al-Athar -Imam Tahawi
- Unused numbers in the source range: [49, 94, 99, 100, 104, 105, 118, 120, 126, 130, 138, 145, 146, 147, 151, 164, 165, 166, 168, 174, '… (2367 total)']
- Packed 5145 matches the book-level list, the union of all 23 chapter lists, and a title-level union of chapter 400 (211 = 211). No missing rows.
- API book metadata claims 7510 hadiths, which is the source number range 1..7510, not a second list. Unused numbers in that range are numbering gaps, not omitted rows.
- Website /titles pages are a table of contents over the same 5145 hadiths.
- 2367 unused number(s) in 1..7508 (source gap, not invented).
- 4 numbers appear more than once (203, 1961, 2636, 2725); unique 5141; packed 5145 matches the complete list (source numbering, not invented).

### Musnad al-Imam Abu Hanifa
- Unused numbers in the source range: [114]
- 1 unused number(s) in 1..523: 114 (source gap, not invented)
- 1 numbers appear more than once (115); unique 522; packed 523 matches list count (source numbering, not invented)

### Al-Muwatta by Imam Muhammad
- 3 numbers appear more than once (656, 700, 799); unique 1010; packed 1013 matches list count (source numbering, not invented)
- Book metadata claims 1007 hadiths; packed 1013 matching the complete list payload.

### Al-Adab Al-Mufrad
- Unused numbers in the source range: [439, 1141]
- 2 unused number(s) in 1..1330: 439, 1141 (source gap, not invented)
- 2 numbers appear more than once (114, 459); unique 1328; packed 1330 matches list count (source numbering, not invented)

### Fiqh-us-Sunan
- Book metadata claims 2710 hadiths; packed 2709 matching the complete list payload (numbers 1..2709 contiguous, no unused or duplicate numbers).

### Akhlak-un-nabi  ﷺ
- Unused numbers in the source range: [48, 64, 65, 66, 67, 68, 69, 71, 72, 93, 171, 172, 303, 517, 518, 519, 520, 521, 522, 523, '… (27 total)']
- 27 unused number(s) in 1..895: 48, 64, 65, 66, 67, 68, 69, 71, 72, 93, 171, 172, 303, 517, 518, 519, 520, 521, 522, 523, 524, 525, 557, 613, 793, 795, 796 (source gap, not invented)

### Al Musnad - Imam Ahmad
- Rebuilt from per-chapter /v2/hadiths?book=17&chapter={id} lists, deduplicated by id. The book-level /v2/hadiths?book=17 pagination only produced 5643 unique ids (it repeated some rows and never returned others). Chapter lists produced 6422 unique ids; 2 further ids from the book-level cache have no chapter_id and were kept. Packed 6424, all with Arabic and Bangla. Nothing invented.
- API book metadata still claims 27647 hadiths and 66 sections. The chapters endpoint, a scan of all 2429 global /chapters rows, and muslimbangla.com/hadith-book/17/chapters all expose only these 47 chapters. 27647 is the size of the original Musnad; this edition is Al-Fathur Rabbani and the public source does not expose more than 47 chapters / 6424 rows.
- Numbers 1..1732 are reused across chapters in this Fathur Rabbani edition; unique numbers 1732; packed 6424 rows (source numbering, not invented).

### At-Targhib wat-Tarhib
- Unused numbers in the source range: [1309, 1677, 2109, 3910, 3982, 4687]
- 6 unused number(s) in 1..5798: 1309, 1677, 2109, 3910, 3982, 4687 (source gap, not invented)
- 1 number appears more than once (1310); unique 5792; packed 5793 matches list count (source numbering, not invented)
- 1 row (number 4386, source id 1621807) has empty Arabic in the source; left empty, not invented. Bangla is present.
- Book metadata claims 5766 hadiths; packed 5793 matching the complete list payload.

