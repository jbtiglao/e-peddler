# E-Peddler  🛍️ 🛒

Unit 13,  Object-Relational Mapping (ORM) E-Commerce Back End Assignment

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## Description 📌

The goal of this assignment is to understand the fundamental structure of e-commerce platforms. **E-commerce**, otherwise known as **internet retail**, is the largest sector of the electronics industry, generating an estimated $29 trillion in 2019. E-commerce platforms like Shopify and WooCommerce provide a suite of services to businesses of all sizes. 

With the manager of an internet retail company in mind as an end-user, this application was developed as a back end for an e-commerce website that uses the latest technologies and enables the user to compete with other e-commerce companies.

Using object-relational mapping (ORM), this e-commerce application has a back end starter code that is modified. Meanwhile, its working Express.js API is configured to use Sequelize as the ORM that interacts with the MySQL database, which in turn consists of tables for categories, products, tags, and product tags. RESTful API routes point to each standard Create, Read, Update, and Delete (CRUD) operation to make requests on the database.

This back end application has the following **appearance** when tested on Insomnia:
[image]

The **walk-through video** demonstrating the functionality of the application can be accessed through the following links:
* [Part 1, Installation and Database Creation](https://drive.google.com/file/d/1OMMFU6NjJRelQbXUzGeM6lnBEJTu4JGc/view?usp=sharing).
* [Part 2, Categories](https://drive.google.com/file/d/1yiFSZZa-rqInblx6gxC-S1woYE9JlzUp/view?usp=sharing)
* [Part 3, Products](https://drive.google.com/file/d/1K6LdPLvW9PLAHK71kVa-XOFGoSRkjffW/view?usp=sharing)
* [Part 4, Tags](https://drive.google.com/file/d/1AfgRf-PuhYt1AlOiq1Y--YQ8sghUT3Qh/view?usp=sharing)

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

  * To create your database:
      * Run `mysql -u root -p`. Enter your password when prompted.  
      
      * Enter `source db/schema.sql` on the terminal.

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


  3. When the user enters the command to invoke the application, the server is started and the Sequelize models are synced to the MySQL database.
  
  4. When the user opens API GET routes in Insomnia for categories, products, or tags, the data for each of these routes is displayed in a formatted JSON.

      * When the user clicks the GET request for all categories, products or tags, the user is presented with all the categories, products, or tags.

      * When the user clicks the GET request for a single category, product, or tag and the user enters the category, product, or tag id, the user is presented with the category, product, or tag bearing the said id.

  5. When the  user tests API POST, PUT, and DELETE routes in Insomnia, the user is able to successfully create, update, and delete a category, product, or tag in the database.

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
  
  Please see the walk-through demonstration videos as well as the sections on Description and Usage to see how the routes and data are created and tested using Insomnia. 
  
  1. The following GET routes are tested to return:
        * `GET All Categories` - all categories;
        * `GET All Products` - all products; and
        * `GET tags` - all tags.
  
  2. The following GET routes are tested to return:
        * `GET a Category by Id` - a single category;
        * `GET a Product by Id` - a single product; and
        * `GET a Tag by Id` - a single tag.

  3. These POST, PUT, and DELETE routes are tested to do the following:
        * `POST Create a Category` - create or add a new category;
        * `POST Create a Product` - create or add a new product;
        * `POST Create a Tag` - create or add a new tag;

        * `PUT Update a Category`- update a category; 
        * `PUT Update a Product` - update a product;
        * `PUT Update a Tag` - update a tag;

        * `DELETE a Category` - remove a category;
        * `DELETE a Product` = remove a product; and
        * `DELETE a Tag` - remove a tag.

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
  * [Screencastify](https://www.screencastify.com/)
 
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


