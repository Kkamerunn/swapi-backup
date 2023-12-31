# swapi challenge by Lucas DG

## Usage
The app is quite easy to use. The home ("/") is the vehicles page, there you will see all the vehicles fetched from the API which has filled the database with the star-wars-api info.
You can navigate between the vehicles and the starships page with the navbar. Both pages share the same functionallity. The vehicles and starships are listed as a list of cards. Each card has the name of the aircraft, its model and the each's one inventory. Also a number input to select the amount of vehicles or starships in inventory. You can modify the amount by
either setting it with the "set" button or increment/decrement it with the "increment/decrement" button. Note that at the begining, as no aircraft has an inventory by default, the "increment/decrement" button of each aircraft card stays disabled until you set the inventory for first time with the set button. Once done it, the button becomes available to increment
and decrement the aircraft inventory as much as you like. 

# Instructions for running this project

To run this project is recommended to use node 18^ in case you don't have it installed you can install nvm (node version manager) and use it to install node 18^ and switch between different versions.
Also make sure to have docker installed since the database is a MySQL image. And finally I quite recommend you to have some database client such as DBeaver, MySQL Workbench,
phpMyAdmin, tablePlus or something like that. And that's it.


### Step 1
Clone this repository into your local machine. Open a terminal and run the following command:

```
git clone https://github.com/Kkamerunn/swapi.git
```
After the project has finished downloading, open it in VScode or the editor you have installed. Then open two terminals, one to get into the project server which name is swapi-server, 
and the other to get into the react project which name is swapi-challenge. Once in the server's terminal, run the following commands:

This command will build the container with the MySQL image.
```
docker compose up
```

This command will install all the packages for de server app
```
npm install
```

### Step 2
Migrate the database. We need to run the migrations to create the database a tables that our app needs to work.

```
npx sequelize-cli db:migrate
```

### Step 3
Create an .env file in the root folder and paste this code:

```
FRONT_END_URL="http://localhost:5173"
PORT=3000
```

The FRONT_END_URL  is url where we are going to run the client side app, therefore you can change for the one that works for your machine.The PORT is the port exposed for our API.
As with the url, you can change for any of your preference, if the API finds your port is being used, it is going to use the 4000 by default.


### Step 4
Run the server app (API):

```
npm run dev
```


### Step 5
Time to run react app. First, install all the needed dependencies.
Go to the opened terminal in the react app and run the following commands:

```
npm install
```

### Step 6
Create an .env file in the root folder and paste this code:

```
VITE_BACKEND_URL="http://localhost:3000"
```

As you can imagine this url of our server and the react app needs it to consume the info.
You can modify this file setting API url that you finally decided to use.

### Step 7
Run the app with the following command:

```
npm run dev
```
finally open the link retorned by the terminal on a browser of you preference.
