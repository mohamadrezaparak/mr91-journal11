# MR91 Journal — 1.1.0-beta

## What changed
- Reworked the visual system around the MR91 deep-black / electric-blue identity, with clearer hierarchy, softer surfaces and larger touch targets.
- Added an offline risk calculator (cash risk and a linear price-distance units estimate; it is deliberately not presented as a broker-specific lot converter).
- Added a daily pre-trade discipline checklist saved locally per day.
- Added a daily trading review saved in SQLite, included in full ZIP backups and full JSON exports.
- Hardened numeric validation against NaN/infinity and invalid entry, size and fee values.
- Restricted imported and displayed attachment paths to the app's private `files/trades` directory.
- Limited imported image size and decoded image dimensions more defensively.
- Hardened ZIP restore with compressed/expanded size limits, entry limits, path checks, SQLite integrity/schema checks, attachment-path validation and staged database replacement.
- Improved JSON escaping for control characters and added CSV formula-injection mitigation for text fields.
- Increased database schema version to 3 and app version to 1.1.0-beta.

## Important limitations
- The risk tool's position-size estimate assumes a linear price-value relationship. It does not know contract size, pip value, leverage, account currency conversion, spread or broker rules. Verify sizing independently before using it.
- Automated source checks do not replace a real Android build, installation/upgrade tests or testing on physical devices.
- This is still a beta build; do not treat it as a certified trading or financial product.
