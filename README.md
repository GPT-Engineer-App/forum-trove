# forum-trove

Online forum similar to Hacker News (news.ycombinator.com), with a simple and clean interface, where people can post links or text posts, and other people can upvote, downvote and comment on. Reading is open to anonymous users, but users must register to post, upvote, downvote or comment. Use simple username+password authentication, mock it for now, any combination should work. 

The UI should use EJS view engine, Bootstrap for styling and plain vanilla JavaScript. Design should be simple and look like Hacker News, with a top bar for navigation, using a blue color scheme instead of the orange color in HN. The footer in each page should just be "Built using GPT Pilot".

Each story has a title (one-line text), a link (optional, URL to an external article being shared on AI News), and text (text to show in the post). Link and text are mutually exclusive - if the submitter tries to use both, show them an error.

Use the following algorithm to rank top stories, and comments within a story: "score = upvotes - downvotes + comments - sqrt(age)" , where "upvotes" and "downvotes" are the number of upvotes and downvotes the story or comment has, "comments" is the number of comments for a story (total), or the number of sub-comments (for a comment), and "age" is how old is the story, in minutes, and "sqrt" is the square root function.

Implement the following pages:

* / - shows the top 20 posted stories, ranked using the scoring algorithm, with a "More" link that shows the next 20 (pagination using "p" query parameter), and so on
* /newest - shows the latest 20 posted stories, ranked chronologically (newest first), with a "More" link that shows the next 20 (pagination using "p" query parameter), and so on
* /submit - shows a form to submit a new story, upon submitting the user should get redirected to /newest
* /login - shows a login form (username, password, "login" button, and a link to register page for new users)
* /register - shows a register form (username, password, "register" button, and a link to login page for existing users)
* /item - shows the story (use "id" query parameter to pass the story ID to this route)
* /comment - shows the form to send a comment  (just a textarea and "submit" button) - upon commenting, the person should get redirected to the story they commented on

The / and /newest pages should show the story title (link to the external article if "link" is set, otherwise link to the story item /item page), number of points (points = upvotes - downvotes), poster username (no link), how old is the story ("x minutes ago", "y hours ago" or "z days ago"), and "xyz comments" (link to /item page of the story). This is basically the same how HN shows it.

## Collaborate with GPT Engineer

This is a [gptengineer.app](https://gptengineer.app)-synced repository 🌟🤖

Changes made via gptengineer.app will be committed to this repo.

If you clone this repo and push changes, you will have them reflected in the GPT Engineer UI.

## Tech stack

This project is built with React and Chakra UI.

- Vite
- React
- Chakra UI

## Setup

```sh
git clone https://github.com/GPT-Engineer-App/forum-trove.git
cd forum-trove
npm i
```

```sh
npm run dev
```

This will run a dev server with auto reloading and an instant preview.

## Requirements

- Node.js & npm - [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating)
