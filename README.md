# **Galactic Battle**

\!\[Galactic Battle Title Screen\](https://github.com/MicahHogan/galactic-battle/blob/main/galactic-battle-title-screen.png "Galactic Battle Title Screen")

\!\[Galactic Battle Gameplay\](https://github.com/MicahHogan/galactic-battle/blob/main/galactic-battle-01.png "Galactic Battle Game Play")

\!\[Galactic Battle Gameplay\](https://github.com/MicahHogan/galactic-battle/blob/main/galactic-battle-02.png "Galactic Battle Game Play")

## **Table of Contents**

* [About the Game](https://www.google.com/search?q=%23about-the-game)  
* [Features](https://www.google.com/search?q=%23features)  
* [How to Play](https://www.google.com/search?q=%23how-to-play)  
* [Technologies Used](https://www.google.com/search?q=%23technologies-used)  
* [Setup and Installation](https://www.google.com/search?q=%23setup-and-installation)  
* [Firebase Configuration](https://www.google.com/search?q=%23firebase-configuration)  
* [Contributing](https://www.google.com/search?q=%23contributing)  
* [License](https://www.google.com/search?q=%23license)

## **About the Game**

Galactic Battle is a fast-paced, retro-inspired arcade shooter built entirely with HTML, CSS, and JavaScript. Defend the galaxy from endless waves of alien invaders, including challenging boss battles, collect power-ups, and aim for the top score on the global leaderboard\!

## **Features**

* **Classic Arcade Action:** Engage in intense top-down shooting gameplay.  
* **Dynamic Waves & Bosses:** Face increasingly difficult waves of enemies and unique boss encounters with varied attack patterns.  
* **Power-Ups:** Collect special bonuses like Raygun, Bazooka, Shield, Time Slow, Homing Missiles, Drones, and Score Multipliers to enhance your combat capabilities.  
* **Generative Background Music:** Experience an adaptive, procedurally generated soundtrack that evolves with your gameplay.  
* **Global Leaderboard:** Compete with players worldwide for the highest score, powered by Firebase Firestore.  
* **Responsive Design:** Play seamlessly on both desktop and mobile devices with touch controls.  
* **Sound Effects:** Engaging sound effects for shots, explosions, and power-up collection.

## **How to Play**

### **Controls**

* **Move Left:** A or Left Arrow  
* **Move Right:** D or Right Arrow  
* **Shoot:** Spacebar  
* **Pause/Unpause:** P  
* **Restart Game (Game Over Screen):** Spacebar or click/tap anywhere on the screen.

### **Mobile Controls**

On mobile devices, on-screen touch controls will appear:

* **Left Button:** Move Left  
* **Right Button:** Move Right  
* **FIRE Button:** Shoot (also starts the game from the title screen)

### **Gameplay Mechanics**

* Destroy all enemies in a wave to progress.  
* Every few waves, you'll encounter a powerful boss.  
* Collect power-ups that drop from defeated enemies to gain temporary advantages.  
* Avoid enemy bullets and collisions to preserve your lives.  
* Achieve high accuracy for bonus points at the end of each wave.  
* Enter your initials on the high score screen if you make it to the top 10\!

## **Technologies Used**

* **HTML5:** For the game structure.  
* **CSS3:** For styling and animations.  
* **JavaScript (ES6+):** For game logic, rendering, and interactivity.  
* **Firebase Firestore:** For real-time global leaderboard persistence.  
* **Font Awesome:** For various icons within the game (e.g., sound/pause toggles, bonus weapon icons).  
* **Google Fonts (Metal Mania):** For the distinct game title font.  
* **Web Audio API:** For generative background music and sound effects.

## **Setup and Installation**

To run this game locally:

1. **Clone the repository:**  
   git clone https://github.com/your-username/galactic-battle.git  
   cd galactic-battle

2. Open galactic-battle-production.html in your web browser.  
   You can simply double-click the file, or use a local web server (e.g., python \-m http.server or Live Server VS Code extension) for better security context and future development.

## **Firebase Configuration**

This game uses Firebase Firestore for its global leaderboard. To enable the leaderboard functionality, you need to set up your own Firebase project:

1. **Create a Firebase Project:**  
   * Go to the [Firebase Console](https://console.firebase.google.com/).  
   * Click "Add project" and follow the steps.  
2. **Add a Web App to your Project:**  
   * In your Firebase project, click the "Web" icon (\</\>) to add a web app.  
   * Follow the setup instructions. You'll get a firebaseConfig object.  
3. **Update firebaseConfig in galactic-battle-production.html:**  
   * Open galactic-battle-production.html.  
   * Locate the firebaseConfig object within the \<script type="module"\> tag:

   const firebaseConfig \= {  
         apiKey: "YOUR\_API\_KEY",  
         authDomain: "YOUR\_AUTH\_DOMAIN",  
         projectId: "YOUR\_PROJECT\_ID",  
         storageBucket: "YOUR\_STORAGE\_BUCKET",  
         messagingSenderId: "YOUR\_MESSAGING\_SENDER\_ID",  
         appId: "YOUR\_APP\_ID",  
         measurementId: "YOUR\_MEASUREMENT\_ID" // Optional  
     };

   * Replace the placeholder values with your actual Firebase project configuration.  
4. **Enable Firestore Database:**  
   * In the Firebase Console, navigate to "Firestore Database" from the left menu.  
   * Click "Create database".  
   * Choose "Start in production mode" (or "Start in test mode" for quick testing, but remember to update rules later).  
   * Select a Firestore location.  
5. **Set up Firestore Security Rules:**  
   * In the Firestore Database section, go to the "Rules" tab.  
   * Update your rules to allow read/write access for authenticated users to the highscores collection. For a public leaderboard, you might use rules similar to this:

   rules\_version \= '2';  
     service cloud.firestore {  
       match /databases/{database}/documents {  
         match /artifacts/{appId}/public/data/highscores/{document=\*\*} {  
           allow read, write: if request.auth \!= null;  
         }  
       }  
     }

   * **Important:** The game uses anonymous authentication (signInAnonymously). Ensure your rules allow authenticated users (request.auth \!= null) to read and write to the highscores collection. The \_\_app\_id variable is automatically provided in the Canvas environment, so the path artifacts/{appId}/public/data/highscores is crucial.

## **Contributing**

Contributions are welcome\! If you have suggestions for improvements, bug fixes, or new features, please feel free to:

1. Fork the repository.  
2. Create a new branch (git checkout \-b feature/your-feature-name).  
3. Make your changes.  
4. Commit your changes (git commit \-m 'Add new feature').  
5. Push to the branch (git push origin feature/your-feature-name).  
6. Open a Pull Request.

## **License**


This project is open-source and available under the [MIT License](https://www.google.com/search?q=LICENSE).
1d524c77e229adcd8ad1ec2f2dc576195a2e06b8
