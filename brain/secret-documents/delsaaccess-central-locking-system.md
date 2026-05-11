# DelsaAccess Central Locking System

## Overview
Centralized licensing and installation locking mechanism for Jafam-local-Azure.

Core goals:
- Validate signed license keys
- Bind licenses to InstallationId
- Lock application access when invalid or expired
- Avoid database manipulation

## Main Components

### SharedLibrary
- DelsaAccessValidator.cs
- DelsaAccessMiddleware.cs

### Registered In
- CoreService
- IdentityService
- MudApp

### Key Tool
- tools/DelsaAccessKeyTool

## Runtime Behavior

When enabled:
- Invalid license => HTML lock page
- APIs => HTTP 423 Locked
- Database remains untouched

## Planned Future Enhancements
- Grace period
- Audit log
- Renewal flow
- Expiration warnings
- License dashboard
- Hardware fingerprinting

## Notes
Each issued key currently has a one-month expiration.
