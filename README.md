Airbnb Clone — Home Rental Web Application
A server-rendered home rental web application inspired by Airbnb. Built with Node.js, Express.js, EJS, and Tailwind CSS, this project lets visitors browse property listings, view individual home details, and manage a favourites list. It also includes a host section for adding, editing, and deleting property listings.
Project note: This is a learning project, not an official Airbnb product. Listing and favourites data are stored locally in JSON files; the project does not currently use a database, user authentication, or real booking/payment services.

Features
Visitor features
- View the home page and browse available properties.
- Open a property details page.
- Add properties to a favourites list.
- View and remove favourite properties.
- Open the bookings page (currently a UI page, not a real booking workflow).
- See a custom 404 page for unknown routes.
Host features
- Open a form to add a property listing.
- View the host's property list.
- Edit an existing listing.
- Delete a listing.
Technical features
- Express routes separated from controller logic.
- Dynamic HTML rendering with EJS templates and reusable partials.
- JSON-file persistence using Node.js fs module.
- Static assets served from the public directory.
- Tailwind CSS for styling, with a build/watch script.
Tech Stack
- Runtime: Node.js
- Server: Express.js
- Templating: EJS
- Styling: Tailwind CSS, CSS
- Data storage: Local JSON files
- Development tools: Nodemon, npm
Project Structure
Airbnb-Clone/
├── controller/
│   ├── error.js
│   ├── hostController.js
│   └── storeController.js
├── data/
│   ├── favourite.json
│   └── homes.json
├── models/
│   ├── favourite.js
│   └── home.js
├── public/
│   ├── images/
│   ├── home.css
│   └── output.css
├── routes/
│   ├── hostRouter.js
│   └── storeRouter.js
├── utils/
│   └── pathUtil.js
├── views/
│   ├── host/
│   ├── partials/
│   ├── store/
│   ├── 404.ejs
│   └── input.css
├── app.js
├── nodemon.json
├── package.json
├── package-lock.json
├── postcss.config.js
├── tailwind.config.js
├── .gitignore
└── README.md
Prerequisites
Install Node.js (which includes npm) before running the application. You can verify the installation with:
node --version
npm --version
Installation and Setup
1. Clone the repository (replace the placeholder with your GitHub repository URL):
   git clone <YOUR_GITHUB_REPOSITORY_URL>
2. Move into the project folder (use the actual folder name in your repository):
   cd "Airbnb - 1"
3. Install dependencies:
   npm install
4. Start the application:
   npm start
5. Open the app in your browser:
   http://localhost:3001
If the start script does not run correctly on your operating system
The current start script launches Nodemon and the Tailwind watcher together. If the combined script does not work in your terminal, run the server and CSS watcher in two separate terminals, from the project folder:

Terminal 1 — start the server:
npx nodemon app.js
Terminal 2 — watch and rebuild Tailwind CSS:
npm run tailwind
Keep both terminals open while developing. The Express server uses port 3001 in app.js.
Main Routes
Route	Purpose
/	Home page
/homes	Browse available homes
/homes/:homeId	View a home's details
/favourites	View favourite homes
/bookings	Bookings page UI
/host/add-home	Display the add-home form
/host/host-home-list	View host listings
/host/edit-home/:homeId	Display the edit form for a home


Some actions use POST requests from the forms, such as creating, editing, deleting, and favouriting a home.
Data Storage
The application stores data in these local files:
- data/homes.json — property listings.
- data/favourite.json — IDs of favourite properties.
Keep these files in place when running the application. Since the project uses local JSON files rather than a database, data is stored on the machine running the server and is not shared across deployments. Back up these files before manually editing or resetting data.
Useful Commands
Command	Description
npm install	Install project dependencies
npm start	Start the app using the configured start script
npx nodemon app.js	Run the Express server with automatic restarts
npm run tailwind	Watch input CSS and rebuild public/output.css


Current Limitations
- No sign-up, login, or user-specific accounts.
- No database integration; JSON files are used for storage.
- The bookings page is not connected to a real reservation system.
- No payment gateway or production booking workflow.
- This project is intended for learning and demonstration purposes.
Future Improvements
- Add authentication and authorization for hosts.
- Replace JSON-file storage with MongoDB or another database.
- Add date availability, booking management, and validation.
- Add image uploads and stronger server-side input validation.
- Deploy the application and configure production environment settings.
Author
Ali Mehdi
If you find this project useful for learning, feel free to explore the code and build on it.