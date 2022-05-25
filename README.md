# E-Peddler  🛍️ 🛒

Unit 13,  Object-Relational Mapping (ORM) E-Commerce Back End Assignment

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[This is a working draft - assignment not yet submitted]

## Description 📌

The goal of this assignment is to understand the fundamental structure of e-commerce platforms. **E-commerce**, otherwise known as **internet retail**, is the largest sector of the electronics industry, generating an estimated $29 trillion in 2019. E-commerce platforms like Shopify and WooCommerce provide a suite of services to businesses of all sizes. 

With the manager of an internet retail company in mind as an end-user, this application was developed as a back end for an e-commerce website that uses the latest technologies and enables the user to compete with other e-commerce companies.

Using object-relational mapping (ORM), this command-line e-commerce application has a back end starter code that is modified. Meanwhile, its working Express.js API is configured to use Sequelize as the ORM that interacts with the MySQL database. The MySQL database consists of tables for categories, products, tags, and product tags. RESTful API routes point to each standard Create, Read, Update, and Delete (CRUD) operation to make requests on the database.

The command-line application has the following **appearance**:
[image]

To show the features and functionalities of the application, a **walk-through demonstration video** can be accessed [here](link).

To access the **application files**, please see my [Github Repository](https://github.com/jbtiglao/e-peddler).

---

## Table of Contents 📌
  1. [Title](#title)
  2. [Description](#description)
  3. [Installation](#installation)
  4. [Usage](#usage)
  5. [Technologies](#technologies)
  6. [License](#license)
  7. [Contributing](#contributing)
  8. [Tests](#tests)
  9. [Credits](#credits)
  10. [Author](#author)
  11. [Questions](#questions)
  
  ---
## Installation 📌
  * Clone my [repository](https://github.com/jbtiglao/e-peddler) on GitHub.

  * On Visual Studio Code:
      * Open the cloned file. 
      * Create your  `.gitignore` and `.env` files.
      * Check the `dependencies` and `dev dependencies` needed on `package.json`. 

  * Required dependencies
      * [MySQL2](https://www.npmjs.com/package/mysql2) and [Sequelize](https://www.npmjs.com/package/sequelize) packages are needed to connect the [Express.js](https://expressjs.com/) [API](https://expressjs.com/en/5x/api.html) to a MySQL database.
  
      *  The [dotenv](https://www.npmjs.com/package/dotenv) package's environment variables are used to store sensitive data like your MySQL username, password, and database name.

  * To set up all the existing npm packages, run `npm init`.

  * To install the dependencies on the `node_modules` folder, run `npm install` or

      * `npm i express` to install Express.js;
      * `npm i mysql2` to install MySQL2;
      * `npm i sequelize` to install Sequelize; 
      * `npm i nodemon` to install Nodemon; and
      * `npm i dotenv` to install dotenv.

  * To create your database, run `mysql -u root -p`. Enter your password when prompted.  

  * Use the `schema.sql` file in the `db` folder to create your database with the MySQL shell commands. 
  
      * To create the tables, enter the following:
    ```
    DROP DATABASE IF EXISTS ecommerce_db;

    CREATE DATABASE ecommerce_db;
    ```

      * Or type `source db/schema.sql` on the terminal.

  * To seed the database, enter `npm run seed`.

  * Use MySQL Workbench to confirm if the tables have been created and the database has been seeded.

      * On MySQL Workbench, click the connection for the application.

      * Click Schemas then the application's database name, `ecommerce_db`. 

      * Click the tables.
  
  * To invoke the application, run `npm start`. The Sequelize models sync to the MySQL database on server start.

  * To test the application, use Insomnia (please see the Test section).
  
  ---
## Usage 📌

For instructions on how to use the application, please see the demonstration video, as well as the description and the features and functionalities sections.

### Features and Functionalities  🔌

  1. Given a functional Express.js API, when the user adds his/her database name, MySQL username, and MySQL password to an environment variable file, the user is able to connect to a database using Sequelize.

  2. When the user enters the schema and seed commands, a development database is created and is seeded with test data.

  3. When the user enters the command to invoke the application, the server is started and the Sequelize models are synced to the MySQL database.

  4. When the user opens API GET routes in Insomnia for categories, products, or tags, the data for each of these routes is displayed in a formatted JSON.

  5. When the  user tests API POST, PUT, and DELETE routes in Insomnia, the user is able to successfully create, update, and delete data in the database.

--- 
## Technologies 📌
  * JavaScript
  * MySQL/MySQL2
  * Sequelize
  * Node.js
  * Nodemon
  * Express.js
  * Insomnia

  ---
 ## License 📌
  License used for this project - MIT
  
  For more information on the above license, please see the [Open Source Initiative](https://opensource.org/licenses).


  ---
## Contributing 📌
  To contribute to this application, please email the author for guidelines.

  ---
## Tests 📌

  The following procedures are performed to develop and test the application and its functionalities:

### Starter Code 

 The API Routes to Perform RESTful CRUD Operations are filled out. This includes the unfinished routes in `product-routes.js`, `tag-routes.js`, and `category-routes.js` to perform create, read, update, and delete operations using Sequelize models.

 ### Creating the database
Models and routes are created. 

The `schema.sql` file in the `db` folder is run to create the database with the MySQL shell commands.

### Seeding the Database

After creating the models and routes, `npm run seed` is invoked to seed data so the routes can be tested.

The database contains the following four models and requirements listed for each model:

* `Category`

    * `id`

    * `category_name`

* `Product`

    * `id`

    * `product_name`

    * `price`

    * `stock`

    * `category_id`

* `Tag`

    * `id`

    * `tag_name`

* `ProductTag`

    * `id`

    * `product_id`

    * `tag_id`

MySQL Workbench is used to confirm the tables have been created and the database seeded.

### Sync Sequelize to the Database on Server Start

The code needed in `server.js` to sync the Sequelize models to the MySQL database on server start is created.

### Associations
  
  1. Association methods on the Sequelize models are executed to create the following relationships between them:

        * `Product` belongs to `Category`, and `Category` has many `Product` models, as a category can have multiple products but a product can only belong to one category.

        * `Product` belongs to many `Tag` models, and `Tag` belongs to many `Product` models. Allow products to have multiple tags and tags to have many products by using the `ProductTag` through model.

  2. Foreign key relationships that match the column created in the respective models are set up.

### Insomnia and Testing RESTful API Routes

  Insomnia is used to test the application's `GET`, `POST`, `PUT`, and `DELETE` routes.  
  
  Please see the walk-through demonstration videos as well as the sections on Description and Usage to see how the routes and data area created and tested using Insomnia. 
  
  1. The following GET routes are tested to return:
        * `GET Categories` - all categories;
        * `GET All Products` - all products; and
        * `GET tags` - all tags.
  
  2. The following GET routes are tested to return:
        * `GET Category by ID` - a single category;
        * `GET One Product` - a single product; and
        * `GET tag by id` - a single tag.

  3. These routes are tested to do the following:
        * `POST` - `CREATE Category`;
        * `PUT` - `UPDATE Category`; and
        * `DELETE` - `DELETE Category`.
        
  4. `POST`, `PUT`, and `DELETE` routes for products and tags are also tested.

  ---
  ## Credits 📌
  The following applications and resources were consulted and/or utilized in the development of this application:
  
  * UCI Boot Camp study materials, videos, and other resources on Object-Relational Mapping (ORM) and MySQL.
  * [MySQL](https://dev.mysql.com/doc/)
  * [Sequelize](https://sequelize.org/docs/v6/category/core-concepts/)
  * [MySQL Workbench](https://www.mysql.com/products/workbench/)
  * [Codecademy](https://www.codecademy.com/article/what-is-crud) for the information on CRUD.
  * [npmjs.com](https://npmjs.com) packages and documentation on MySQL2, Sequelize, Nodemon, Express.js, and dotenv.
  * [Insomnia](https://insomnia.rest/)
 
  ---
  ## Author 📌
  Jane Tiglao

  ---
  ## Questions 📌 
  For questions or issues, please contact: 
  - Jane Tiglao 
  - Email: janeytiglao@gmail.com
  - GitHub Username: jbtiglao
  - GitHub Profile: https://github.com/jbtiglao


