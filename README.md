# SaveAPlate Zimbabwe — MVP prototype

This is an early UI prototype for a Zimbabwe food-rescue marketplace, packaged as a lightweight Android WebView app. It includes demo food listings, search and offer-type filtering, local demo reservations, and a business listing form.

## Important limitations
- All listings are sample data, not real participating businesses.
- Data is stored only on the current device/browser using localStorage.
- It does not yet have user accounts, a shared cloud database, verified payments, notifications, location services, or production food-safety workflows.
- Reservations are demonstrations only; no food order or payment is sent to a business.
- Do not use this prototype for real food transactions until backend access controls, reservation concurrency, privacy, payments and safety procedures have been implemented and tested.

## Build an Android debug APK with GitHub Actions
1. Create a GitHub repository and upload the contents of this folder (the files inside `saveaplate-mvp`, not the containing folder itself).
2. Push the default branch as `main`.
3. Open the repository's **Actions** tab and select **Build SaveAPlate Android APK**.
4. Click **Run workflow** if it has not started automatically.
5. When the run finishes, open it and download the `SaveAPlate-debug-apk` artifact.
6. Extract the downloaded ZIP; it contains `app-debug.apk`. Transfer it to your Android phone and install it. Android may ask you to allow installs from that source.

The APK generated this way is a debug build for testing, not a signed release for Google Play.

## Local build
Requirements: JDK 17, Android SDK with platform 35 and build tools, and Gradle 8.9 or compatible with Android Gradle Plugin 8.7.3.

From this folder run:

```bash
gradle assembleDebug
```

Output: `app/build/outputs/apk/debug/app-debug.apk`.

## Prototype features
- Discover page with discounted and free demo offers
- Search and filter
- Reservation flow and collection code
- Business-mode listing form
- Device-local persistence
- Android app shell that works offline

## Suggested next production steps
1. Add Supabase Auth and database with row-level security.
2. Move listings and reservations from localStorage to the backend.
3. Make reservations atomic to prevent overbooking.
4. Add verified business onboarding, reporting and admin tools.
5. Integrate an authorised payment provider and verify server-side payment callbacks.
6. Implement safe-food listing policy, moderation and applicable local compliance.
