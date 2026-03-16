# SpaceTrader for Android

A modernized Android port of the classic SpaceTrader game.

## Attribution

Based on **SpaceTrader** by [Brucelet](https://bitbucket.org/brucelet/space-trader/src/master/).

This is a fork of the original SpaceTrader Android application, updated for compatibility with modern Android development.

## Current Status

⚠️ **AndroidX Migration In Progress**

This project is currently being migrated from the legacy Android Support Library to AndroidX. The codebase requires substantial refactoring to build on modern Android Studio and CI environments.

### Known Issues

- `ListPopupWindow.java` uses deprecated Support Library classes (`ListViewCompat`, `AppCompatPopupWindow`)
- `MainActivity.java` contains switch/case statements with `R.id` constants, incompatible with AndroidX's non-final resource IDs
- `ActivityCompat` import statements point to wrong packages

### Migration Plan

To make this project buildable on modern Android, the following changes are required:

1. **Class Replacements**
   - `ListViewCompat` → `android.widget.ListView`
   - `AppCompatPopupWindow` → `android.widget.PopupWindow`
   - Correct `ActivityCompat` imports to `androidx.core.app.ActivityCompat`

2. **Control Flow Updates**
   - Convert switch/case statements with `R.id` constants to if-else chains (18+ cases in MainActivity.java)

3. **Build Configuration**
   - Verify `compileSdkVersion` and `targetSdkVersion` compatibility
   - Ensure AndroidX dependencies are correctly declared

### Branches

- `main` — Current development branch with AndroidX migration in progress

## Building

### Requirements

- Android Studio Arctic Fox or newer
- Android SDK 21+
- Java 11+

### Quick Start

The recommended approach for completing this migration:

1. Clone the repository
2. Open in Android Studio
3. Run **Refactor → Migrate to AndroidX** (this handles most class replacements automatically)
4. Manually convert remaining switch/case statements to if-else
5. Build and test

## License

Original SpaceTrader code by Brucelet. This fork maintains the same license terms as the original project.

---

*Last updated: March 2026 — AndroidX migration documentation in progress*
