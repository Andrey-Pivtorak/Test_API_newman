# **Postman + newman + github actions + newman report**

## **Commands Overview**
1. Install Node.js (minimum 16 version) on your PC

    [choose version](https://nodejs.org/en/download/releases/)

2. Open the command line.
3. open the command line (or terminal, if VS Code or another apps are used) and copy the repository. Enter the command:

    **git clone https://github.com/Andrey-Pivtorak/Postman_API_testing.git**

4. Move to the _Postman_API_testing_ folder, using the command:

    **cd Postman_API_testing**

5. Run _npm i_ to install node.js dependencies.
6. Run _npm run tern-on-api_ to run testing server locally on 3000 port.
7. Run _npm run test_ to run newman runner with store.collection.json through API on local server.
8. Run _allure:report_ to run generate the static report web-application folder.
9. Run _allure:open_ to open web-report.

### REST API Overview
Routes `/products`, `/orders` and `/users`. Below is a table of supported operations with `users` as example resource. The same operations are also supports for `products/` and `orders/`.

| VERB     |Route       |Input       |Output              |
|----------|------------|------------|--------------------|
| GET      | /users     | *None*     | **Array**          |
| GET      | /users/:id |  **e.g 9** | **Object**         |
| POST     | /users     | **object** | **Created object** |
| PUT      | /users     | **object** | **Updated object** |
| DELETE   | /users/:id | **e.g 9**  | **Deleted object** |

Test examples overview:
- Test pagination, by way like `http://localhost:3000/users?page=1&pageSize=5`.
- Test sorting, by way like `http://localhost:3000/users?sortOrder=ASC&sortKey=email`. You can sort an any resource response using query parameters sortOrder and sortKey.
-  Test status code for REST API (200, 201).
-  Test response time.
-  Test response thanks to json schema validation.

### You must have this result:
![](https://github.com/Andrey-Pivtorak/Postman_API_testing/blob/main/mockApi/screens/allure_report.png)
