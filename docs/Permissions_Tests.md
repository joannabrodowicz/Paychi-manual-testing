# Permissions of group member's roles

## Roles and permissions matrix - expected behaviours

| Action                             | Owner            | Admin            | Member           |
| ---------------------------------- | ---------------- | ---------------- | ---------------- |
| Invite new members to the group    | ✅ Allowed       | ✅ Allowed       | ❌ Not Allowed   |
| Remove regular members             | ✅ Allowed       | ✅ Allowed       | ❌ Not Allowed   |
| Remove admins                      | ✅ Allowed       | ❌ Not Allowed   | ❌ Not Allowed   |
| Remove owner                       | ❌ Not Allowed   | ❌ Not Allowed   | ❌ Not Allowed   |
| Change roles                       | ✅ Allowed       | ❌ Not Allowed   | ❌ Not Allowed   |
| Create group shopping lists        | ✅ Allowed       | ✅ Allowed       | ✅ Allowed       |
| Add items to shopping lists        | ✅ Allowed       | ✅ Allowed       | ✅ Allowed       |
| Remove items from shopping lists   | ✅ Allowed       | ✅ Allowed       | ✅ Allowed       |
| Delete shopping lists              | 🔲 To Be Defined | 🔲 To Be Defined | 🔲 To Be Defined |
| Create group expenses              | ✅ Allowed       | ✅ Allowed       | ✅ Allowed       |
| Delete expense (no settlements)    | 🔲 To Be Defined | 🔲 To Be Defined | 🔲 To Be Defined |
| Delete expense (settlements exist) | ❌ Not Allowed   | ❌ Not Allowed   | ❌ Not Allowed   |

---

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

---

## Notes

Current behaviors of not defined permissions: only the creator of the shopping list or expense can delete group lists, regardless of the group role.

Expected future behavior (per developer roadmap):

- Member: will lose the ability to delete any list or expense
- Owner and Admin: will gain the ability to delete all list or expense (without settlements) in the group
