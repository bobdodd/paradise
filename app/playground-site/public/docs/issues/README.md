# Paradise Issue Documentation

Comprehensive help for all accessibility issues detected by Paradise.

## How to Use This Documentation

When Paradise detects an accessibility issue in VS Code:

1. **Hover over the squiggly line** to see the issue description, WCAG criteria, and confidence level
2. **Click the issue code** (e.g., `mouse-only-click`) in the diagnostic to open the detailed help page
3. **Press Ctrl+. (or Cmd+.)** to see available quick fixes

Each help page includes:
- **Description**: What the issue is and why it matters
- **The Problem**: Example code showing the issue
- **The Solution**: How to fix it with code examples
- **Common Patterns**: Real-world scenarios
- **Testing**: How to verify the fix works
- **Additional Resources**: Links to WCAG docs and tutorials

## Available Issue Documentation

### Keyboard Accessibility

- **[mouse-only-click](mouse-only-click.md)** - Click handler without keyboard equivalent
  - WCAG: 2.1.1 (Keyboard)
  - Severity: Warning
  - Quick Fix: ✓ Available

- **[potential-keyboard-trap](potential-keyboard-trap.md)** - Tab key intercepted with preventDefault without Escape handler
  - WCAG: 2.1.2 (No Keyboard Trap)
  - Severity: Warning
  - Quick Fix: ✓ Available

- **[screen-reader-conflict](screen-reader-conflict.md)** - Single-character keyboard shortcuts conflict with screen reader navigation
  - WCAG: 2.1.1, 2.1.4 (Keyboard, Character Key Shortcuts)
  - Severity: Warning
  - Quick Fix: ✓ Available

- **[deprecated-keycode](deprecated-keycode.md)** - Using deprecated event.keyCode or event.which
  - WCAG: 2.1.1 (Keyboard)
  - Severity: Info
  - Quick Fix: ✓ Available

- **[tab-without-shift](tab-without-shift.md)** - Tab key handler doesn't check event.shiftKey for reverse navigation
  - WCAG: 2.1.1 (Keyboard)
  - Severity: Info
  - Quick Fix: ✓ Available

- **[missing-escape-handler](missing-escape-handler.md)** - Modal or dialog without Escape key handler
  - WCAG: 2.1.2 (No Keyboard Trap)
  - Severity: Warning
  - Quick Fix: ✓ Available

- **[missing-arrow-navigation](missing-arrow-navigation.md)** - ARIA widget role without arrow key navigation
  - WCAG: 2.1.1, 4.1.2 (Keyboard, Name, Role, Value)
  - Severity: Info
  - Quick Fix: ✗ Manual implementation required

- **[screen-reader-arrow-conflict](screen-reader-arrow-conflict.md)** - Arrow key handlers interfere with screen reader browse mode
  - WCAG: 2.1.1 (Keyboard)
  - Severity: Info
  - Quick Fix: ✗ Manual fix required

### Code Integrity

- **[orphaned-event-handler](orphaned-event-handler.md)** - Event handler attached to non-existent element
  - WCAG: 4.1.2 (Name, Role, Value)
  - Severity: Error
  - Quick Fix: ✗ Manual fix required

### ARIA Relationships

- **[missing-aria-connection](missing-aria-connection.md)** - ARIA attribute references non-existent element
  - WCAG: 4.1.2, 1.3.1 (Info and Relationships)
  - Severity: Warning
  - Quick Fix: ✗ Manual fix required

### ARIA Semantics

- **[invalid-role](invalid-role.md)** - Using ARIA role value that doesn't exist in ARIA 1.2 specification
  - WCAG: 4.1.2 (Name, Role, Value)
  - Severity: Error
  - Quick Fix: ✓ Available

- **[interactive-role-static](interactive-role-static.md)** - Interactive ARIA role without required event handlers
  - WCAG: 2.1.1, 4.1.2 (Keyboard, Name, Role, Value)
  - Severity: Error
  - Quick Fix: ✓ Available

- **[aria-expanded-static](aria-expanded-static.md)** - aria-expanded set but never updated
  - WCAG: 4.1.2 (Name, Role, Value)
  - Severity: Warning
  - Quick Fix: ✓ Available

