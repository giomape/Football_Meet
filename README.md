# Football Meet

Football Meet is a web-based social networking platform designed to connect football players ('calciatori') and clubs ('società'). It provides a complete ecosystem for users to create profiles, share updates, discover talent, and communicate with each other. The application leverages PHP for its backend logic and a MySQL database to store user data, posts, and relationships.

## Features

*   **Dual User Roles:** Separate registration and profile management for 'Calciatore' (Player) and 'Società' (Club).
*   **User Authentication:** Secure login system with password hashing (`password_hash`) and email verification for new accounts.
*   **Dynamic Homepage:** A personalized feed displaying posts from followed accounts.
*   **Profile Management:** Detailed user profiles including personal information, biography, playing roles, team history, and follower/following statistics.
*   **Content Creation:** Users can create, view, and delete their own posts.
*   **Social Graph:** A follow/unfollow system to build a network.
*   **Real-time Messaging:** A private chat interface for direct communication between users, with notifications for new messages.
*   **Geospatial Search:** Find nearby players or clubs using latitude and longitude data, powered by the OpenStreetMap Nominatim API.
*   **User Search:** A global search bar with autocompletion to easily find other users.
*   **Profile Discovery:** 'Most Popular' and 'Nearby' sections to suggest new profiles to a user.

## Technology Stack

*   **Backend:** PHP
*   **Frontend:** HTML5, CSS3, JavaScript, jQuery, Bootstrap
*   **Database:** MySQL
*   **API:** OpenStreetMap Nominatim for geocoding

## Project Structure

The project consists of a full-stack implementation with frontend pages, backend API endpoints, and database scripts.

*   **Core Application Pages:**
    *   `index.php`: The public landing page.
    *   `registrazione.php`: The main registration page to choose an account type.
    *   `login.php`: User login page.
    *   `homepage.php`: The user's main dashboard and social feed after logging in.
    *   `user.php`: Public view of another user's profile.
    *   `message.php`: The direct messaging/chat interface.
    *   `userPost.php`: A page for a user to view and manage their own posts.

*   **Backend API (PHP scripts):**
    *   `registrazione_calciatore.php` / `registrazione_societa.php`: Handle the registration logic for players and clubs.
    *   `getPostHome.php`, `getPostUser.php`: Fetch posts for the homepage feed and user profiles.
    *   `follow.php` / `unfollow.php`: Manage the follow/unfollow actions.
    *   `inviaMessaggio.php` / `getMessage.php`: Send and retrieve chat messages.
    *   `getNearestPlace.php`: Finds nearby users based on location.
    *   `topProfile.php`: Retrieves the most followed profiles.
    *   `prendiDati.php`, `prendiRuoli.php`: Fetch profile and role data from the database.

*   **Database & Design Files:**
    *   `my_giovannimapelli10.sql`: SQL dump of the database schema and sample data.
    *   `modello_relazionale_database.PNG`: An image of the database relational model.
    *   `UML.drawio`, `casiuso.drawio`: UML and Use Case diagrams for the project.

## Database Schema

The database is structured to handle the distinct roles of players and clubs, their interactions, and the content they generate.

![Database Relational Model](modello_relazionale_database.PNG)

Key tables include:
*   `calciatori`: Stores player-specific data.
*   `societa`: Stores club-specific data.
*   `post_calciatori` & `post_societa`: Contain posts made by players and clubs.
*   `follow_calciatori` & `follow_societa`: Junction tables to manage the follow relationships.
*   `messaggi`: Stores all chat messages between users.
*   `ruoli`: A list of possible football roles (e.g., Portiere, Difensore).
*   `calciatori_ruoli` & `societa_ruoli`: Link players and clubs to their specific positional roles.
