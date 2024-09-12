# MERN GraphQL Expense Tracker App

![Demo App](https://i.ibb.co/WHyMscm/Screenshot-42.png)

[Watch the Video Tutorial on YouTube](https://youtu.be/Vr-QHtbmd38)

Welcome to the **MERN GraphQL Expense Tracker App**! This project, inspired by [Burak Orkmez’s GraphQL Crash Course](https://www.youtube.com/watch?v=Vr-QHtbmd38), is designed to help you manage your expenses efficiently using a modern tech stack and GraphQL.

## Features

- 🌟 **Tech Stack**: MERN (MongoDB, Express.js, React.js, Node.js) + [Apollo GraphQL](https://www.apollographql.com/docs/apollo-server/)
- 📜 **GraphQL Schema & Resolvers**: Learn how to define type definitions and build resolvers for efficient data fetching.
- 🔄 **GraphQL Mutations**: Modify data with powerful mutations and establish relationships in the graph.
- 🔐 **Authentication**: Implement secure user authentication using [Passport.js](https://www.passportjs.org/) and MongoDB for session management.
- 📝 **Transaction Management**: Perform CRUD operations for transactions, and use `categoryStatistics` to analyze data.
- 🎨 **Frontend Styling**: Tailwind CSS and [Exterity UI](https://ui.aceternity.com/) for a polished and responsive user interface.
- 📊 **Data Visualization**: Create stunning charts with [Chart.js](https://www.chartjs.org/) and integrate with React using [react-chartjs-2](https://www.npmjs.com/package/react-chartjs-2).
- 🚀 **Deployment**: Deploy effortlessly using [Render](https://render.com) with Cron jobs for server maintenance.
- 🐞 **Error Handling**: Handle errors effectively on both the server and client side.
- ⏳ **Cache Management**: Clear Apollo client cache on logout to prevent data leakage.

## Setup Instructions

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-repo/expense-tracker-app
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. Set up the environment variables:Create a `.env` file in the root directory and add the following:

   ```bash
   MONGO_URI=your_mongo_connection_string
   SESSION_SECRET=your_session_secret
   ```

4. **Build the app:**

   ```bash
   npm run build
   ```

5. **Start the app:**

   ```bash
   npm start
   ```

## Key Insights

### Why this Project Uses the MERN + Apollo GraphQL + Passport.js Stack

The **MERN + Apollo GraphQL + Passport.js** stack offers several key advantages over the traditional **MERN + REST** approach:

1. **Efficient Data Fetching**:

   - **GraphQL** allows clients to request exactly the data they need, reducing the amount of unnecessary data transfer. In a traditional **REST API**, responses often include extra data that isn’t needed, which can be inefficient, especially on slower networks or mobile devices.
   - With **GraphQL**, you can also fetch related data in a single query, eliminating the need for multiple round-trip requests to different endpoints (common in REST).

2. **Better Control Over API Evolution**:

   - In **REST APIs**, any modification or addition to the structure often requires changes to existing endpoints or adding new ones, which may break compatibility with older clients.
   - **GraphQL**, on the other hand, supports evolving APIs without breaking existing clients. Clients can continue requesting the fields they need, even as the API evolves with new fields.

3. **Strongly Typed Schema**:

   - **GraphQL** has a strongly typed schema that clearly defines the structure of data, making it easier to understand, test, and document APIs. This also enables excellent development tools like autocompletion and validation.
   - In contrast, **REST** often lacks formal schema definitions, making it harder to predict or enforce the shape of responses.

4. **Performance Optimization**:

   - With **GraphQL**, you can implement **batching** and **caching** techniques to reduce the load on your database, ensuring that repeated queries fetch cached data instead of querying the database every time.
   - **REST APIs** typically require more custom work to achieve similar levels of optimization.

5. **Global State Management**:

   - Using **Apollo Client** integrates seamlessly with **React**, allowing you to manage global state, caching, and data fetching out of the box. REST approaches often require separate state management libraries like Redux or context-based management, which can add complexity.

6. **Authentication**:

   - **Passport.js** is a widely used middleware for **authentication** and works smoothly with both REST and GraphQL, ensuring secure sign-ups and logins.

### How to Transition from MERN + REST to MERN + GraphQL with Best Practices

For a beginner familiar with **MERN + REST**, transitioning to **GraphQL** while keeping the time cost low and following best practices involves the following steps:

#### 1. **Understand the Core Differences**:

- **Queries vs. Endpoints**: In REST, you have specific endpoints for each resource, while in GraphQL, you define queries to request specific data.
- **Mutations vs. POST Requests**: In GraphQL, mutations handle the modification of data, similar to POST requests in REST.

#### 2. **Libraries and Tools to Master**:

- **Apollo Client & Apollo Server**:
  - [Apollo Client Documentation](https://www.apollographql.com/docs/react/) – Essential for integrating GraphQL with your React app.
  - [Apollo Server Documentation](https://www.apollographql.com/docs/apollo-server/) – Used to set up the GraphQL API on the server side.
- **GraphQL Playground**:
  - [GraphQL Playground](https://github.com/graphql/graphql-playground) – A great tool for testing GraphQL queries and mutations.
- **Mongoose with GraphQL**:
  - [Mongoose and GraphQL Example](https://github.com/the-road-to-graphql/fullstack-apollo-express-mongodb-boilerplate) – This project shows how to integrate MongoDB and Mongoose with Apollo Server.
- **Error Handling**: Use Apollo’s error handling mechanisms to catch and display meaningful errors to users.
  - [Error Handling in Apollo](https://www.apollographql.com/docs/react/data/error-handling/)

#### 3. **Follow Best Practices**:

- **Define a Clear Schema**:
  - Your GraphQL schema should be well-structured and clearly define the relationships between different types of data.
- **Modular Resolvers**:
  - Keep your resolver logic modular and separate, which improves maintainability and testing.
- **Use Caching**:
  - Apollo Client comes with caching out of the box, which improves performance significantly. Make sure you configure and use it correctly.
  - [Apollo Caching](https://www.apollographql.com/docs/react/caching/cache-configuration/)
- **Security**: Implementing authentication with **JWT** (JSON Web Tokens) or **OAuth** with Passport.js is essential for secure API usage.
  - [Passport.js with GraphQL Example](https://github.com/mrdulin/graphql-authentication)
- **Pagination**:
  - Handling pagination in GraphQL is slightly different than in REST. You'll typically use "cursor-based" pagination for efficiency.
  - [GraphQL Pagination Guide](https://graphql.org/learn/pagination/)

#### 4. **Reference Projects**:

- **Fullstack Apollo + MongoDB Boilerplate**:
  - [Fullstack Apollo + MongoDB Example](https://github.com/the-road-to-graphql/fullstack-apollo-express-mongodb-boilerplate) – A complete MERN GraphQL project to learn from.
- **Apollo React GraphQL Starter Kit**:
  - [Apollo React GraphQL Starter Kit](https://github.com/graphql-boilerplates/react-fullstack-graphql) – This project showcases best practices for setting up a React and GraphQL environment.

### Passport.js vs. JWT

- **Passport.js with Session-based Authentication**: Suitable for smaller apps where session data is stored on the server. It requires session persistence (e.g., Redis) in distributed systems, making it less ideal for scalability.
- **JWT (JSON Web Tokens)**: Stateless and better suited for API-based or mobile apps. It scales easily in distributed environments without needing a session store, making it the preferred choice for modern web apps and microservices.

## Course Highlights

This project follows the structure outlined in the **GraphQL Crash Course 2024** by Burak Orkmez:

- 🗄️ **MongoDB Setup**: Securely connect to MongoDB and update credentials using environment variables.
- 🔄 **Modular Resolvers**: Improve maintainability with well-structured **GraphQL** resolvers for queries and mutations.
- 📊 **Data Analysis**: Integrate category statistics to provide insights for users on transaction patterns.
- 🚪 **User Session Management**: Implement robust session handling with [Passport.js](https://www.passportjs.org/) and custom refetch logic post-login.
- 📈 **Transaction Management**: Create resolvers for CRUD operations and integrate data visualization using [Chart.js](https://www.chartjs.org/) and [react-chartjs-2](https://react-chartjs-2-two.vercel.app/).
- 🎨 **UI Design**: Build a user-friendly interface using Tailwind CSS and [Exterity UI](https://ui.aceternity.com/). Use [Iran Liara Avatar Service](https://avatar.iran.liara.run/public/) for dynamic user avatars.
- 🚀 **Deployment & Cron Jobs**: Deploy the app using [Render](https://render.com), with added **Cron** jobs to ensure the app stays live.

## Acknowledgements

I would like to extend my heartfelt thanks to [Burak Orkmez](https://github.com/burakorkmez) for his amazing **GraphQL Crash Course in 2024** on YouTube. His comprehensive and insightful tutorial on building a full-stack MERN application with GraphQL provided invaluable guidance throughout my learning journey. You can check out the course [here](https://www.youtube.com/watch?v=Vr-QHtbmd38).

This project was inspired and developed based on the lessons shared in his tutorial, and I highly recommend others to follow his work for a deeper understanding of full-stack development.
