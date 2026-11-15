# ZUNO Android source (starter build)

## What is included
- `www/index.html`: the existing ZUNO UI prototype, adjusted for a mobile bottom navigation and local demo-post persistence.
- Capacitor configuration and package manifest to wrap the web app as an Android application.
- `supabase/schema.sql`: initial secure-by-default database tables and row-level security policies for profiles, posts, comments, likes, follows, live-room metadata, room chat, blocks and reports.

## Important status
This is a **starter source package, not a finished production social network and not an APK**.
The current screens still contain demo interactions. Real login, cross-user chat, photo/video storage, live audio/video streaming, notifications, moderation operations, creator payments and admin tools need their respective services and implementation/testing. A real live-streaming service is not provided by Supabase alone. No fake live streams or fake earnings are presented as real.

## Android build
A computer or cloud build environment with Node.js, Java and Android SDK is required. SPCK Editor on an Android phone can edit the HTML, but it does not by itself compile a signed Android APK.

1. Install Node.js and Android Studio on a computer.
2. Unzip this project.
3. In the project folder run:
   - `npm install`
   - `npx cap add android`
   - `npx cap sync android`
   - `npx cap open android`
4. In Android Studio, build an APK for testing. For Play Store release, create and protect a signing key and complete the store's current requirements.

## Supabase setup
1. Open the existing ZUNO Supabase project.
2. Review `supabase/schema.sql` and run it in SQL Editor.
3. In a later integration step, add the Supabase Project URL and **publishable/anon key** to client configuration.
4. Never put the Supabase `service_role` key in the Android app or any public file.

## Before public launch
- Add authentication and verify account ownership.
- Add private storage buckets and strict upload limits.
- Add a real-time video provider and test camera/microphone permissions.
- Add robust moderation, reporting, appeals, block/mute and abuse response.
- Add privacy policy, terms, age-appropriate design and account deletion.
- Keep purchases, cash-out and real-money creator earnings disabled until legal, payment-provider and adult-account requirements are met.
- Test RLS policies with separate user accounts before storing real user data.
