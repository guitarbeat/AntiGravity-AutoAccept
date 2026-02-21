# Changelog

## [1.18.3] — 2026-02-21

### Webview Guard Architecture (OOPIF migration fix)
- **Webview Guard**: DOM-marker check (`.react-app-container`) prevents execution on main VS Code window
- **startsWith matching**: "Run Alt+d" matches `run`, but "Always run ^" dropdown doesn't
- **Priority reorder**: `run` and `accept` checked before `always allow`
- **Removed dangerous commands**: `chatEditing.acceptAllFiles`, `inlineChat.acceptChanges` etc. removed (caused sidebar interference)
- **Removed problematic texts**: `expand` (infinite click loop), `always run` (clicked dropdown toggle)

### CDP Auto-Fix
- **Detection**: Extension checks CDP port 9222 on activation
- **Auto-Fix Shortcut**: PowerShell patcher finds Antigravity shortcuts and adds `--remote-debugging-port=9222`
- **Manual Guide**: Links to GitHub README setup instructions

### Safety
- Script exits immediately on non-agent-panel targets
- Only Antigravity-specific VS Code commands in polling loop
- Clean logging — only actual button clicks are logged

---

## [2.1.0] — 2025-02-20

### Complete Rewrite (V2)
- **Replaced** 1,435-line CDP DOM scraper with hybrid architecture
- **Primary:** VS Code Commands API with async lock
- **Secondary:** Targeted CDP with Shadow DOM piercing for permission dialogs

### Removed
- All CDP DOM scraping code (1,435 lines)
- Settings panel UI (34KB)
- 18 main_scripts helper files