- **[dialog-missing-label](dialog-missing-label.md)** - Dialog role without accessible label
  - WCAG: 4.1.2 (Name, Role, Value)
  - Severity: Error
  - Quick Fix: ✓ Available

- **[missing-required-aria](missing-required-aria.md)** - ARIA role missing required attributes
  - WCAG: 4.1.2 (Name, Role, Value)
  - Severity: Error
  - Quick Fix: ✓ Available

- **[assertive-live-region](assertive-live-region.md)** - Overuse of aria-live="assertive"
  - WCAG: 4.1.3 (Status Messages)
  - Severity: Warning
  - Quick Fix: ✓ Available

- **[aria-hidden-true](aria-hidden-true.md)** - aria-hidden on focusable/interactive element
  - WCAG: 4.1.2 (Name, Role, Value)
  - Severity: Error
  - Quick Fix: ✓ Available

- **[aria-label-overuse](aria-label-overuse.md)** - aria-label overriding visible text
  - WCAG: 2.5.3 (Label in Name)
  - Severity: Info
  - Quick Fix: ✓ Available

### Focus Management

- **[removal-without-focus-management](removal-without-focus-management.md)** - Element removed without checking if it has focus
  - WCAG: 2.4.3, 2.4.7 (Focus Order, Focus Visible)
  - Severity: Warning
  - Quick Fix: ✓ Available

- **[hiding-without-focus-management](hiding-without-focus-management.md)** - Element hidden without checking if it has focus
  - WCAG: 2.4.3, 2.4.7 (Focus Order, Focus Visible)
  - Severity: Warning
  - Quick Fix: ✓ Available

- **[hiding-class-without-focus-management](hiding-class-without-focus-management.md)** - classList operation may hide element without focus check
  - WCAG: 2.4.7 (Focus Visible)
  - Severity: Info
  - Quick Fix: ✓ Available

- **[possibly-non-focusable](possibly-non-focusable.md)** - Attempting to focus element that may not be focusable
  - WCAG: 2.4.3, 4.1.2 (Focus Order, Name, Role, Value)
  - Severity: Warning
  - Quick Fix: ✓ Available

- **[standalone-blur](standalone-blur.md)** - Removing focus without explicitly moving it
  - WCAG: 2.4.7 (Focus Visible)
  - Severity: Info
  - Quick Fix: ✓ Available

- **[focus-restoration-missing](focus-restoration-missing.md)** - Modal/dialog closes without restoring focus
  - WCAG: 2.4.3 (Focus Order)
  - Severity: Warning
  - Quick Fix: ✓ Available

- **[focus-order-conflict](focus-order-conflict.md)** - Positive tabindex creates unpredictable focus order
  - WCAG: 2.4.3 (Focus Order)
  - Severity: Warning
  - Quick Fix: ✗ Manual fix required

### Visual & Interactive

- **[visibility-focus-conflict](visibility-focus-conflict.md)** - Element is focusable but visually hidden
  - WCAG: 2.4.7 (Focus Visible), 4.1.2 (Name, Role, Value)
  - Severity: Error
  - Quick Fix: ✗ Manual fix required

### Document Structure

- **[no-headings-on-page](no-headings-on-page.md)** - Page contains no heading elements
  - WCAG: 1.3.1, 2.4.6 (Info and Relationships, Headings and Labels)
  - Severity: Error
  - Quick Fix: ✓ Available

- **[no-h1-on-page](no-h1-on-page.md)** - Page has headings but missing H1 element
  - WCAG: 1.3.1, 2.4.6 (Info and Relationships, Headings and Labels)
  - Severity: Error
  - Quick Fix: ✓ Available

- **[multiple-h1-headings](multiple-h1-headings.md)** - Page contains more than one H1 element
  - WCAG: 1.3.1 (Info and Relationships)
  - Severity: Warning
  - Quick Fix: ✓ Available

- **[page-doesnt-start-with-h1](page-doesnt-start-with-h1.md)** - First heading on page is not H1
  - WCAG: 1.3.1, 2.4.6 (Info and Relationships, Headings and Labels)
  - Severity: Warning
  - Quick Fix: ✓ Available

