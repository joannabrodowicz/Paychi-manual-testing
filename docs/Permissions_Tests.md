# Permissions of group member's roles

I performed role‑based permission testing to verify how different user roles interact with system functions and to identify any inconsistencies in the permission logic.

## Roles and permissions matrix - expected behaviours

| Action                             | Owner         | Admin         | Member        |
| ---------------------------------- | ------------- | ------------- | ------------- |
| Invite new members to the group    | Allowed       | Allowed       | Not Allowed   |
| Remove regular members             | Allowed       | Allowed       | Not Allowed   |
| Remove admins                      | Allowed       | Not Allowed   | Not Allowed   |
| Remove owner                       | Not Allowed   | Not Allowed   | Not Allowed   |
| Change roles                       | Allowed       | Not Allowed   | Not Allowed   |
| Create group shopping lists        | Allowed       | Allowed       | Allowed       |
| Add items to shopping lists        | Allowed       | Allowed       | Allowed       |
| Remove items from shopping lists   | Allowed       | Allowed       | Allowed       |
| Delete shopping lists              | To Be Defined | To Be Defined | To Be Defined |
| Create group expenses              | Allowed       | Allowed       | Allowed       |
| Delete expense (no settlements)    | To Be Defined | To Be Defined | To Be Defined |
| Delete expense (settlements exist) | Not Allowed   | Not Allowed   | Not Allowed   |

---

Permissions related to deleting shopping lists and expenses were marked as "To Be Defined", because the developer confirmed that the logic for these permissions was still being designed.

## Roles and permissions matrix - test results

| Action                             | Owner           | Admin           | Member          |
| ---------------------------------- | --------------- | --------------- | --------------- |
| Invite new members to the group    | Passed          | Passed          | Passed          |
| Remove regular members             | Passed          | Passed          | Passed          |
| Remove admins                      | Passed          | Passed          | Passed          |
| Remove owner                       | Passed          | Passed          | Passed          |
| Change roles                       | Passed          | Passed          | Passed          |
| Create group shopping lists        | Passed          | Passed          | Passed          |
| Add items to shopping lists        | Passed          | Passed          | Passed          |
| Remove items from shopping lists   | Passed          | Passed          | Passed          |
| Delete shopping lists              | See notes below | See notes below | See notes below |
| Create group expenses              | Passed          | Passed          | Passed          |
| Delete expense (no settlements)    | See notes below | See notes below | See notes below |
| Delete expense (settlements exist) | Passed          | Passed          | Passed          |

Of the 36 permission combinations, 30 work correctly.

---

## Notes

Current behavior of undefined permissions:

Shopping lists and expenses can only be deleted by their creator, regardless of the role in the group, e.g. a member can delete a group list that he created himself, the owner cannot delete a list created by a member

Expected future behavior (based on developer roadmap):

Member: will lose the ability to delete any list or expense.

Owner & Admin: will gain the ability to delete every list or expense in the group (as long as no settlements are attached).
