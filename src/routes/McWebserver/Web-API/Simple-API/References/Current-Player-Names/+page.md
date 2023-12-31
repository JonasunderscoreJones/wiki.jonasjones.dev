## Server Current Player Names
---
- Returns the Server's currently online players
```
http://localhost:8080/api/v1/playernames
```
- Response:
```json
[
  {
    "ID": "c888eef5-edb7-4ceb-bbf3-987731de9747",
    "NAME": "Jonas_Jones"
  }
]
```
NOTE: *v0.3.0 returns an additional property* `LEGACY` *for every player that states whether or not the account is a legacy account or not. Since mc 1.20.2 and the mod release 0.3.1 this was removed due to the end of the account migration period, where all legacy accounts were migrated to microsoft accounts. (This property is now always false and thus redundant)*