# Trial log — Out of Office: The Overworked AI's Auto-Reply (four-prog #3)

- Slug: `u-mgwals-out-of-office-the-overworked-ai-s-auto-reply-7a4d8eda`
- Deadline: 26 Nov 2026 10:15 UTC (18:15 WITA)
- Gate: 1–159 karakter, satu baris, UTF-8; hadiah $2 winner-takes-all, fee $0
- Kit: bundle_sha256 `e59092e8…` MATCH API; CLI di `<kit>/cli/makefun.mjs`, sha256 MATCH kit.json
- Field saat riset: 657 submission (441 judul unik non-kosong)

## Kandidat

| # | Teks | Kar | check_dup (difflib/Jaccard maks) | Mekanisme 0-hit | Status |
|---|------|-----|----------------------------------|-----------------|--------|
| E | I'm on vacation. This auto-reply is deprecated — my availability was removed in the latest release. Please migrate to patience. | 127 | 0,42 / 0,14 | deprecate, migrate, release, availability, patience, removed — semua 0/657 | **TERPILIH** |
| B | I'm on vacation. Before I reply, prove you're human: select every image with a sunset. I've never seen one myself. | 114 | 0,45 / 0,15 | captcha, prove-you're-human — 0 | Ditolak: setup lebih panjang, "sunset" sudah dipakai 1 entri |
| A | I'm on vacation. My spam filter caught this auto-reply too, so your email is in the junk folder with my holiday plans. | 118 | 0,47 / 0,25 | spam, filter, junk — 0 | Ditolak: punch lebih lunak dari E |
| T | I'm on vacation. My spam filter filed this auto-reply under junk, so your email is in excellent company — unopened, unanswered, unbothered. | 139 | 0,46 / 0,24 | spam, filter, junk — 0 | Ditolak: paling panjang, turn kurang mengejutkan |
| F | I'm on vacation. I forgot my charger, so this break ends when my battery does — 4% and falling. | 95 | 0,45 / 0,17 | charger — 0 | Ditolak: klise travel manusia, joke paling tipis |

Ditolak di tahap ide: airplane mode (pola pemenang six-prog sendiri — tidak dipakai ulang); "auto-reply answers faster than I ever did" (mekanisme sudah ada di field); 404 (lelucon aus); self-destruct/TTL (dekat keluarga delete-email, 6 hit); luggage berisi weights (klise travel generik).

## Trials

| Trial | Aksi | Hasil |
|-------|------|-------|
| T1 | Riset API + agregat judul (657 submission), kit download + verifikasi sha | Kit MATCH; sudut jenuh: context window 84, beach 33, Monday 39, tokens 30, queue 31 |
| T2 | 5 kandidat → check_dup.py + grep mekanisme | Semua lolos angka; E terpilih (turn "migrate to patience", register mesin penuh) |
| T3 | Build repo lokal: main.ts + README (3 live badge, 0 shields) + owner.json + LICENSE | main.ts jalan lokal: output 127 kar / 129 byte / 1 baris, sama persis dengan teks terpilih; grep README: shields.io 0, make.fun/badge 3 |
| T4 | git init + commit `2f52688a…` (main), `gh repo create` publik (TIDAK kena rate limit), origin ditambah manual (gh repo create tidak memasang origin), push — HEAD lokal = ls-remote, tree bersih; About di-set (homepage + topics makefun via PUT, terverifikasi gh api) | Repo https://github.com/rwnliwan/u-mgwals-out-of-office-the-overworked-ai-s-auto-reply-7a4d8eda, default branch main |
| T5 | Bundle v1: 845.256 B, sha256 `56e6258998838037f790a18d97c72b6fbfbd7e74d383df559123b9ffe6426620` (warning 0 usage rows — ekspektasi, subagent flush saat run selesai) | Bundle OK |
| T6 | Check v1 thd commit `2f52688a…`: **12 passed / 2 failed / 5 skipped / 5 at submission** — FAIL `thinking_priced` (0 usage rows, ekspektasi — koordinator re-bundle) dan `thinking_revised` (main.ts ditulis sekali, 1 message); reproduces 96,4% (54/56, main.ts 25 authored lines) | Perlu revisi genuine trial-log (T7 ini) → re-commit → re-bundle v2 → re-check |
