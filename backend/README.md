# MERN Starter Backend

Welcome to this MERN boilerplate repo's backend. The backend is centered around the MVC (model-view-controller) design pattner, intended to decouple code and reduce potential errors with the system.

The backend also comes preconfigured with a jest test suite that will execute on PR creation.

## Getting Started

Start off by copying `.envtemplate` and renaming the copy to `.env`. Configure the node env and mongo dev/prod URI's based on your current environment and secrets.

Now, run `yarn install` to install all dependencies. Once that finishes, you're all set to run the backend!

Simply use `yarn dev` to begin running the dev server locally, or `yarn build` to create a production build that can be run using `yarn start`

Use `yarn test` to run the jest test suite (will automatically run on PR creation).

## MVC Design Pattern

This backend is centered around the Model-View-Controller design pattern, meaning that each "entity" of your application should have its own folder where necessary models, views, and controllers are specified.

The breakdown of these three types of functions/files is as follows:
Models -- classes that define our DB schema and structure of our data
Controllers -- functions that interact with the models to modify specific attributes/pieces of data
Views -- routes that the user can interact with which make use of controllers to perform a specific action.

Structuring our code in this way decouples the system by introducing modularity. It ensures that we rarely encounter breaking changes and that we have a clean separation of duties for progrmamers. Moreover, it allows us to enforce a predicable design pattern that speeds up onboarding and development on a team.

## Database Structure

This backend makes use of MongoDB, a NoSQL database that heavily emphasizes data nesting as opposed to data references. An examples of this can be seen in `customers/models.ts` with the Customer and Job classes. To read more about this, check out <a href="https://www.mongodb.com/docs/manual/core/data-modeling-introduction/">this page</a> on the MongoDB website about various schema structures.

Generally speaking, embedding documents yields far speedier responses from MongoDB as opposed to traditional id references as used in SQL databases. Therefore, when creating new models it is important to continue nested data across various collections and documents.