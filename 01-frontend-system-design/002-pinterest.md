1. General Requirements
2. Functional Requirements
3. Component Architecture
4. Mansory Layout
5. Data Entities
6. Data API
7. Data store and Layers
8. Optimization
9. Accessibility


1. General Requirements
-> Pin Should be placed in the form of mansory layout
-> User can see full details details of the pin
-> Pin can be gif or picture, we don't have video stuff
-> User can post the comments
-> User can share the pin

2. Functaional Requirements
-> We do not support IE 11+ 
-> We support 95% of browsers
-> We support wide range of devices (Mobile, Desktops etc...)
-> We support offline mode
-> We want the app to work even in a short network bandwidth

3. Component Architecture
-> Pin: If we hover over it we see the link, share, menu and if we click on the pin we can see the complete detail of the pin with picture, details, comments.
-> Comments: It is a comment list, with a button of shore more so that we can see more comments and we also have an input box to publish new comment.

4. Schema of Application
Application -> Router -> PinsFeedPage -> Pins Grid -> Pin
Pin Component: Pin -> PinControls -> Pin Menu -> Pin Picture
Pin Detail Component: Pin Detail -> PinComments -> Pin Details -> Pin Picture

5. Mansory Layout
Visible Zone, content height, recycle zone, top sentinenl, and botton sentinel, when we reach botton sentinel we replace the top most pins and load new pin below and make them visible.

How translateY properties comes into play and how does it work in this case?

6. Data Entities
type Pin = {
  id: string;
  origin: PinBoard;
  description: string;
  title: string;
  imageUrl: string;
  author: User
}

type Pin = {
  id: string;
  content: string;
  author: User
}

type User = {
  id: string;
  nickname: string;
}

7. Data API

getPins(api_key, user_id, includeComments, cursor, minID)
getComments(api_key, pin_id, page)

8. Data Layers and store 

How we store data and how do we fetch data and how the data flow and then how the data get's displayed on the screen?

9. Performance
-> Network Performance: Image Optimization, Lazy Loading
-> Rendering Performance: Inlin critical css and js, link rel = preconnect, load analytics on page load, css-naming
-> JavaScript Performance: Do less stuff, cache heavy work, do stuff async, web workers, service workers

10. Accessibility
-> keyboard navigation: adding pin, go to top, got to bottom, share the pin, like the pin, quick access help
-> Different color theming
-> announce live fields with aria-live
-> Use rems instead of pixels
