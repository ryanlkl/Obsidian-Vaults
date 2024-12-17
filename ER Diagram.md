# Entities
- User
	- userId
	- username
	- email
	- password
	- dateJoined
	- lastLogin
	- (friends)
- Friendship
	- userId1
	- userId2
	- status (Enum e.g. Pending, Accepted, Blocked)
	- sinceDate
- Review
	- reviewId
	- userId
	- title
	- body
	- rating
	- createdDate
	- modifiedDate
- Media
	- mediaId
	- title
	- synopsis
	- releaseDate
	- mediaType
	- actors
- Statistic
	- statId
	- userId
	- totalHoursWatched
	- mostWatchedMediaId
	- totalMediaWatched
	- mostWatchedActor
	- mostWatchedGenre

# Relationship
## User - Friendship
- A user can have many friends and can be friends with many users
- Friendships is the middle table
- 1 to many relationship
## User - Review
- A user can write many reviews
- 1 to many relationship
## User - Statistic
- A user has one statistics record
- 1 to 1 relationship
## Media - Review
- Media can have many reviews
- 1 to many relationship