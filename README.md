<div align="center">

# 🏰 Mission II: The Cursed Royal Marketplace

### 🔥 A Hard MEN Stack Debugging Mission 🔥

![Difficulty](https://img.shields.io/badge/Difficulty-Hard-8B0000?style=for-the-badge)
![Time](https://img.shields.io/badge/Time-45%20Minutes-B8860B?style=for-the-badge)
![Formation](https://img.shields.io/badge/Formation-Teams%20of%203-4B0082?style=for-the-badge)
![Stack](https://img.shields.io/badge/Stack-MongoDB%20%7C%20Express%20%7C%20Node.js-355E3B?style=for-the-badge)

</div>

---

## 📜 The Royal Emergency

The **Dark Bug** has returned and placed a powerful curse on Codoria's Royal Marketplace.

Magical artifacts have vanished from the shelves. Merchants cannot add or update their items. Reviews are being attached to the wrong artifacts, routes lead travelers into darkness, and the Royal Archives refuse to reveal their records.

The marketplace is built using the legendary **MEN Stack**:

- 🍃 **MongoDB** protects the Royal Archives
- 🗺️ **Express** controls the kingdom's routes
- ⚔️ **Node.js** powers the Royal Server

Your team must investigate the complete application, repair its models, routes, views, and database operations, and lift the curse before the marketplace closes forever.

> **This is a hard mission. Do not trust appearances—some code may look correct while leading you to the wrong destination.**

---

## 🗺️ Mission Brief

| Mission detail | Information |
|---|---|
| ⏳ Time limit | 45 minutes |
| 👥 Formation | Teams of 3 |
| 🔥 Difficulty | Hard |
| 🧰 Technology | MongoDB, Mongoose, Express, Node.js and EJS |
| 🐛 Corruption detected | Models, routes, views, forms and server configuration |
| 🎯 Main objective | Restore the complete Royal Marketplace |
| ⭐ Bonus quest | Repair the Royal Review system |
| 🏆 Maximum reward | 40 Kingdom Points |

---

## 🏪 The Royal Marketplace

The application manages magical artifacts such as:

- ⚔️ Enchanted weapons
- 🛡️ Royal armor
- 🧪 Magical potions
- 📜 Ancient scrolls
- 💎 Rare treasures
- 🪄 Legendary magical items

Each artifact should contain:

| Field | Purpose |
|---|---|
| `name` | Name of the artifact |
| `category` | Weapon, Armor, Potion, Scroll, Treasure or Magical Item |
| `description` | Information about the artifact |
| `price` | Price in gold coins |
| `rarity` | Common, Rare, Epic or Legendary |
| `image` | Image URL |
| `owner` | Knight or merchant who created it |
| `reviews` | Reviews connected to the artifact |

---

## 🎯 Main Quest: Restore Artifact CRUD

Your team must restore all four CRUD operations:

| Operation | Expected result |
|---|---|
| **Create** | A merchant can add a new artifact |
| **Read** | Visitors can see all artifacts and view one artifact's details |
| **Update** | An artifact can be edited and saved |
| **Delete** | An artifact can be removed from the marketplace |

### Routes that must work

| Method | Route | Expected action |
|---|---|---|
| `GET` | `/` | Display the Codoria home page |
| `GET` | `/artifacts` | Display every artifact |
| `GET` | `/artifacts/new` | Display the new artifact form |
| `POST` | `/artifacts` | Create an artifact |
| `GET` | `/artifacts/:artifactId` | Display one artifact |
| `GET` | `/artifacts/:artifactId/edit` | Display the edit form |
| `PUT` | `/artifacts/:artifactId` | Update an artifact |
| `DELETE` | `/artifacts/:artifactId` | Delete an artifact |

---

## ⭐ Bonus Quest: Restore the Royal Reviews

After Artifact CRUD works, restore the review system.

Each review contains:

- A message
- A rating from 1 to 5
- The review's author

| Method | Route | Expected action |
|---|---|---|
| `POST` | `/artifacts/:artifactId/reviews` | Add a review to an artifact |
| `DELETE` | `/artifacts/:artifactId/reviews/:reviewId` | Delete a review |

The review must be connected to the correct artifact and displayed on its details page.

---

## 🧭 Recommended Investigation Order

Do not randomly edit every file. Investigate the application in stages:

### Stage I — Awaken the Royal Server

1. Install the dependencies.
2. Create your `.env` file.
3. Start the application.
4. Read the first terminal error carefully.
5. Repair server imports, middleware and database configuration.

### Stage II — Open the Marketplace

1. Visit `/artifacts`.
2. Repair the index route and view.
3. Confirm that existing artifacts appear.

### Stage III — Restore Artifact CRUD

Test Create, Show, Update and Delete separately. Complete one operation before moving to the next.

### Stage IV — Restore the Reviews

Test the review form, artifact ID, database relationship and redirect destination.

### Stage V — Final Inspection

Test every route again and confirm that the terminal and browser consoles contain no errors.

---

## 🧰 Prepare for the Mission

Clone the repository and enter its folder:

```bash
git clone <repository-url>
cd mission-2-cursed-marketplace
```

Install the dependencies:

```bash
npm install
```

Create a `.env` file in the root of the project:

```env
MONGODB_URI=your_mongodb_connection_string
PORT=3000
```

Start the Royal Server:

```bash
nodemon server.js
```

If the application does not start, **that is part of the mission**. Read the error message and begin your investigation.

---

## ✅ Victory Conditions

The curse is lifted only when:

- [ ] The application starts without crashing
- [ ] MongoDB connects successfully
- [ ] Static files load correctly
- [ ] The home page renders correctly
- [ ] All artifacts are displayed
- [ ] One artifact can be viewed
- [ ] A new artifact can be created
- [ ] An artifact can be updated
- [ ] An artifact can be deleted
- [ ] Forms send information to the correct routes
- [ ] Redirects lead to routes rather than EJS files
- [ ] EJS views render without path errors
- [ ] Reviews connect to the correct artifact
- [ ] Every Software Knight can explain at least two repairs

---

## 🏆 Kingdom Points

Your team can earn up to **40 Kingdom Points**:

| Achievement | Points |
|---|---:|
| Royal Server starts and connects to MongoDB | 5 |
| Artifact index and show pages work | 6 |
| Create Artifact works | 5 |
| Update Artifact works | 5 |
| Delete Artifact works | 5 |
| Royal Review system works | 5 |
| Team explains its debugging process | 4 |
| Every Software Knight participates | 3 |
| Clear code and meaningful commits | 2 |
| **Maximum score** | **40** |

### Royal Rules

- Every team receives the full 45 minutes.
- Speed does not earn additional points.
- Each opened hint costs **1 Kingdom Point**.
- Do not delete the application and rebuild it from the beginning.
- Repair the existing code and keep its original structure.
- Do not copy another team's solution.
- Do not submit AI-generated code your team cannot explain.
- The instructor may ask any team member to explain a repair.

---

## 🔮 The Royal Book of Hints

Open hints only after your team has read the error, inspected the related file, and attempted a repair.

<details>
<summary>🕯️ Server Hint</summary>

Compare every imported route filename with the actual filename inside the `routes` folder. Also inspect the middleware configuration carefully.

</details>

<details>
<summary>🗺️ Route Hint</summary>

Express route callbacks receive two important objects in a specific order. Swapping them changes which object contains the request information and which sends the response.

</details>

<details>
<summary>📜 EJS Hint</summary>

`res.render()` expects a view path relative to the `views` folder. A view path is not a URL, and it should not begin at the root of the computer.

</details>

<details>
<summary>🚪 Redirect Hint</summary>

`res.redirect()` sends the browser to an application route. It does not directly open a file from the `views` folder.

</details>

<details>
<summary>🍃 Database Hint</summary>

Before passing a value into `findById()`, inspect the submitted form data. Does the ID exist directly in `req.body`, or inside a named property?

</details>

<details>
<summary>🧪 Form Hint</summary>

Compare each form's `action`, method override value and input `name` attributes with the route that should receive the request.

</details>

---

## 📤 Declare Your Victory

Before time expires:

1. Test every route in the victory checklist.
2. Check the terminal and browser console.
3. Confirm that every team member understands the repairs.
4. Commit the completed application using a meaningful message:

```text
Lift the curse from the Royal Marketplace
```

5. Select one Software Knight to demonstrate the application.

---

## 📖 The Royal Debugging Code

- Read the complete error message before editing.
- Fix one problem at a time.
- Test after every important repair.
- Use `console.log()` when you need to inspect data.
- Check route parameters, request bodies and EJS variables carefully.
- Never assume that a redirect and a render perform the same job.
- Ask your teammates to explain their changes.

---

<div align="center">

## ⚔️ The Marketplace Awaits ⚔️

**The artifacts are missing. The routes are corrupted. The Dark Bug is watching.**

🏰 Restore the MEN Stack and return peace to Codoria! 🐛

</div>
