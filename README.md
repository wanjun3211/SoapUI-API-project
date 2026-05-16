# SoapUI-API-project about testing a calculator

## Introduction
This project is about using the Postman to test a public book management API, which consists of eight individual API testing items.  I first created each individual item and then writing corresponding test scripts to check they are working all properly. Finally, I used the Runner function in the Postman to automate this collection. 

## The Eight individual API Testing Items and Description
1. API Status.

    Using the **Get** to checking connection with server is working properly. The script in this section is
    ```javascript
    pm.test("Status code is 200",  ()=> {
    pm.response.to.have.status(200);
    });
    ```
  
3. List of books
   
    Using the  **Get** to list all the book information. The script in this section is
```javascript
pm.test("Status code is 200",  ()=> {
    pm.response.to.have.status(200);
});

const response = pm.response.json();
const books = response.filter((book) => book.available === true);

const book = books[0];

if(book){
pm.globals.set("avaBookId", books[0].id);
}

pm.test("Book found", ()=>{
    pm.expect(book).to.be.an('object');
    pm.expect(book.available).to.be.true;
    pm.expect(book.available).to.eql(true);
})
```
  

5. Get a single book

      Using the  **Get** to list all the book information. The script in this section is
```javascript
   pm.test("Status code is 200",  ()=> {
    pm.response.to.have.status(200);
});

const response = pm.response.json();
console.log(response['current-stock']);

pm.test("Stock is greater than 0",  ()=> {
    pm.expect(response['current-stock']).to.be.above(0);
});
   ```
   
7. Order book

    Using the **Post** to show one book information. The script in this section is
   ```javascript
    pm.test("Status code is 201",  ()=> {
    pm.response.to.have.status(201);
   });
    ```
    
9. Get all order books

    Using the **Get** to show all the book order information. The script in this section is
```javascript
    pm.test("Status code is 200",  ()=> {
    pm.response.to.have.status(200);
});

const response = pm.response.json();
console.log(response[0].id);
pm.globals.set("orderID", response[0].id);
```
   
11. Get an order

     Using the **Get** to show one order information.
    
13. Update an order

    Using the **Patch** to update the order information. In this instance, I tried to update the borrower's name. The script in this section is
```javascript
    pm.test("Status code is 204",  ()=> {
    pm.response.to.have.status(204);
});
```
    
     
15. Delete order

    Using the **Delete** to delete an existing order. The script in this section is
    ```javascript
    pm.test("Status code is 204",  ()=> {
    pm.response.to.have.status(204);
    });
    ```

    
## Using **Runner** to automate this collection

The photo is a screenshot that shows this collection result. And there is one fialed API request due to repetitive registration of client.

<img width="1234" height="823" alt="image" src="https://github.com/user-attachments/assets/9672aa1c-4d28-48e8-947a-aac42819288f" />

## Other feature of this API testing 

The base API address and book ID has been stored in the varible.
