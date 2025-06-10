## ekilo - enchanted kilo
This fork includes several important improvements to enhance user experience and code quality, particularly addressing window resizing and terminal behavior.

## Changes

### 1. Add terminal clear on exit
- Modified `editorAtExit()` function to clear the terminal screen when exiting with CTRL+Q
- Added VT100 escape sequences `\x1b[2J` (clear screen) and `\x1b[H` (cursor home)
- Prevents leftover editor characters from remaining visible in the terminal
- Maintains clean exit flow through existing `atexit()` handler

### 2. Fix compiler warning for singleline_comment_start array size
- **Problem**: Modern GCC versions produce a warning about string truncation:
  ```
  kilo.c:193:9: warning: initializer-string for array of 'char' truncates NUL terminator 
  but destination lacks 'nonstring' attribute (3 chars into 2 available)
  ```
- **Root Cause**: `singleline_comment_start[2]` was too small for `"//"` + null terminator
- **Solution**: Increased array size to `char singleline_comment_start[3]`

### 3. Implement improved window resize handling
- **Retry Logic**: Instead of immediately exiting when `getWindowSize()` fails, the function now tries up to 3 times with a small delay between attempts. This handles temporary terminal state inconsistencies during resize.
- **Graceful Error Handling**: If all retry attempts fail, the editor now continues running with the current window dimensions and displays a warning message instead of exiting.
- **Better Bounds Checking**: The `handleSigWinCh()` function now has improved bounds checking to ensure the cursor and scroll offsets remain valid after a resize.
- **Added `usleep()` for Retry Delay**: A small 10ms delay between retry attempts helps handle race conditions during window resizing.

## Benefits
- Cleaner user experience when exiting the editor
- Terminal returns to pristine state without residual interface elements
- Eliminates compiler warnings with modern GCC versions
- Enhanced stability and user experience during window resizing
- Prevents editor crashes or erratic behavior when resizing the terminal window
- Maintains the project's simple and clean coding philosophy

## Testing
- CTRL+Q properly clears terminal on exit
- Unsaved changes warning still works correctly
- Code compiles without warnings with `-Wall -W -pedantic -std=c99`
- Syntax highlighting for C/C++ comments works correctly
- Resizing the terminal window multiple times no longer causes crashes or unexpected exits.
- The editor adapts correctly to new window dimensions, maintaining cursor and scroll positions.
- No impact on other functionality
