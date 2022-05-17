Challenge Link: https://docs.google.com/document/d/1ijXrqQMOORukOWCWcwwcpxPcF_TczwvNE0wB4M2Orqg/edit#heading=h.n7bww7g70ipk

<h1>Shopify-Image-Repository</h1>
<h2>This is a demonstrative image repository with capacity to sell/buy products.</h2>

This project has been implemented in Python using Flask to serve a web interface and sqlite3 to track product information and transactions.

<h2>How to run the application on Localhost</h2>
- To use this application, simply run python3 server.py from the command line. This will create the appropriate database tables and start the Flask server.

- After this, open a web browser at the address given by Flask (usually http://127.0.0.1:5000). You will see a listing of products with associated data, such as their name, price, stock, and, of course, the image for said product. All of this data is pulled directly from a DB table and generated live with an HTML template. The images themselves are served from a static images folder.

- A user can also try to buy any product by clicking the BUY button next to its image. This will verify that there are any left in stock, and will record the transaction (including time, product, and value) in our transactions table, while decrementing the product's inventory appropriately. Note that on the home page, we can see the total value of all transactions we have processed to date.

<h2>Possible Features</h2>

- We could add a feature such as adding/removing products. 

- This would be straightforward to implement using a simple HTTP form that would POST an image and its data to our server, allowing us to save the image to our images folder and update our products table. 

- Another complimentary form would let us remove products from the database and delete the image from disk.

- Another feature would be access control, allowing us to have different users of the image repository. 

- One such user could be a vendor and another could be a customer. 

- We could verify vendors by a login form that would give the browser an access token, allowing the application to serve administrative tools to the user such as adding/removing products, viewing earnings, and managing inventory. 

- Customers could save payment information allowing them to easily buy products without having to enter their payment data again each time.

<h2>Output</h2>
![Screenshot (1)](https://user-images.githubusercontent.com/50801491/168886133-725621bc-75d1-4ceb-920a-31a6197f6bcd.png)

![Screenshot (2)](https://user-images.githubusercontent.com/50801491/168886159-f4cf9e1b-6a5e-4443-acfd-9bbc13c3676e.png)

![Screenshot (3)](https://user-images.githubusercontent.com/50801491/168886178-7aa28b88-8269-4b3a-8eaa-bd2599a9df9d.png)

![Screenshot (4)](https://user-images.githubusercontent.com/50801491/168886190-0f35c15e-a254-40b3-9df8-22a8a0f2eaf1.png)
