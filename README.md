# WriteNode

WriteNode is a simple blogging app. Read posts on the home page, sign in with Google to publish a post, or delete a post you wrote. Firebase Authentication handles sign-in, and Cloud Firestore stores the posts.

## Run locally

Use Node.js **26.13.1**. The app uses React and React DOM **19.3.1** and the Firebase JavaScript SDK **13.4.0**.

1. Register a web app in your Firebase project. Enable Google sign-in, add `localhost` to Authentication’s authorized domains, and create a Cloud Firestore database. [Firebase web setup](https://firebase.google.com/docs/web/setup)
2. Create a `.env.local` file in the project folder and fill in the values from your Firebase web app configuration.

   ```dotenv
   REACT_APP_API_KEY=your_api_key
   REACT_APP_AUTH_DOMAIN=your_auth_domain
   REACT_APP_PROJECT_ID=your_project_id
   REACT_APP_STORAGE_BUCKET=your_storage_bucket
   REACT_APP_MESSAGING_SENDER_ID=your_messaging_sender_id
   REACT_APP_APP_ID=your_app_id
   ```

3. Configure Firestore rules for the `posts` collection. The home page reads posts before sign-in. Allow signed-in users to create posts under their own user ID and delete only their own posts. WriteNode stores the author’s user ID in `author.id`. [Firestore security rules](https://firebase.google.com/docs/firestore/security/get-started)
4. From the project folder, install the locked dependencies and start the app.

   ```sh
   npm ci
   npm start
   ```

Open [localhost:3000](http://localhost:3000). Run `npm run build` to create a production build in `build/`.
