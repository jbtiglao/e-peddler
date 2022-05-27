# E-Peddler  🛍️ 🛒

Unit 13,  Object-Relational Mapping (ORM) E-Commerce Back End Assignment

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## Description 📌

The goal of this assignment is to understand the fundamental structure of e-commerce platforms. **E-commerce**, otherwise known as **internet retail**, is the largest sector of the electronics industry, generating an estimated $29 trillion in 2019. E-commerce platforms like Shopify and WooCommerce provide a suite of services to businesses of all sizes. 

With the manager of an internet retail company in mind as an end-user, this application was developed as a back end for an e-commerce website that uses the latest technologies and enables the user to compete with other e-commerce companies.

Using object-relational mapping (ORM), this e-commerce application has a back end starter code that is modified. Meanwhile, its working Express.js API is configured to use Sequelize as the ORM that interacts with the MySQL database, which in turn consists of tables for categories, products, tags, and product tags. RESTful API routes point to each standard Create, Read, Update, and Delete (CRUD) operation to make requests on the database.

This back end application has the following **appearance** when tested on Insomnia:


<img width="1415" alt="image1_appearance" src="https://user-images.githubusercontent.com/94569484/170664146-468a698a-0f4b-449d-a9b9-cb6296ec8e28.png">


To see how the functionalities of the application work using Insomnia, access the **walk-through videos** here:
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

### Pre-Installation and Coding Requirements 🔌

**Starter Code**

 The API Routes to Perform RESTful CRUD Operations are filled out. This includes the unfinished routes in `product-routes.js`, `tag-routes.js`, and `category-routes.js` to perform create, read, update, and delete operations using Sequelize models.

**Creating and Seeding the Database**
Models and routes are created. 

The `schema.sql` file in the `db` folder is run to create the database with the MySQL shell commands.

After creating the models and routes, `npm run seed` is invoked to seed data so the routes can be tested.

MySQL Workbench is used to confirm the tables have been created and the database seeded.

**Sync Sequelize to the Database on Server Start**

The code needed in `server.js` to sync the Sequelize models to the MySQL database on server start is created.

**Associations**
  
  1. Association methods on the Sequelize models are executed to create the following relationships between them:

        * `Product` belongs to `Category`, and `Category` has many `Product` models, as a category can have multiple products but a product can only belong to one category.

        * `Product` belongs to many `Tag` models, and `Tag` belongs to many `Product` models. Allow products to have multiple tags and tags to have many products by using the `ProductTag` through model.

  2. Foreign key relationships that match the column created in the respective models are set up.

### Installation Instructions 🔌
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

      * Click the tables. The following models and their requirements should be displayed:


<img width="1203" alt="image14_workbench-category" src="https://user-images.githubusercontent.com/94569484/170675098-2f6f94be-44b0-40f0-91fa-d0c77cf9fece.png">

<img width="1201" alt="image15_workbench-product" src="https://user-images.githubusercontent.com/94569484/170675119-d2b443d7-653f-4fd5-8fa5-8fed4574d166.png">

  <img width="1202" alt="image17_workbencg-tag" src="https://user-images.githubusercontent.com/94569484/170675128-5ea0a2c2-d99e-4761-8a42-11d5a99e4927.png">
  
  <img width="1208" alt="image16_workbench-product-tag" src="https://user-images.githubusercontent.com/94569484/170675159-a3b84ae2-1778-434f-aa19-0ba82d33f313.png">


  * To invoke the application, run `npm start`. The Sequelize models sync to the MySQL database on server start.

  * To test the application, use Insomnia (please see the Test section).
  
  ---
## Usage 📌

For instructions on how to use the application, please see the demonstration video, as well as the Description and the Features and Functionalities sections.

### Features and Functionalities  🔌

  1. Given a functional Express.js API, when the user adds his/her database name, MySQL username, and MySQL password to an environment variable file, the user is able to connect to a database using Sequelize.

