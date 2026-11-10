# An Noor content packs

Offline hadith packs used by the An Noor Quran app. Small items (Islamic Foundation Bengali translation, ayah transliteration, duas, Muslim names, and Tawzeehul Quran tafsir) stay bundled inside the app and are not stored here.

## Layout

- `manifest.json` — book list, compressed file size, and SHA-256 of each pack
- `hadith/` — one gzip-compressed SQLite file per Bangla hadith book

The app downloads a pack once from this raw URL (must end with a slash):

    https://raw.githubusercontent.com/Arifmullikh/annur-content/main/

then verifies the SHA-256 in `manifest.json` and reads the book fully offline. A book is only offered for download when `ready` is true and `sha256` is set.

## Source

Hadith text comes from [muslimbangla.com](https://muslimbangla.com) via `hadith-api.muslimbangla.com`. This repository redistributes that material so the app can work offline. No licence is granted here; the original site remains the source.

## Books

Bangla editions only:

1. Sahih al-Bukhari
2. Sahih Muslim
3. Riyad us-Salihin
4. Mishkat al-Masabih
5. Jami at-Tirmidhi
6. Sunan Abu Dawud
7. Sunan an-Nasa'i
8. Sunan Ibn Majah
9. Muwatta Malik
10. Ash-Shamail al-Muhammadiyyah
11. Sharh Ma'anil Athar (at-Tahawi)
12. Musnad Abu Hanifa
13. Muwatta Muhammad
14. Al-Adab al-Mufrad
15. Fiqhus Sunan wal Athar
16. Akhlaqun Nabi
17. Musnad Ahmad (Fathur Rabbani)
18. At-Targhib wa at-Tarhib

Not included: Ma'ariful Hadith, Sahifa Hammam, Hadith Qudsi, and all Urdu books.

## Integrity

Use the `sha256` and `size` fields in `manifest.json` to verify each pack. `sha256` and `size` refer to the gzip-compressed SQLite file, not the encoding wrapper.

Packs are stored as Base64 text (`*.sqlite.gz.b64`) so they can be published through GitHub's text file API. The app downloads the `.b64` file, decodes it to gzip, checks the SHA-256, then decompresses. Each pack is kept well under GitHub's 100 MB limit; a book that would exceed that is split and listed as more than one file.

Currently published:

- `hadith/bukhari.sqlite.gz.b64.part01` … `part05` — Sahih al-Bukhari (Bangla edition, 7052 hadiths, 84 chapters). Join the parts, Base64-decode, then check sha256.
