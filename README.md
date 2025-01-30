To-Do List - React with TypeScript and API Integration

A simple To-Do List application built with React, TypeScript, and API integration. This app allows users to view a list of tasks from a remote API and filter them by their status.

Features
	•	View Tasks from API: The tasks are fetched from an external API.
	•	Task Filtering: Users can filter tasks based on their completion status (e.g., All, Active, Completed).
	•	Loading State: A loading indicator is shown while data is being fetched from the API.

Technologies Used
	•	React: A JavaScript library for building user interfaces.
	•	TypeScript: A superset of JavaScript that adds static typing to the language.
	•	Fetch API: For making HTTP requests to fetch tasks from an API.
	•	Bulma: A modern CSS framework to create clean and responsive UI designs.
	•	FontAwesome: For icons in the UI.

Installation
	1.	Clone this repository:

`git clone https://github.com/chelsea7smile/react-todo-list.git`


2.	Navigate to the project directory:

`cd react-todo-list`


3.	Install dependencies:

`npm install`



Usage
	1.	To run the app in development mode:

`npm start`

This will start the development server, and you can view the app at http://localhost:3000.

	2.	To create a production build:

npm run build

This will create an optimized production build of the app in the build directory.

Project Structure

src/
│
├── components/         # UI components
│   ├── Header.tsx
│   ├── TodoList.tsx
│   ├── TodoItem.tsx
│   ├── TodoFilter.tsx
│   └── Footer.tsx
├── features/           # Handles the fetching and filtering logic
│   ├── todos.ts        # To-do list for handling fetched tasks
│   └── filter.ts       # Filter for managing the current task filter
├── types/              # TypeScript types
│   └── Todo.ts         # Type definition for a Todo task
├── utils/              # Utility functions
│   └── fetchClient.ts  # Handles the fetch logic for API requests
├── App.tsx             # Main application component
└── index.tsx           # Entry point for React

Fetching Data

The tasks are fetched from an external API when the component is mounted:
	1.	getTodos() is called to fetch tasks from the API.
	2.	The data is stored in the component’s state.
	3.	The user can filter the tasks using the filter component, which updates the visible tasks.


Example Usage in API Functions

import { client } from './utils/fetchClient';

const TODOS_API_PATH = '/todos';
const USER_ID = 1;

export const getTodos = () => {
  return client.get<Todo[]>(`${TODOS_API_PATH}?userId=${USER_ID}`);
};

License

This project is licensed under the MIT License - see the LICENSE file for details.

