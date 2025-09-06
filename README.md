# 🔗 HTTP URL Shortener Microservice

A robust, high-performance microservice for shortening URLs, complete with real-time analytics and custom logging.

---

## ✨ Features

- **Globally Unique Shortcodes:** Generates unique, compact shortcodes for every URL.
- **Custom Shortcodes:** Users can specify a personalized shortcode for their URL.
- **Configurable Expiry:** Shortened URLs are valid for 30 minutes by default, with an option to specify a custom validity period in minutes.
- **Comprehensive Analytics:** Tracks visits and monitors URL expiry in real-time.
- **Custom Logging:** A dedicated logging middleware provides detailed insights into all incoming requests.

---

## 🚀 API Endpoints

| Method | Endpoint | Description | Request Body (JSON) |
| :--- | :--- | :--- | :--- |
| `POST` | `/api/shorten` | Shortens a URL and returns the shortcode. | `{ "originalUrl": "string", "validity": "number (optional)", "customCode": "string (optional)" }` |
| `GET` | `/api/:code` | Redirects to the original URL. | `N/A` |
| `GET` | `/api/analytics/:code` | Retrieves analytics (visits, expiry status) for a shortcode. | `N/A` |

---

## ⚙️ Setup & Installation

To get the microservice running locally, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [your-repository-url]
    cd [your-project-directory]
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Configure Environment Variables:**
    -   Set up a MongoDB database instance (local or cloud-hosted).
    -   Create a `.env` file in the root directory.
    -   Add your MongoDB connection string to the file:
        ```
        MONGODB_URI=your-mongodb-connection-string
        ```

4.  **Start the server:**
    ```bash
    node server.js
    ```

The server will now be running and accessible, ready to handle requests.

---

## 📝 Logging

All incoming requests are automatically logged using the custom middleware located at `middleware/logger.js`. This provides a transparent and auditable record of all API interactions.

---

## 📜 License

This project is licensed under the **MIT License**. For more details, see the `LICENSE` file in the root directory.