![image2_schema](https://user-images.githubusercontent.com/94569484/170664661-fc029c06-1317-4f93-84ab-a1dc7f6c376e.png)


  2. When the user enters the schema and seed commands, a development database is created and is seeded with test data. 

![image3_schema2](https://user-images.githubusercontent.com/94569484/170665173-9cece363-e0b7-4eca-9b85-a01e1b87db1b.png)

  
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


![image4_seed](https://user-images.githubusercontent.com/94569484/170665087-7daef03f-ec63-44b0-8191-81c3ea0e9f94.png)


  3. When the user enters the command to invoke the application, the server is started and the Sequelize models are synced to the MySQL database.

![image5_server-started](https://user-images.githubusercontent.com/94569484/170665395-7c1539d7-62bd-4f83-a90d-1ee7abe25809.png)

  
  4. When the user opens API GET routes in Insomnia for categories, products, or tags, the data for each of these routes is displayed in a formatted JSON.

  * When the user clicks the GET request for **all** categories, products or tags, the user is presented with all the categories, products, or tags.

<img width="1395" alt="image6_get-all-products" src="https://user-images.githubusercontent.com/94569484/170665800-557c77b8-547d-43da-b6d2-f3da72c3a4ce.png">

  * When the user clicks the GET request for a **single** category, product, or tag and the user enters the category, product, or tag id, the user is presented with the category, product, or tag bearing the said id.
      
  <img width="1400" alt="image7_get-category-by-id" src="https://user-images.githubusercontent.com/94569484/170665846-8187d2e4-a029-425b-9bb3-9f543a3fa3d6.png">


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

  [Insomnia](https://insomnia.rest/) is used to test the application's RESTful API routes.
  
  Please see the walk-through demonstration videos as well as the sections on Description and Usage to see how the `GET`, `POST`, `PUT`, and `DELETE` routes and relevant data are created and tested using Insomnia. 
  
  1. Routes for **`CATEGORIES`**, **`PRODUCTS`**, and **`TAGS`** are created to request category, product, and tag information from the database.

<img width="1391" alt="image18_routes" src="https://user-images.githubusercontent.com/94569484/170666446-b311deb1-a4c7-474c-a3bc-10cfe422d210.png">

  
  2. **`GET` Request** - there are two kinds of `GET` requests:
 
  * The `GET All` request allows a user to get all categories, products, and tags from the database. 
    
    On Insomnia, the following `Get All` requests are created and tested to return:
  
  * `GET All Categories` - all categories;
        
  <img width="1402" alt="image19_get-all-categories" src="https://user-images.githubusercontent.com/94569484/170667004-efc7ac32-77f2-43c4-b64c-6e70b4235ab5.png">

        
  * `GET All Products` - all products; and
        
  <img width="1395" alt="image21_get-all-products" src="https://user-images.githubusercontent.com/94569484/170667389-70c32672-c8f3-4440-b3cc-f9db54d4166b.png">

  * `GET tags` - all tags.
        
  <img width="1397" alt="image22_get-all-tags" src="https://user-images.githubusercontent.com/94569484/170667543-7bd4433d-8ba4-4d9e-9c85-8edb943db13b.png">

  
  * The `Get By ID` request allows a user to get a single category, product, or tag by id. The following `GET By Id` requests are created and tested to return:
    
  * `GET a Category by Id` - a single category;
        
  <img width="1401" alt="image20_get-category-by-id" src="https://user-images.githubusercontent.com/94569484/170667245-a721ea10-14ac-4aa1-9ab2-801ca80d053f.png">

        
  * `GET a Product by Id` - a single product; and
        
  <img width="1397" alt="image23_get-product-by-id" src="https://user-images.githubusercontent.com/94569484/170667708-f478fbd5-0b64-44d8-bf2a-de5e8dfd98d3.png">

        
  * `GET a Tag by Id` - a single tag.
        
  <img width="1400" alt="image24_get-tag-by-id" src="https://user-images.githubusercontent.com/94569484/170667869-295e719b-5def-47c3-adcb-77a05a8263ca.png">


  3. **`POST` Request** - allows a user to create or add a new category, product, or tag. The following `POST` requests are created and tested to return: 
  
  * `POST Create a Category` - create or add a new category;
        
  <img width="1402" alt="image25_post-category" src="https://user-images.githubusercontent.com/94569484/170668338-53a4678a-b929-4430-97ca-e28f8d5596ec.png">

        
  * `POST Create a Product` - create or add a new product; and

  <img width="1401" alt="image26_post-product" src="https://user-images.githubusercontent.com/94569484/170668690-942f192e-f755-495e-97d7-03af427cc15f.png">

  <img width="1399" alt="image27_post-product2" src="https://user-images.githubusercontent.com/94569484/170668903-1f7c4610-1077-4690-87ef-1cdf40db869a.png">

    
  * `POST Create a Tag` - create or add a new tag;
      
    
    
  <img width="1395" alt="image28_post-tag" src="https://user-images.githubusercontent.com/94569484/170669080-1ea5bdc3-7e64-4678-b26f-696085187377.png">
      

  4. **`PUT` Request** - allows a user to update a category, product, or tag. The following `PUT` requests are created and tested to return:
  
  * `PUT Update a Category`- update a category; 

  <img width="1399" alt="image29_put-category1" src="https://user-images.githubusercontent.com/94569484/170669574-fa7e4c94-c619-4583-839f-ace9853a240f.png">

  <img width="1400" alt="image30_put-category2" src="https://user-images.githubusercontent.com/94569484/170670802-fd2bab24-82dd-427b-b7bc-9bdc88bc42c3.png">

  <img width="1400" alt="image31_put-category3" src="https://user-images.githubusercontent.com/94569484/170671116-10316597-b1d5-4118-ac44-ed8956daa529.png">


  * `PUT Update a Product` - update a product; and
        
  <img width="1396" alt="image32_put-product1" src="https://user-images.githubusercontent.com/94569484/170671661-3cff8aae-4529-4b5e-8ed1-0a5e5edcb5aa.png">
        
  <img width="1396" alt="image33_put-product3" src="https://user-images.githubusercontent.com/94569484/170672325-912d4d24-11db-46a0-8dcb-dc20b6df5114.png">


  * `PUT Update a Tag` - update a tag;
        
  <img width="1398" alt="image34_put-tag1" src="https://user-images.githubusercontent.com/94569484170672902-481414f7-778e-4321-8004-bb1010100afd.png">

  <img width="1395" alt="image35_put-tag2" src="https://user-images.githubusercontent.com/94569484/170673146-15a0e611-4f70-4a76-947a-f998419649e7.png">

  <img width="1398" alt="image36_put-tag3" src="https://user-images.githubusercontent.com/94569484/170673333-3476316b-285d-4efd-9af3-ca406956cc52.png">


  5. **`POST` Request** - allows a user to remove a category, product, or tag. The follwoing `POST` requests are created and tested to return:
  
  * `DELETE a Category` - remove a category;

  <img width="1399" alt="image37_delete-category" src="https://user-images.githubusercontent.com/94569484/170673685-4a7da0f5-8856-4004-8351-234b5df20589.png">

  <img width="1406" alt="image38_delete-category2" src="https://user-images.githubusercontent.com/94569484/170674080-b79c8eb0-a0a9-4b17-8a2d-b4ac2a0be440.png">

  <img width="1399" alt="image39_delete-category3" src="https://user-images.githubusercontent.com/94569484/170674242-a9a5234c-182b-4ba1-b125-b60479fb5d35.png">

  * `DELETE a Product` = remove a product; and
        
  <img width="1395" alt="image40_delete-product" src="https://user-images.githubusercontent.com/94569484/170674447-2fcad0fc-17e4-430e-8163-782e95aec9f5.png">

  * `DELETE a Tag` - remove a tag.
        
  <img width="1399" alt="image41_delete-tag" src="https://user-images.githubusercontent.com/94569484/170674653-4f766adb-d370-4d54-88b1-e506063c602b.png">


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


