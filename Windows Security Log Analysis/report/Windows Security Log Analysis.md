# Windows Security Log Analysis Report

## 1. Objective
To investigate Windows Security Event Logs and identify failed and successful login attempts using Windows Event Viewer.

## 2. Tools Used
- Windows 11
- Windows Event Viewer
- Security Event Logs

## 3. Findings

### Finding 1: Failed Login Attempt

- **Event ID:** 4625
- **Date:** 17 October 2026
- **Time:** 11:50:29 AM
- **Account:** Naima
- **Logon Type:** 2 (Interactive logon)
- **Failure Reason:** Unknown user name or bad password
- **Status:** `0xC000006D`
- **Substatus:** `0xC000006A`
- **Source Address:** `127.0.0.1`

**Analysis:** Event ID 4625 records a failed login attempt. The status and substatus are consistent with an incorrect password. The source address `127.0.0.1` is the loopback address, indicating the local computer rather than an identified external IP address.

### Finding 2: Successful Login

- **Event ID:** 4624
- **Date:** 17 October 2026
- **Time:** 11:50:32 AM
- **Account:** Naima
- **Logon Type:** 2 (Interactive logon)
- **Source Address:** `127.0.0.1`

**Analysis:** Event ID 4624 records a successful login. It occurred approximately three seconds after the failed attempt for the same account.

## 4. Correlation and Interpretation

The failed login was followed shortly by a successful login for the same account. One possible explanation is that an incorrect password was entered and then corrected. However, the logs alone do not prove this explanation or establish who performed the attempts.

The reviewed events do not, by themselves, confirm malicious activity.

## 5. Evidence

Screenshots of the failed login (Event ID 4625) and successful login (Event ID 4624) are stored in the `evidence/` folder.

## 6. Conclusion

This investigation demonstrated how Windows Security Event IDs 4625 and 4624 can be used to identify and correlate failed and successful login events. Further log review would be needed to determine whether any additional suspicious activity occurred.

## 7. Skills Practised

- Reviewing Windows Security Logs
- Interpreting Event IDs 4625 and 4624
- Comparing event timestamps
- Documenting findings and limitations
- Applying basic security investigation techniques
