# Changelog

## v2.0

### Added
- **Session liquidity.** Asia, London, NY AM and NY PM highs and lows extend
  right after each session closes and are marked swept when price trades
  through them. Swept levels can be kept dimmed or removed.
- **New key levels.** Daily Open, NY Midnight Open, Previous Day High/Low,
  Previous Week High/Low. Optional price in labels.
- **Fair value gaps.** 3-candle FVG is now the default gap type. The original
  2-candle price gap is still available, alone or together with FVG.
- **Gap options.** Minimum size in ATR, shrink on partial fill, midpoint (CE)
  line.
- **NWOG / NDOG.** New Week and New Day Opening Gaps with midpoint, keeping the
  most recent N of each.
- **Dashboard.** Active session and kill zone, 5-day ADR, today's range as % of
  ADR, nearest level above and below with distance.
- **Alerts.** Session sweep and kill zone open, alongside level cross and new
  gap from v1.1.

### Changed
- Sessions are tracked as objects. Box drawing, liquidity and the dashboard all
  read the same state.
- Levels are hidden on timeframes where they carry no information.
- Level colours sit on the same row as their toggle in the settings.

## v1.1

### Fixed
- **Session timezone.** It defaulted to `Europe/Istanbul` while the default
  session times were New York times, so every box was drawn about seven hours
  early and drifted another hour during US daylight saving. The default is now
  `America/New_York`.
- **Overlapping labels.** Merging only caught identical prices. Levels within
  an ATR(14)-based tolerance now merge into one line.
- **Unbounded gap array.** Filled-but-collected gaps stayed in the array and
  were looped over every bar. Active gaps are now capped.

### Added
- Alerts: price crossing a key level, new gap formed.

## v1.0
- Initial public release: sessions and kill zones, YO/MO/PMO/WO/PWO with
  merging, 2-candle price gaps.
