![Ironhack Logo](https://i.imgur.com/1QgrNNw.png)

# Answers

### 1. All the companies whose name match 'Babelgum'. Retrieve only their `name` field.
filter: { name: "Babelgum"}
<!-- Your Code Goes Here -->

### 2. All the companies that have more than 5000 employees. Limit the search to 20 companies and sort them by **number of employees**.
filter: { number_of_employees : { $gt: 5000 } }
sort:{ number_of_employees : 1 } 
limit: 20 

<!-- Your Code Goes Here -->

### 3. All the companies founded between 2000 and 2005, both years included. Retrieve only the `name` and `founded_year` fields.
filter: {founded_year: {$in: [2000, 2001, 2002, 2003, 2004, 2005] }}
project: {founded_year: 1, name: 1,  _id: 0}
sort: { founded_year : 1 }

<!-- Your Code Goes Here -->

### 4. All the companies that had a Valuation Amount of more than 100.000.000 and have been founded before 2010. Retrieve only the `name` and `ipo` fields.

<!-- Your Code Goes Here -->

### 5. All the companies that have less than 1000 employees and have been founded before 2005. Order them by the number of employees and limit the search to 10 companies.
filter: {number_of_employees : { $lt: 1000 } } , {founded_year : { $lt: 2005} }
sort: {number_of_employees : -1 }    skip: 18791
<!-- Your Code Goes Here -->

### 6. All the companies that don't include the `partners` field.
filter: {partners : { $exists: false }}

<!-- Your Code Goes Here -->

### 7. All the companies that have a null type of value on the `category_code` field.
filter: {category_code : { $type: null}}

<!-- Your Code Goes Here -->

### 8. All the companies that have at least 100 employees but less than 1000. Retrieve only the `name` and `number of employees` fields.
filter: {number_of_employees : {$lt: 1000, $gte: 100}}
project: {number_of_employees: 1 ,name: 1, _id: 0}

<!-- Your Code Goes Here -->

### 9. Order all the companies by their IPO price in a descending order.

<!-- Your Code Goes Here -->

### 10. Retrieve the 10 companies with most employees, order by the `number of employees`
sort: {number_of_employees: -1}
limit: 10
<!-- Your Code Goes Here -->

### 11. All the companies founded on the second semester of the year. Limit your search to 1000 companies.
limit: 1000
filter: { founded_month: {$in: [6, 7, 8, 9, 10, 11, 12]}}

<!-- Your Code Goes Here -->

### 12. All the companies founded before 2000 that have an acquisition amount of more than 10.000.000
{founded_year: {$lt: 2000}, "acquisition_amount": {$gt: 10000000}}
<!-- Your Code Goes Here -->

### 13. All the companies that have been acquired after 2010, order by the acquisition amount, and retrieve only their `name` and `acquisition` field.
{"acquisition_acquired_year": 2010}}
{ name: 1, acquisition: 1, _id: 0}
{ acquisition: -1}

<!-- Your Code Goes Here -->

### 14. Order the companies by their `founded year`, retrieving only their `name` and `founded year`.
project: {founded_year: 1, name: 1,  _id: 0}
sort: { founded_year : -1 }

<!-- Your Code Goes Here -->

### 15. All the companies that have been founded on the first seven days of the month, including the seventh. Sort them by their `acquisition price` in a descending order. Limit the search to 10 documents.
filter: { founded_day: {$lte: 7}}
sort: {acquisition: -1}
limit: 10
<!-- Your Code Goes Here -->

### 16. All the companies on the 'web' `category` that have more than 4000 employees. Sort them by the amount of employees in ascending order.
filter: {category_code: "web"}, {number_of_employees: { $gt: 4000}}
sort: {number_of_employees: 1}

<!-- Your Code Goes Here -->

### 17. All the companies whose acquisition amount is more than 10.000.000, and currency is 'EUR'.
filter:{"acquisition.price_amount": {$gt: 10000000}, "acquisition.price_currency_code:"EUR}
<!-- Your Code Goes Here -->

### 18. All the companies that have been acquired on the first trimester of the year. Limit the search to 10 companies, and retrieve only their `name` and `acquisition` fields.
filter: {"acquisition.acquired_month": {$eq: 3}}
project:{name: 1, acquisition: 1, _id: 0}
limit: 10

<!-- Your Code Goes Here -->

### 19. All the companies that have been founded between 2000 and 2010, but have not been acquired before 2011.
filter: {"founded_year: {$gte: 2000, $lte: 2010, "acquisition.acquired_year: {$gte: 2011}}
<!-- Your Code Goes Here -->
