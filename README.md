# Introduction to Rails discussion questions

Take 30 minutes to discuss the following questions with your table group.

## Rails router

1. What are the seven conventional REST routes for a pizza resource? For each route list the HTTP verb, path and rails controller/action pair

Route Name | HTTP Verb | Path | Rails Controller Action
- | - | - | -
Index | GET | /pizzas | `pizzas#index`
New | GET | /pizzas/new | `pizzas#new`
Create | POST | /pizzas | `pizzas#create`
Show | GET | /pizzas/:id | `pizzas#show`
Edit | GET | /pizzas/:id/edit | `pizzas#edit`
Update | PATCH | /pizzas/:id | `pizzas#update`
Destroy | DELETE | /pizzas/:id | `pizzas#destroy`

2. What benefits does naming a route provide? (e.g. get '/pizzas, to: 'pizzas#index, as: 'pizzas')

Naming a route can be convenient, and prevent name collisions that might occur with users of different authority using the web app. The example provided in the question is curious, as `resources :pizzas` defaults to creating a route name `pizzas_path`, which is what the example would result in.

3. Assuming you are using the standard REST routes, what rails built-in methods can be used to write concise routes?

Using the `resources` helper method in `config/routes.rb` will generate concise and intuitive RESTful route names for a model.

## Rails Request and Response cycle

1. What are the steps that Rails will take to implement the use cases below? List the verb/path, controller/action and associated SQL.
    - Display a list of resources
        - GET /resources
        - `resources#index`
        - `SELECT * FROM resources;`
    - Delete a resource
        - DELETE `/resources/:id`
        - `resources#destroy`
        - `DELETE * FROM resources WHERE id = :id;`
    - Create a new resource
        - POST `/resources`
        - `resources#create`
        - `INSERT INTO resources (attribute1, attribute2) VALUES (value1, value2);`
    - Display one resource
        - GET `/resources/:id`
        - `resources#show`
        - `SELECT * FROM resources WHERE id = :id;`
