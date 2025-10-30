### Features to Design (scope)

- Storing and Getting Posts / Images
- Like + Comment on Posts / Images
- Follow Someone
- Publish a news feed

---

## Storing and getting Images

Follow Designing Tinder by Gaurav Sen ( Youtube ). This feature is defined in that video.

**Todo**: when done with deisgning tinder, also reflect notes here

### Like + Comment on Posts / Images

We can do like and comment on a normal post. We cannot reply or comment on a comment. We can Like a comment though.

The Entity Releation diagram shown below can be used to store how likes, comments , posts are stored. We can have 4 tables namely likes, comments, posts and activtiy. Activity table is to store likes on a comment or a post, a separate table is needed for this aggregation.
