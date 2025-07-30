# Vehicle Rental Management App (React + Axios CRUD)

### Developed by **Vaibhav**, 4th Year B.Tech CSE Graduate | Built under guidance from **DevMountain**

---

## Overview

This project is a simple yet functional **Vehicle Rental Management App** built using **React** and **Axios**, showcasing full **CRUD operations**: `GET`, `POST`, `PUT`, and `DELETE`. It also implements user-friendly **toast notifications** to enhance UX by providing immediate visual feedback on API interactions.

This application is part of my learning journey, applying concepts learned through **DevMountain’s curriculum**, and extending them into a standalone React project. The focus is primarily on effective API handling, state management, and modular component interaction in a live frontend environment.

---

## 🚀 Live Demo

[Click here to view the live version](https://devmountain.github.io/react-3-mini/)
*(Note: This may point to the original hosted version. You can deploy your customized version to Vercel or Netlify for showcasing your own deployment.)*

![Demo Screenshot](https://github.com/DevMountain/react-3-mini/blob/solution/assets/1.png)

---

## 🔧 Setup Instructions

1. Clone the repository to your local machine
   `git clone <your-repo-url>`
2. Navigate to the project directory
   `cd vehicle-rental-app`
3. Install dependencies
   `npm install`
4. Start the React development server
   `npm start`
5. Open a second terminal (if needed for backend or mock API)

---

## 🛠️ Features & API Interaction

This application interacts with a mock API using `axios`. Toast notifications are integrated using `react-toastify` for real-time feedback.

### ✅ Successful API Request

```js
toast.success("Action completed successfully!");
```

### ❌ Failed API Request

```js
toast.error("Action failed. Please try again.");
```

---

## 📌 Implementation Steps

### Step 1: Fetch All Vehicles (`GET`)

* File: `./src/App.js`
* Method: `getVehicles()`

```js
axios.get('https://joes-autos.herokuapp.com/api/vehicles')
  .then(results => {
    toast.success("Successfully fetched vehicles");
    this.setState({ vehiclesToDisplay: results.data });
  })
  .catch(() => toast.error("Error fetching vehicles"));
```

---

### Step 2: Update Price (`PUT`)

* Method: `updatePrice(priceChange, id)`

```js
axios.put(`https://joes-autos.herokuapp.com/api/vehicles/${id}/${priceChange}`)
  .then(results => {
    toast.success("Price updated successfully");
    this.setState({ vehiclesToDisplay: results.data.vehicles });
  })
  .catch(() => toast.error("Error updating price"));
```

---

### Step 3: Add a New Vehicle (`POST`)

* Method: `addCar()`

```js
let newCar = {
  make: this.make.value,
  model: this.model.value,
  color: this.color.value,
  year: this.year.value,
  price: this.price.value
};

axios.post('https://joes-autos.herokuapp.com/api/vehicles', newCar)
  .then(results => {
    toast.success("Vehicle added successfully");
    this.setState({ vehiclesToDisplay: results.data.vehicles });
  })
  .catch(() => toast.error("Error adding vehicle"));
```

---

### Step 4: Delete Vehicle (`DELETE`)

* Method: `sellCar(id)`

```js
axios.delete(`https://joes-autos.herokuapp.com/api/vehicles/${id}`)
  .then(results => {
    toast.success("Vehicle removed successfully");
    this.setState({ vehiclesToDisplay: results.data.vehicles });
  })
  .catch(() => toast.error("Error removing vehicle"));
```

---

## 💎 Additional Practice

If you're looking to extend the project, you can:

* Refactor components into functional components with hooks
* Integrate Redux or Context API
* Add routing for individual vehicle pages
* Build an admin dashboard for vehicle management

---

## 🙌 Contributions

If you'd like to contribute to this project, feel free to fork the repository, make changes, and submit a pull request. All constructive feedback and improvements are welcome.

---

## 📄 License & Acknowledgements

© 2024 Vaibhav – Final Year B.Tech CSE Graduate
This project is created as a personalized implementation based on guided learning from **DevMountain**. Unauthorized reproduction or duplication is prohibited without explicit permission. Credits to DevMountain for educational resources and foundational project ideas.

---
