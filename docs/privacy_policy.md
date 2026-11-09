# Privacy Policy – Travel AI

**Last updated:** November 6, 2026  
**Application Name:** Travel AI  
**Package Name:** `com.amj.travelai.app`  
**Developer / Publisher:** AMJ Travel AI Team

---

## 1. Overview and Scope

Travel AI ("we", "our", or "the App") is an intelligent travel itinerary planner and assistant designed for Android devices. This Privacy Policy explains how Travel AI collects, stores, uses, transmits, and protects your information when you use our mobile application.

**Important Note on AI Features & Manual Setup:** Travel AI is designed as a client-side utility application. **We as developers do not provide any ready-to-use AI models, default API keys, or centralized backend proxy services.** All AI-powered features (such as itinerary generation, chat assistants, and recommendations) require the user to perform a manual setup of their chosen AI provider. You must supply your own API keys, credentials, and configuration.

By using Travel AI, you agree to the practices described in this Privacy Policy. If you do not agree with this policy, please do not use the application.

---

## 2. Data Collection Inventory

Travel AI is designed with a local-first architecture. Most data remains securely on your device. We categorize data handled by the app as follows:

### A. Data Stored Locally on Your Device (SQLite / Room Database)
- **Trip Itineraries & Details:** Destination city, start date, end date, travel interests, and budget preferences.
- **Saved Stops & Activities:** Manually added or AI-recommended stops, categories, addresses, day indices, times of day, sequencing positions, and activity origin metadata.
- **Agent Chat Conversations:** Chat sessions, user prompt history, AI responses, and saved recommendation snapshots.
- **Retention & User Control:** All local trip, stop, and chat data is stored exclusively in on-device SQLite databases managed by Android Room. Users maintain full control to delete individual trips, close/delete chat sessions, or clear all app data at any time through device settings or app controls.

### B. Data Stored Securely in Encrypted Preferences (BYOK Configuration)
- **Bring Your Own Key (BYOK) & Manual Provider Setup:** Because we do not provide pre-installed AI models or backend servers, all AI capabilities depend on user-configured credentials. 
- **Preconfigured & Custom Providers:** The application comes preconfigured with default API URL endpoint templates for four primary providers: **OpenAI, Groq, Ollama, and Google**. In addition, users can configure **any other provider compatible with the OpenAI API** by supplying a custom endpoint URL and API key.
- **Security:** BYOK API keys and access tokens are never stored in plaintext. They are encrypted at rest using a strong symmetric cipher (`AES/GCM/NoPadding`) backed by the hardware-enforced **Android Keystore System**. Encrypted credentials are excluded from Android Auto Backup and device-to-device transfers.

### C. Data Transmitted to Third-Party Services
- **Direct AI Provider Transmission (BYOK Model):** Travel AI does not operate a centralized backend proxy server for AI requests. When you interact with the AI assistant, your prompts, trip destinations, dates, interests, and budget are transmitted **directly from your device** over encrypted HTTPS connections to the specific third-party AI provider you have manually selected and configured (such as OpenAI, Groq, Ollama, Google, or any other custom OpenAI-compatible provider). Each AI provider processes this data under its own respective terms of service and privacy practices.
- **Geocoding & Destination Search:** When searching for destination cities or places, search queries are sent via HTTPS to the open Photon/Komoot geocoding service (`photon.komoot.io`) to retrieve location suggestions.
- **Maps & Navigation Handoff:** When tapping navigation buttons on saved stops, the app launches an Android implicit intent (`geo:` or `https:`) to open Google Maps or a web browser on your device. Location queries and navigation requests are handled entirely by the mapping application on your device; no location tracking or telemetry is transmitted to us.

### D. Diagnostics and Analytics
- **Diagnostics:** Travel AI does not collect personal telemetry, device identifiers, or analytics tracking. No third-party crash reporting or analytics SDKs (such as Firebase Analytics or Crashlytics) are bundled in the release build. Standard Android system-level crash logs remain on your device unless manually exported by you (e.g., when sending an AI response error report via your device's email client).

---

## 3. Recipients and Purposes of Data Sharing

| Recipient / Service | Data Transmitted | Purpose | Privacy & Retention Governance |
| :--- | :--- | :--- | :--- |
| **User-Selected AI Provider** (OpenAI, Groq, Ollama, Google, or any custom OpenAI-compatible provider configured manually) | Prompts, trip destinations, dates, interests, and budget. | Generating AI travel recommendations, summaries, and itineraries. | Governed by the chosen provider's independent privacy policy and data retention terms. |
| **Photon / Komoot Geocoding** (`photon.komoot.io`) | Destination search query text. | Retrieving autocomplete location suggestions for trip creation and search. | Ephemeral geocoding lookup; no persistent profiling or user tracking. |
| **Google Maps / Web Browser** (Device Intent) | Stop name and address. | Providing driving directions and map views on your device. | Handled locally by device OS and mapping application. |

---

## 4. Children and Minors Privacy

The App is intended for adults planning trips and is not directed to children. We do not collect or store personal information or traveler demographics regarding children or minors.

---

## 5. Data Security and Retention

- **Encryption in Transit:** All network requests (AI provider API calls and geocoding lookups) use strict HTTPS/TLS encryption.
- **Encryption at Rest:** Sensitive API credentials are encrypted using Android Keystore cryptographic keys.
- **Data Retention:** Data is retained locally on your device until you manually delete it or uninstall the application. Deleting a trip instantly and permanently removes all associated stops, chat sessions, messages, and recommendations from the local database.

---

## 6. User Controls and Data Deletion

You retain full control over your data:
- **Delete Trips:** You can delete any trip from the Trips screen, which instantly deletes all associated itinerary stops, chat sessions, and recommendations via cascading database rules.
- **Disconnect Providers:** You can disconnect any AI provider or delete its stored API key from the AI Settings screen, which immediately erases the encrypted credentials from device storage.
- **Clear All Data:** You can clear all app data at any time via Android device system settings (`Settings > Apps > Travel AI > Storage > Clear Data`), which completely erases all local SQLite databases and encrypted preference stores.

---

## 7. Changes to This Privacy Policy

We may update this Privacy Policy from time to time. Any changes will be posted on this page with an updated revision date. Continued use of the app after changes constitutes acceptance of the updated policy.

---