- **[heading-levels-skipped](heading-levels-skipped.md)** - Heading hierarchy has gaps (e.g., H1 to H3)
  - WCAG: 1.3.1 (Info and Relationships)
  - Severity: Error
  - Quick Fix: ✓ Available

- **[empty-heading](empty-heading.md)** - Heading element contains no text content
  - WCAG: 2.4.6, 1.3.1 (Headings and Labels, Info and Relationships)
  - Severity: Error
  - Quick Fix: ✓ Available

- **[hidden-heading](hidden-heading.md)** - Heading hidden with display:none or visibility:hidden
  - WCAG: 1.3.1 (Info and Relationships)
  - Severity: Warning
  - Quick Fix: ✓ Available

- **[heading-too-long](heading-too-long.md)** - Heading exceeds 60 characters
  - WCAG: 2.4.6 (Headings and Labels)
  - Severity: Warning
  - Quick Fix: ✗ Manual review recommended

- **[heading-near-length-limit](heading-near-length-limit.md)** - Heading approaching 60 character limit (40-60 chars)
  - WCAG: 2.4.6 (Headings and Labels)
  - Severity: Info
  - Quick Fix: ✗ Manual review recommended

- **[aria-level-without-role](aria-level-without-role.md)** - Element has aria-level but missing role="heading"
  - WCAG: 4.1.2 (Name, Role, Value)
  - Severity: Error
  - Quick Fix: ✓ Available

### React-Specific

- **[react-portal-accessibility](react-portal-accessibility.md)** - Portal renders outside parent DOM hierarchy
  - WCAG: 2.1.1, 2.4.3, 1.3.2, 4.1.2
  - Severity: Warning
  - Quick Fix: ✓ Comprehensive guidance

- **[react-stop-propagation](react-stop-propagation.md)** - stopPropagation blocks assistive technology events
  - WCAG: 2.1.1, 4.1.2
  - Severity: Warning/Error
  - Quick Fix: ✓ Alternative approaches

## Documentation Status

✅ **Complete**: Comprehensive help page with examples, testing, and resources
🚧 **In Progress**: Basic documentation available
📋 **Planned**: Not yet documented

| Issue Type | Status | WCAG | Severity |
|------------|--------|------|----------|
| mouse-only-click | ✅ | 2.1.1 | Warning |
| potential-keyboard-trap | ✅ | 2.1.2 | Warning |
| screen-reader-conflict | ✅ | 2.1.1, 2.1.4 | Warning |
| deprecated-keycode | ✅ | 2.1.1 | Info |
| tab-without-shift | ✅ | 2.1.1 | Info |
| missing-escape-handler | ✅ | 2.1.2 | Warning |
| missing-arrow-navigation | ✅ | 2.1.1, 4.1.2 | Info |
| screen-reader-arrow-conflict | ✅ | 2.1.1 | Info |
| orphaned-event-handler | ✅ | 4.1.2 | Error |
| missing-aria-connection | ✅ | 4.1.2, 1.3.1 | Warning |
| invalid-role | ✅ | 4.1.2 | Error |
| interactive-role-static | ✅ | 2.1.1, 4.1.2 | Error |
| aria-expanded-static | ✅ | 4.1.2 | Warning |
| dialog-missing-label | ✅ | 4.1.2 | Error |
| missing-required-aria | ✅ | 4.1.2 | Error |
| assertive-live-region | ✅ | 4.1.3 | Warning |
| aria-hidden-true | ✅ | 4.1.2 | Error |
| aria-label-overuse | ✅ | 2.5.3 | Info |
| removal-without-focus-management | ✅ | 2.4.3, 2.4.7 | Warning |
| hiding-without-focus-management | ✅ | 2.4.3, 2.4.7 | Warning |
| hiding-class-without-focus-management | ✅ | 2.4.7 | Info |
| possibly-non-focusable | ✅ | 2.4.3, 4.1.2 | Warning |
| standalone-blur | ✅ | 2.4.7 | Info |
| focus-restoration-missing | ✅ | 2.4.3 | Warning |
| focus-order-conflict | ✅ | 2.4.3 | Warning |
| visibility-focus-conflict | ✅ | 2.4.7 | Error |
| no-headings-on-page | ✅ | 1.3.1, 2.4.6 | Error |
| no-h1-on-page | ✅ | 1.3.1, 2.4.6 | Error |
| multiple-h1-headings | ✅ | 1.3.1 | Warning |
| page-doesnt-start-with-h1 | ✅ | 1.3.1, 2.4.6 | Warning |
| heading-levels-skipped | ✅ | 1.3.1 | Error |
| empty-heading | ✅ | 2.4.6, 1.3.1 | Error |
| hidden-heading | ✅ | 1.3.1 | Warning |
| heading-too-long | ✅ | 2.4.6 | Warning |
| heading-near-length-limit | ✅ | 2.4.6 | Info |
| aria-level-without-role | ✅ | 4.1.2 | Error |
| react-portal-accessibility | ✅ | Various | Warning |
| react-stop-propagation | ✅ | 2.1.1 | Warning/Error |

