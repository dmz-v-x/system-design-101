1. Different Requirements

General Requirements
Specific Requirements
Components Architecture
Data Entities
Data API
Data Store
Infinite Scroll
Optimization
Accessibility

2. General Requirements: Feature we want to build

-> Infinite Scrollable News Feed Where stories appears based on user subscription, friends and interests
-> User can store the story
-> User can post the story and attach comments, links, images and videos

3. Specific/Functional Requirements

-> We wnat the feature to be accessible on wide range of devices
-> We want the feature to be accessible for people with disabilities

4. Componenets Architecture (Story Component)

We have a story component that has an avatar, title and date of posting, some text and images and a panel to like comment and share.
Below that we also have a list of comments with each comment having an avatar text and comment input.

5. We have a news feed and news feed contains the story component and the story component have story card, comment list, comment input and comment list contains comments.

6. Data Models:

-> Now we need to have story data, comments and some images so how can we descibe such entities

type Story = {
  id: number;
  comments: Comment[];
  media: Media[];
  date: number;
  content: string;
  origin: {
    id: string;
    type: OriginType
    name: string;
    data: ...
  }
}

type Comment = {
  id: number;
  authorId: string;
  media: Media[];
  date: number;
  content: string;
}

type Media = {
  type: "link" | "video";
  url: string;
}

7. APIs

getPosts(api_key, user_id, excludeComments, cursor, pageSize, minID)
createPost(api_key, user_id, post_data)
createComment(api_key, user_id, post_id, comment_data)
subscribeNewStories

8. To call our api we can use either rest api or graphql apis, so let's say we want to use rest api.

9. Data Store

WE attach a datastore ot news feed to fetch the data, how should data be stored in datastore and how will it show up in the ui?

How we will load new stories if new stories comes up? 
-> Long Polling: Full Request
-> Web Sockets: Bidirectional, HTTP2 not supported
-> SSE (Server Side Events): Very Effective, Easy to Load Balance

So we will load new stories with server side events

10. Infinite Scroll: How to implement it. We use top sentinel and bottom sentinal, top padding and bottom padding. We change the window?? Why we need top and bottom padding and how we increase and decrease it

11. Optimization

CDN:
Image Optimization
Network Performance: How to do it?
Rendering Performance: How to do it?
JavaScript Performance: How to do it?

Bundle Splitting
feed, header, vendor, analytics scripts

12. Rendering Performance

13. Accessibility




















































