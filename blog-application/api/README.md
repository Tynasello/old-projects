A Node.js API constructed in RESTful manner, supporting CRUD commands to a MongoDB database.

JWTs and the bcrypt library were used to authenticate users, allowing login functionality and access to protected routes.

API supports frontend blog with admin-only features, including creating, deleting, and editing posts, as well as deleting comments.

API deployed with Heroku: [https://tynasello-blog-api.herokuapp.com](https://tynasello-blog-api.herokuapp.com).

### Built With

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT
- Heroku

### API Routes

Routes can be accessed through the following URI: 'https://tynasello-blog-api.herokuapp.com/blog/'

An asterisk (\*) before method types signifies protected routes. **x-access-token** must be passed in the request header to access these routes

#### Auth

| Method | URI      | Description              |
| ------ | -------- | ------------------------ |
| POST   | /sign-up | Sign up                  |
| POST   | /log-in  | Log in                   |
| DELETE | /logout  | Log out                  |
| \*GET  | /user    | Currently logged in user |

#### Posts

| Method   | URI        | Description       |
| -------- | ---------- | ----------------- |
| GET      | /posts     | All posts         |
| GET      | /posts/:id | Single post by id |
| \*POST   | /posts     | Create post       |
| \*DELETE | /posts/:id | Delete post by id |
| \*PATCH  | /posts/:id | Edit post by id   |

#### Comments

| Method   | URI                                 | Description              |
| -------- | ----------------------------------- | ------------------------ |
| GET      | /posts/:postid/comment              | All post comments        |
| GET      | /posts/:postid/comments/:commentid  | Single comment by id     |
| POST     | /posts/:postid/comments             | Create comment           |
| \*DELETE | //posts/:postid/comments/:commentid | Delete comment by id     |
| \*DELETE | /posts/:postid/comments             | Delete all post comments |
| \*PATCH  | /posts/:postid/comments/:commentid  | Edit comment by id       |


### Example Route Requests

```bash
const req = await fetch(
    `https://tynasello-blog-api.herokuapp.com/blog/log-in`,
    {
        method: "POST",
        headers: {
        "Content-Type": "application/json",
        },
        body: JSON.stringify({ username, password }),
    }
);
const result = await req.json();
localStorage.setItem("token", result.token);
```

```bash
await fetch(`https://tynasello-blog-api.herokuapp.com/blog/posts/`, {
    method: "POST",
    headers: {
        "Content-Type": "application/json",
        "x-access-token": localStorage.getItem("token") || " ",
    },
    body: JSON.stringify({
        title: newTitle,
        author_name: newAuthor,
        text: newText,
    }),
});
```

---

Acknowledgments

Inspiration for this project was found while following the tutorials on [The Odin Project](https://www.theodinproject.com), and advancing to the [NodeJS Project: Blog API](https:/$$/www.theodinproject.com/paths/full-stack-javascript/courses/nodejs/lessons/blog-api) section.
