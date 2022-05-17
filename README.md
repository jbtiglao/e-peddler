# E-Peddler  🛍️ 🛒

Unit 13,  Object-Relational Mapping (ORM) E-Commerce Back End Assignment

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[This is a working draft - assignment not yet submitted]

## Description 📌

A command-line e-commerce application that utilizes object-relational mapping (ORM). The back end starter code is modified, and the working Express.js API is configured to use Sequelize to interact with a MySQL database.

The command-line application has the following **appearance**:
[image]

A **walk-through demonstration video** can be accessed [here](link).

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
  * Clone my repository on GitHub.

  * On Visual Studio Code:
      * Open the cloned file. 
      * Create your  `.gitignore` and `.env` files.
      * Check the dependencies and dev dependencies needed on `package.json`. 

  * [MySQL2](https://www.npmjs.com/package/mysql2) and [Sequelize](https://www.npmjs.com/package/sequelize) packages are needed to connect the Express.js API to a MySQL database, and the [dotenv](https://www.npmjs.com/package/dotenv) package to use environment variables to store sensitive data.
  
  * To set up all the existing npm packages, run `npm init`.

  * To install the dependencies on the `node_modules` folder, run `npm install` or

      * `npm i express` to install Express.js;
      * `npm i mysql2` to install MySQL2;
      * `npm i sequelize` to install Sequelize; 
      * `npm i nodemon` to install Nodemon; and
      * `npm i dotenv` to install dotenv.

  * Run `mysql -u root -p`. Enter your password when prompted.

  * Create your models and routes, and seed your database.
  
  * Use the `schema.sql` file in the `db` folder to create your database with MySQL shell commands. Use environment variables to store sensitive data like your MySQL username, password, and database name.

  * Your database should contain the following four models and requirements listed for each model:

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


  * Enter `npm run seed` to seed the database.
  
  * To invoke the application, run `npm start`. Your Sequelize models should sync to the MySQL database on server start.

  * To test the application, use Insomnia (please see the Test section).

  
  ---
  ## Usage 📌

With the manager of an internet retail company in mind as an end-user, this application was developed as a back end for an e-commerce website that uses the latest technologies, which enables the user to compete with other e-commerce companies.

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

  Insomnia is used to test the application's `GET`, `POST`, `PUT`, and `DELETE` routes.  Please see the walk-through demonstration videos as well as the sections on Description and Usage to see how the routes and data are tested using Insomnia. 
  
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
  
  * UCI Boot Camp study materials, videos, and other resources on Object-Relational Mapping (ORM)and MySQL.
  * [mySQL](https://dev.mysql.com/doc/)
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