## Contributing

Help us improve this documentation! If you:
- Find an issue that needs better explanation
- Have real-world examples to share
- Spot errors or omissions

If you have suggestions for improvements, please reach out to the Paradise development team.

## WCAG Quick Reference

Paradise maps issues to WCAG 2.1 success criteria:

- **[1.3.1 Info and Relationships](https://www.w3.org/WAI/WCAG21/Understanding/info-and-relationships)** - Structure and relationships are programmatically determined
- **[2.1.1 Keyboard](https://www.w3.org/WAI/WCAG21/Understanding/keyboard)** - All functionality available via keyboard
- **[2.1.2 No Keyboard Trap](https://www.w3.org/WAI/WCAG21/Understanding/no-keyboard-trap)** - Users can navigate away using keyboard alone
- **[2.1.4 Character Key Shortcuts](https://www.w3.org/WAI/WCAG21/Understanding/character-key-shortcuts)** - Single-character shortcuts can be turned off or remapped
- **[2.4.1 Bypass Blocks](https://www.w3.org/WAI/WCAG21/Understanding/bypass-blocks)** - Mechanism to skip repeated content blocks
- **[2.4.3 Focus Order](https://www.w3.org/WAI/WCAG21/Understanding/focus-order)** - Navigation order is logical and intuitive
- **[2.4.6 Headings and Labels](https://www.w3.org/WAI/WCAG21/Understanding/headings-and-labels)** - Headings and labels describe topic or purpose
- **[2.4.7 Focus Visible](https://www.w3.org/WAI/WCAG21/Understanding/focus-visible)** - Keyboard focus indicator is visible
- **[2.4.10 Section Headings](https://www.w3.org/WAI/WCAG21/Understanding/section-headings)** - Section headings organize content
- **[2.5.3 Label in Name](https://www.w3.org/WAI/WCAG21/Understanding/label-in-name)** - Accessible names contain the visible text label
- **[4.1.2 Name, Role, Value](https://www.w3.org/WAI/WCAG21/Understanding/name-role-value)** - UI components have accessible names and roles
- **[4.1.3 Status Messages](https://www.w3.org/WAI/WCAG21/Understanding/status-messages)** - Status messages are announced to assistive technologies

## Additional Resources

### Official Standards
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [ARIA Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/)

### Testing Tools
- [NVDA Screen Reader](https://www.nvaccess.org/) (Windows, free)
- [JAWS Screen Reader](https://www.freedomscientific.com/products/software/jaws/) (Windows, commercial)
- [VoiceOver](https://www.apple.com/accessibility/voiceover/) (macOS/iOS, built-in)
- [axe DevTools](https://www.deque.com/axe/devtools/) (Browser extension)

### Learning Resources
- [WebAIM](https://webaim.org/) - Accessibility tutorials and articles
- [The A11Y Project](https://www.a11yproject.com/) - Community-driven accessibility resources
- [MDN Accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility) - Developer documentation

---

**Maintained by:** Paradise Development Team
**Last Updated:** January 2026
**License:** GPL-3.0-or-later
