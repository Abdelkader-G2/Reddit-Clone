# Reddit Clone

A full-stack Reddit clone application built with Next.js and Prisma, using MySQL as the database. This app features user authentication, subreddit creation, post and comment functionality, and voting (upvote/downvote) similar to Reddit.

## Features

- **User Authentication**: Secure sign-up and login using OAuth providers.
- **Subreddits**: Users can create and subscribe to subreddits.
- **Posts and Comments**: Users can create posts within subreddits and comment on posts.
- **Voting System**: Upvote and downvote functionality for posts and comments.
- **Responsive Design**: Built with Tailwind CSS for a responsive and modern UI.

## Technologies Used

- **Next.js** - A React-based framework for server-side rendering.
- **Prisma** - ORM for interacting with a MySQL database.
- **MySQL** - Database for storing user, post, and subreddit data.
- **NextAuth.js** - For secure authentication with OAuth providers.
- **Tailwind CSS** - CSS framework for styling.
- **Vercel** - Deployment for the Next.js app.

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (version 14 or later)
- [MySQL](https://dev.mysql.com/downloads/mysql/) (or a compatible relational database)
- Optional: [Prisma CLI](https://www.prisma.io/docs/getting-started/setup-prisma/start-from-scratch-prisma-migrate)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/reddit-clone.git
   cd reddit-clone
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Set up environment variables:**
   - Create a `.env` file in the root directory and add the following variables:
     ```plaintext
     DATABASE_URL="mysql://USER:PASSWORD@localhost:3306/your-database-name"
     NEXTAUTH_SECRET="your_secret_key"
     NEXTAUTH_URL="http://localhost:3000"
     ```

4. **Set up the database:**
   - Use Prisma to migrate your database schema:
     ```bash
     npx prisma migrate dev --name init
     ```

5. **Seed the database (optional):**
   - If you have a `prisma/seed.js` file, you can seed the database with initial data:
     ```bash
     npx prisma db seed
     ```

6. **Run the development server:**
   ```bash
   npm run dev
   ```

   Open [http://localhost:3000](http://localhost:3000) to view the app in your browser.

### Environment Configuration

Ensure the following environment variables are set in `.env`:

- `DATABASE_URL`: Connection string for MySQL.
- `NEXTAUTH_SECRET`: A unique secret key for NextAuth.js.
- `NEXTAUTH_URL`: The base URL of your app (e.g., `http://localhost:3000` for local development).

### Prisma Schema Overview

This app uses a relational database schema defined in Prisma with models like:

- **User**: Represents registered users.
- **Account**: Stores user OAuth account details.
- **Session**: Manages user sessions.
- **Subreddit**: Represents individual subreddits (or communities).
- **Post**: Stores post content within subreddits.
- **Comment**: Represents user comments on posts.
- **Vote** and **CommentVote**: Manages upvotes and downvotes on posts and comments.

### API Routes

This application uses Next.js API routes for backend functionality. Here are some key API routes:

| HTTP Method | Endpoint                  | Description                            |
|-------------|---------------------------|----------------------------------------|
| `POST`      | `/api/auth/signin`        | Authenticate users                     |
| `POST`      | `/api/auth/signup`        | Register a new user                    |
| `GET`       | `/api/subreddits`         | Retrieve a list of subreddits          |
| `POST`      | `/api/subreddits`         | Create a new subreddit                 |
| `GET`       | `/api/subreddits/[id]`    | Get details of a specific subreddit    |
| `POST`      | `/api/posts`              | Create a new post                      |
| `GET`       | `/api/posts/[id]`         | Get details of a specific post         |
| `POST`      | `/api/posts/[id]/vote`    | Upvote or downvote a post              |
| `POST`      | `/api/comments`           | Add a comment to a post                |
| `POST`      | `/api/comments/[id]/vote` | Upvote or downvote a comment           |

### Running Tests

To run tests, use the following command:

```bash
npm test
```

For continuous testing:

```bash
npm run test:watch
```

## Deployment

To deploy this app on Vercel:

1. **Push your code to GitHub**.
2. **Link the repository to Vercel** in the Vercel dashboard.
3. **Set environment variables** in the Vercel settings for the project.
4. Deploy the project, and Vercel will handle the build and hosting.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request for any new features or bug fixes.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a pull request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.



### Explanation

- **Project Overview**: Explains the main functionality of the Reddit clone app.
- **Installation**: Steps to set up the development environment, including database configuration and schema migration.
- **Environment Configuration**: Details on required environment variables for local and production environments.
- **API Routes**: Lists core API routes related to subreddits, posts, and comments.
- **Prisma Schema Overview**: Provides a brief description of the main models used in the database schema.
- **Deployment**: Instructions for deploying the app to Vercel. 

Feel free to adjust the descriptions and links as per your specific project setup!