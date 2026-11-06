# MR91 Journal — QA / adversarial review matrix

| Area | Review / test | Current result |
|---|---|---|
| Input validation | Reject empty symbol, non-positive entry, NaN/infinity, non-positive size and negative fees | Implemented in source; runtime test pending |
| Attachment import | Accept common raster image MIME types only; cap each imported image at 25 MB | Implemented in source; runtime test pending |
| Attachment path security | Reject absolute, traversal, backslash and out-of-private-directory paths before preview/delete | Implemented in source; static review passed |
| Image memory safety | Bounds-first decode with sampling cap | Implemented in source; runtime test pending |
| ZIP restore | Compressed 350 MB cap, expanded 300 MB cap, 10,000-entry cap, traversal checks | Implemented in source; malicious archive tests pending |
| Database restore | SQLite quick_check, required table/column checks, rejects triggers/views/unknown tables, validates attachment paths, staged replacement | Implemented in source; upgrade/restore runtime test pending |
| JSON export | Escapes quotes, slashes, control characters and line breaks; includes daily reviews in full exports | Implemented in source; test vectors pending |
| CSV export | Prefixes formula-like text cells to reduce spreadsheet formula injection | Implemented in source; test vectors pending |
| Offline behavior | No INTERNET permission; local SQLite/files/SharedPreferences only | Static manifest review |
| Migration | v1→v2 checks for legacy created_at; v2→v3 adds daily_reviews | SQL logic reviewed; real-device migration pending |
| UI / RTL | Persian/English layout and MR91 black/blue palette | Source updated; visual QA pending |
| Build | Android Gradle build and APK artifact | Not yet verified in this environment |
| Physical device | Fresh install, upgrade, backup/restore, image attachment and rotation tests | Pending |

No claim is made that thousands of bugs were found or that the app is bug-free. Findings are recorded only when supported by source inspection or executed tests.
