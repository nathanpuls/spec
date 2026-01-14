# 🛠 Built.at: The Universal App Engine Blueprint

## 🌌 The Vision
Built.at is a **headless App Studio** for instantly turning abstract ideas into structured, live-hosted digital products. It bridges the gap between vision and deployment via an "Idea-to-App" AI-powered workflow.

---

## 🎨 Design System: "Minimalist Light"
A high-contrast, professional workspace designed to feel like a blank canvas.
*   **Palette:** Stark Black (`#000000`), Pure White (`#FFFFFF`), Crisp **Purple** (Studio/AI), and **Blue** (Live/Data).
*   **Aesthetic:** `0.75rem` border radii, razor-thin borders, and soft shadows over a white background.
*   **Interactions:** Instant, tactile feedback using custom minimalist modals/toasts (no browser alerts).
*   **Ghost UI:** Use "Vertical Spacing and Hairlines" for complex lists. Avoid heavy boxes; favor subtle indentation and minimalist drag handles.

---

## 🏗 Ecosystem & Infrastructure
*   **Subdomains:**
    *   `built.at`: Minimalist landing with a brief about section and App grid.
    *   `built.at/{user}/{slug}`: Public hosting for the **App**.
    *   `api.built.at/{user}/{slug}`: Headless JSON and atomic source access.
    *   `studio.built.at`: The workspace.
*   **Naming Logic:** The App Name is the source of truth; it auto-generates the lowercase, kebab-case **Slug**. Changing the name alters the public URL (triggers a warning).
*   **Discovery:** A simple public gallery where any App can be **Cloned** (forking code/content) into a user's account.

---

## 🛠 Technical Core
*   **Stack:** React (Vite) + TS (Studio), Firebase (Auth, Firestore, Storage), Tailwind CDN (Apps).
*   **Preview Communication:** Uses the **`postMessage` API** to stream JSON from the Studio state directly into the `iframe`. This enables **0-latency updates**—data changes reflect in the preview as the user types without reloading.
*   **App Anatomy:**
    1.  **Schema:** JSON structure using human-readable Keys (defined by external AI).
    2.  **Content:** Data values managed in the "Content" workspace.
    3.  **Code:** Single-file HTML/CSS/JS bundle managed in the "Code" workspace.
    4.  **Embed:** Optimized iframe-ready output.

---

## 🖱 The Studio Workspace
Controlled by a persistent **Vertical Sidebar** with four core modes:

### 1. 🤖 AI (The Generator)
Describe a vision in a centered textarea. The "Seed Engine" generates a prompt for external LLMs. 
*   **The "Inject Code" Secret Sauce:** When code is pasted via the shortcut:
    1.  **Extraction:** Scans for the `const data = { ... }` block via Regex.
    2.  **Schema Comparison:** Maps keys in code to the Schema. If a new key is detected (e.g., `track_length`), it automatically creates a new **Field Card** in Content.
    3.  **UI Sync:** Notifies the user: *"X new fields detected and added to your Content tab."*

### 2. 💻 Code (The Architect)
A dual-pane view featuring a custom-themed **Monaco Editor** (syntax highlighting: Black/White/Purple/Blue) and a high-performance **Live Preview** iframe. Includes a floating **Save** button in the bottom-right.

### 3. 📝 Content (The Manager)
*   **Visual Schema:** Management of Keys and Types (`Text`, `Number`, `Yes/No`, `List`, `File`, `Date`).
*   **Data Grid:** Spreadsheet-style input for values.
*   **Ghost Accordions (Dynamic Lists):** 
    *   **Collapsed:** Single-line text with a drag handle (left) and trash icon (right).
    *   **Expanded:** Expands vertically to reveal fields without background changes—utilizing subtle indentation and hairlines.
    *   **Auto-Sync:** Updates the data array in real-time for the 0-latency preview.

### 4. ⚙️ Settings (The Identity)
Management of Google-linked profile (name/photo), personal namespace (`@username`), and App metadata/favicons.

---

## 🗺 Implementation Roadmap
1.  **Identity:** Firebase setup, Google login, and `@username` registration.
2.  **Content Engine:** Field/Schema manager and "Ghost Accordion" implementation.
3.  **Code Engine:** Monaco integration and `postMessage` preview stream.
4.  **Studio Logic:** AI prompt generator and the "Inject Code" regex parser.
5.  **Public Proxy:** Public routing for hosted Apps and API endpoints.
