## Week 7 — Issue selection

**Issue link:** [https://github.com/ascherj/pathreview/issues/80]

**Issue title:** [DELETE /profiles/{profile_id} doesn't cascade to delete associated reviews and embeddings #80]

**Tier:** [ ] Tier 1  [X] Tier 2  [ ] Tier 3

**Problem summary:**
[When a user is deleted their associated reviews and vector store embeddings are left in the app. A successful bug fix would delete the reviews associated with the deleted user from the postgreSQL database and the user's associated vector store embeddings. This would involve mostly working with the api and databases]

**Branch name:** [fix/80-cascading-delete]

**Setup confirmation:** [X] App runs locally at localhost:5173

**Cohort ledger:** [X] Issue added to cohort ledger