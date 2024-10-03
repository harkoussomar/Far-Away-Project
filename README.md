# Far Away Packing List App

## Table of Contents

1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Components](#components)
   - [App Component](#1-app-component)
   - [Form Component](#2-form-component)
   - [PackingList Component](#3-packinglist-component)
   - [Item Component](#4-item-component)
   - [Stats Component](#5-stats-component)
   - [Logo Component](#6-logo-component)
4. [Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Installation](#installation)
5. [Usage](#usage)
6. [File Structure](#file-structure)


## Project Overview

The **Far Away Packing List** is a simple yet efficient React-based web application that helps users manage a list of items they need to pack for trips. It allows users to add, sort, toggle, and delete items from their packing list, offering an organized and user-friendly interface to ensure nothing is left behind.

## Features

- **Add New Items:** Users can add new items to their packing list by specifying the item description and quantity.
- **Delete Items:** Users can remove any item from their list with a single click.
- **Toggle Packed Status:** Users can mark items as packed or unpacked by clicking a checkbox.
- **Sort Items:** Users can sort the packing list by input order, description, or packing status.
- **Clear List:** With the click of a button, users can clear the entire packing list.
- **Real-time Statistics:** Displays the total number of items and the percentage of items packed.

## Components

### 1. `App` Component

This is the main component that manages the state and renders the UI by combining other components. It holds the list of items and handles the logic for adding, deleting, and updating item statuses.

#### State:
- `items`: An array of objects, where each object represents an item with properties such as `id`, `description`, `quantity`, and `packed`.

#### Functions:
- `handleAddItems(item)`: Adds a new item to the packing list.
- `handleDeleteItems(id)`: Removes an item from the packing list by `id`.
- `updateToggleItems(id)`: Toggles the `packed` status of an item by `id`.
- `handleClearList()`: Clears all items from the list.

#### Rendered Components:
- `Logo`
- `Form`
- `PackingList`
- `Stats`

### 2. `Form` Component

This component is responsible for capturing user input to add new items to the packing list. The user can select the quantity and type the item description.

#### State:
- `description`: Tracks the description of the item being added.
- `quantity`: Tracks the quantity of the item.

#### Props:
- `onAddItems`: A function passed down from the `App` component to handle the addition of new items.

#### Functions:
- `handleSubmit(event)`: Handles the form submission, preventing the default behavior and creating a new item to add to the list.

### 3. `PackingList` Component

This component renders the list of items and offers sorting options. It also contains logic to delete items, toggle their packed status, and clear the list.

#### State:
- `sortBy`: Tracks the current sorting method, which can be "input", "description", or "packed".

#### Props:
- `items`: The array of items passed down from `App`.
- `onDeleteItems`: A function to delete items from the list.
- `onToggleItems`: A function to toggle the packed status of items.
- `onClearList`: A function to clear all items from the list.

### 4. `Item` Component

This is a small component that represents each individual item in the packing list. It provides a checkbox to mark items as packed or unpacked and a delete button.

#### Props:
- `item`: The item object.
- `onDeleteItems`: A function to delete the item.
- `onToggleItems`: A function to toggle the packed status of the item.

### 5. `Stats` Component

This component displays the statistics for the packing list, such as the total number of items and the percentage of packed items.

#### Props:
- `items`: The array of items passed down from `App`.

#### Computed Values:
- `numItems`: Total number of items.
- `numItemsPacked`: Number of items marked as packed.
- `percentage`: Percentage of items packed (rounded to the nearest whole number).

### 6. `Logo` Component

This is a simple component that displays the logo and title of the application: "🌴 Far Away 👜".

## Getting Started

### Prerequisites

- Node.js and npm should be installed on your machine.

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/far-away-packing-list.git
   cd far-away-packing-list

2. Install the dependencies:
   ```bash
   npm install

3. Start the development server:
   ```bash
   npm start
The application should now be running on `http://localhost:3000/`.

## Usage

1. Enter the name of the item you wish to add in the input field at the top of the page.
2. Select the quantity of the item using the dropdown menu and click the "Add" button to include it in your packing list.
3. To mark an item as packed or unpacked, simply check or uncheck the box next to the item.
4. To remove an item from the list, click the ❌ button beside the corresponding item.
5. You can sort your items using the dropdown menu with the following options:
   - **Sort by Input Order**: Displays items in the order they were added.
   - **Sort by Description**: Arranges items alphabetically based on their description.
   - **Sort by Packed Status**: Organizes items by their packing status (packed vs. unpacked).
6. To clear all items from the list, click the "Clear List" button.

## File Structure
  ```bash
  src/
│
├── components/
│   ├── Form.js            // Form for adding new items
│   ├── Logo.js            // Logo of the application
│   ├── PackingList.js     // Displays and manages the list of items
│   └── Stats.js           // Displays packing statistics
│
├── App.js                 // Main application file
└── index.js               // Entry point for the React app

