# 【entity-Azure¦canonical_name=Azure】 Resource Locks

## Overview
This project implements 【entity-Azure¦canonical_name=Azure】 Resource Locks to prevent accidental deletion or modification of critical cloud resources. Locks act as safety guardrails for business continuity and data protection.

## Lock Types
| Lock Type | Can Modify? | Can Delete? |
| CanNotDelete | Yes | No |
| ReadOnly | No | No |

- CanNotDelete: Allows modification but blocks deletion.
- ReadOnly: Blocks both modification and deletion. Read-only access only.

## Levels Tested
1. Subscription Level
2. Resource Group Level
3. Resource Level (Storage Account)

## What I Did
1. Created a Resource Group and a Storage Account.
2. Applied CanNotDelete lock at Resource Group level.
3. Applied ReadOnly lock at Resource level.
4. Attempted to delete the locked Storage Account - it FAILED with an error. This proves the lock works.
5. Attempted to modify the ReadOnly resource - it FAILED with an error.
6. Verified that child resources inherit protection from the Resource Group lock.
7. Used Azure CLI to list, create, and remove locks.

## Results / Evidence
- See screenshots folder:
- lock-created.png - Lock visible in Portal
- delete-blocked.png - Error when trying to delete locked resource
- modify-blocked.png - Error when trying to modify ReadOnly resource
- resource-group-inheritance.png - Child resource blocked by parent lock

## Conclusion
Resource Locks successfully prevent accidental deletion and modification. They are essential for cloud governance and disaster prevention.

Author: Bathokoro221 / BathoTech