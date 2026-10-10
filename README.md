# SWED — Shak World Entertainment Distribution

A responsive HTML/CSS/Bootstrap/vanilla JavaScript starter website for SWED.

## Included
- Premium black-and-gold public landing page
- Artist login and registration UI previews
- Icon-button social links and contact email
- Planned 80/20 royalty model presentation
- Planned African currency list with availability disclaimer
- Artist distribution agreement draft placeholder
- Placeholder Supabase client configuration

## Run locally
Open `index.html` in a browser, or use a local static server such as VS Code Live Server. Internet access is needed for the Bootstrap, Bootstrap Icons, and Google Fonts CDNs.

## Add your logo
Place your logo image at `assets/images/icons/icon.png`. The layout hides the image element if the file is missing.

## Social links
Update the URLs in the footer of `index.html` if any handle links are incorrect. The WhatsApp link assumes the Nigerian number `09167671935` maps to international format `+2349167671935`; verify before publishing.

## Supabase setup (not connected yet)
1. Create a Supabase project.
2. Configure email authentication and redirect URLs.
3. Create tables for profiles, releases, tracks and distribution submissions.
4. Enable Row Level Security and create ownership-specific policies.
5. Create Storage buckets and policies for artwork and audio.
6. The Project URL and publishable key are configured in `assets/js/supabase.js`.
7. Integrate the client into registration/login and release forms.
8. Keep all secret/service_role keys server-side only.

The login and registration forms use Supabase Auth. `dashboard.html` lets authenticated artists submit release records and upload audio/artwork to the private `swed-releases` Storage bucket. Streaming delivery, royalty accounting, payouts and admin review are not implemented yet.

## Agreement
`agreements/artist-distribution-agreement.md` is a draft placeholder only, not legal advice or a final contract. Obtain qualified legal review before onboarding artists.

## Before public launch
- Verify social URLs and contact information.
- Add and test your logo file.
- Connect and test Supabase Auth, database, Storage, RLS and admin authorization.
- Establish actual music distribution partnerships before advertising store delivery.
- Confirm payout providers, currencies, FX fees, tax and country requirements.
- Complete legal agreement, privacy policy, terms and copyright/takedown process.


## Supabase schema
The `swed_artist_profiles_and_releases` migration was applied to the connected SWED project. It creates `artist_profiles` and `releases`, enables Row Level Security, and creates a private `swed-releases` Storage bucket with per-user folder policies.
