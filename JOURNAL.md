## Week 7 — Issue selection

**Issue link:** [https://github.com/ascherj/pathreview/issues/80]

**Issue title:** [DELETE /profiles/{profile_id} doesn't cascade to delete associated reviews and embeddings #80]

**Tier:** [ ] Tier 1  [X] Tier 2  [ ] Tier 3

**Problem summary:**
[When a user is deleted their associated reviews and vector store embeddings are left in the app. A successful bug fix would delete the reviews associated with the deleted user from the postgreSQL database and the user's associated vector store embeddings. This would involve mostly working with the api and databases]

**Branch name:** [fix/80-cascading-delete]

**Setup confirmation:** [X] App runs locally at localhost:5173

**Cohort ledger:** [X] Issue added to cohort ledger



## Week 8 — Reproduction & solution planning

**Reproduction commit link:** [link to commit documenting the reproduced issue]
https://github.com/CrabHeadd/pathreview/commit/a3e3abfa573c60db6442778b01f70b6889900e63
**Reproduction summary:**
[1–2 sentences: How did you reproduce the issue? What did you observe?]
When I deleted user1@example.com by authenticating on the swagger ui and then inputting their profile id, all of their reviews were deleted in the docker database as expected, I checked, however in the /profiles/{profile_id} delete endpoint, and in the function delete_profile in profile_service.py called by the endpoint, nothing ever gets rid of the vector store embeddings associated with the deleted user, thus they are likely still there. 

**PLAN.md link:** [link to PLAN.md in your fork]
https://github.com/CrabHeadd/pathreview/commit/a3e3abfa573c60db6442778b01f70b6889900e63#diff-1d972b4ac04c89bf54f79f2111064626b16aeb8bb9488f4ca0aed3ab1e728d2c
**Walkthrough video (recommended):** [link to your Loom video, ≤2 min — recommended, not graded]

**Blockers or open questions:**
[Anything you're still uncertain about going into Week 9, or leave blank]
There was supposed to be orphaned reviews? But I checked inside the database and the reviews that had their profile deleted were deleted. Also am a little unsure of how to work with the vector store embeddings, but the function delete_by_source_id in profile_service.py gives me hope.