# Platform Retirement Plan: [Platform Name]

| | |
|---|---|
| **Owner** | [Name, role] |
| **Executive sponsor** | [Name, role] |
| **Target decommission date** | [Date] |
| **Status** | Draft / Approved / In progress / Complete |
| **Last updated** | [Date] |

---

## 1. Summary

*Two or three sentences: what is being retired, why, and what replaces it (if anything).*

**Platform:** [Name and version]
**Reason for retirement:** [End of vendor support / replaced by X / cost / security risk / low usage]
**Replacement:** [New system, or "none: function is no longer needed"]

## 2. Scope

**In scope**
- [Environments: production, test, DR]
- [Data stores, file shares, databases]
- [Licenses and contracts]

**Out of scope**
- [Anything adjacent that is NOT being touched]

## 3. Inventory: know what you're turning off

*The most common retirement failure is an unknown dependency. Do this section first and do it thoroughly.*

### Users
| Group | Approx. # users | How they use it | Contact |
|---|---|---|---|
| | | | |

### Integrations and dependencies
| System | Direction (in/out) | What flows | Owner | Plan |
|---|---|---|---|---|
| | | | | Migrate / Retire / Repoint |

*Check for scheduled jobs, API keys, service accounts, SSO configs, DNS entries, and firewall rules. These are the hidden integrations that break on shutdown day.*

### Data
| Data set | Volume | Retention requirement | Disposition |
|---|---|---|---|
| | | [Legal/regulatory period] | Migrate / Archive / Destroy |

## 4. Phased plan

| Phase | What happens | Exit criteria | Target date |
|---|---|---|---|
| **1. Discover** | Complete inventory; confirm owners | All dependencies identified and owned | |
| **2. Decide** | Disposition for every user group, integration, and data set | Sponsor sign-off on this plan | |
| **3. Communicate** | Announce timeline; train users on the replacement | Users acknowledge; no open objections | |
| **4. Migrate** | Move data and users; repoint integrations | Validation checks pass; parallel run clean | |
| **5. Freeze** | Read-only mode; no new data | [X] weeks with no business-critical access | |
| **6. Decommission** | Shut down services; revoke access; end contracts | Systems off; accounts disabled; licenses cancelled | |
| **7. Close out** | Archive records; destroy data per policy; lessons learned | Certificate of destruction filed; final report sent | |

## 5. Risks

| Risk | Likelihood | Impact | Mitigation | Owner |
|---|---|---|---|---|
| Undiscovered integration breaks on shutdown | Medium | High | Freeze phase with monitoring; keep restorable backup for [X] days | |
| Data needed later for audit or legal hold | Medium | High | Confirm retention with Legal/Compliance before destruction | |
| Users keep working in the old system | High | Medium | Read-only freeze; clear cutoff date; leadership messaging | |
| Contract auto-renews | Low | Medium | Calendar the notice deadline now | |

## 6. Rollback / exit strategy

*What you do if something critical breaks after shutdown.*

- **Rollback window:** [Until date] the platform can be restored from [backup/snapshot].
- **Rollback trigger:** [Who can call it, and on what criteria]
- **Point of no return:** [The step after which rollback is no longer possible, usually data destruction or contract termination]

## 7. Communication plan

| When | Audience | Message | Channel | Sender |
|---|---|---|---|---|
| [T-90 days] | All users | Retirement announced; timeline | Email | Sponsor |
| [T-30 days] | All users | Reminder; training links | Email + meeting | Owner |
| [T-7 days] | All users | Final notice; freeze date | Email | Owner |
| [T+0] | All users | System retired; where to go now | Email | Owner |

## 8. Decommission checklist

- [ ] All user groups migrated or confirmed no longer needed
- [ ] All integrations repointed or disabled
- [ ] Data migrated, archived, or approved for destruction
- [ ] Retention and legal hold confirmed with Legal/Compliance
- [ ] Final backup taken and stored per policy
- [ ] User accounts and service accounts disabled
- [ ] SSO, DNS, and firewall entries removed
- [ ] Monitoring and alerting removed
- [ ] Licenses and support contracts cancelled (notice dates met)
- [ ] Documentation updated (CMDB, architecture diagrams, runbooks)
- [ ] Data destruction completed and certified
- [ ] Lessons learned captured

## 9. Sign-off

| Role | Name | Date |
|---|---|---|
| Platform owner | | |
| Executive sponsor | | |
| Security | | |
| Legal / Compliance | | |
