# tri-cli — Manual Testing Plan

## Test Environment

- **OS**: macOS
- **Tailscale**: App Store version
- **Rust**: stable

## Test Cases

### TC-001: Start Funnel

**Steps**:
1. Ensure Funnel is not running (`tri-cli stop`)
2. Run: `tri-cli start`

**Expected**:
- Shows header with "tri"
- Spinner appears
- Success message "✅ Funnel started successfully!"
- Status box shows ACTIVE
- Shows 3 URLs (main, health, api/status)

**Actual**: ✅ PASS

---

### TC-002: Status When Active

**Steps**:
1. Start Funnel (`tri-cli start`)
2. Run: `tri-cli status`

**Expected**:
- Shows header with "tri"
- Status box shows Device name
- Funnel: ACTIVE ✅
- Shows URL

**Actual**: ✅ PASS

---

### TC-003: Status When Inactive

**Steps**:
1. Stop Funnel (`tri-cli stop`)
2. Run: `tri-cli status`

**Expected**:
- Shows header with "tri"
- Status box shows Device name
- Funnel: INACTIVE ❌
- No URL shown

**Actual**: ✅ PASS

---

### TC-004: Stop Funnel

**Steps**:
1. Start Funnel
2. Run: `tri-cli stop`

**Expected**:
- Shows header with "tri"
- Spinner appears
- Success message "✅ Funnel stopped"

**Actual**: ✅ PASS

---

### TC-005: Open Dashboard

**Steps**:
1. Start Funnel
2. Run: `tri-cli open`

**Expected**:
- Info message with URL
- Success "✅ Dashboard opened in browser"
- Browser opens with funnel URL

**Actual**: ✅ PASS

---

### TC-006: Start When Already Running

**Steps**:
1. Start Funnel
2. Run: `tri-cli start` again

**Expected**:
- Info message "Funnel is already running!"
- Shows status box
- Does not create duplicate funnel

**Actual**: ✅ PASS

---

### TC-007: Stop When Not Running

**Steps**:
1. Ensure Funnel is stopped
2. Run: `tri-cli stop`

**Expected**:
- Shows success message
- Does not crash

**Actual**: ✅ PASS

---

### TC-008: Open When Not Running

**Steps**:
1. Stop Funnel
2. Run: `tri-cli open`

**Expected**:
- Error message "Funnel is not running"
- Does not crash

**Actual**: ✅ PASS

---

### TC-009: Help Command

**Steps**:
1. Run: `tri-cli --help`

**Expected**:
- Shows usage
- Lists all subcommands (start, stop, status, open)
- Shows options

**Actual**: ✅ PASS

---

## Summary

| Test | Result |
|------|--------|
| TC-001: Start Funnel | ✅ PASS |
| TC-002: Status (Active) | ✅ PASS |
| TC-003: Status (Inactive) | ✅ PASS |
| TC-004: Stop Funnel | ✅ PASS |
| TC-005: Open Dashboard | ✅ PASS |
| TC-006: Start When Running | ✅ PASS |
| TC-007: Stop When Stopped | ✅ PASS |
| TC-008: Open When Stopped | ✅ PASS |
| TC-009: Help Command | ✅ PASS |

**Total**: 9/9 tests passed
