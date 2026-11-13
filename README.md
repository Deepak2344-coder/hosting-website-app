# ProxiNotes site (Astro)

Static site: landing page, APK download, install guide, privacy policy and the
private **/admin** page used to manage notes.

```bash
cp .env.example .env     # fill PUBLIC_SUPABASE_URL and PUBLIC_SUPABASE_ANON_KEY
npm install
npm run dev              # http://localhost:4321
npm run build            # static output in dist/
```

The admin page talks only to the `admin-api` Supabase Edge Function using the
signed-in admin's own session token. There is no shared admin password and no
secret in this repo. Notes are NOT served from this site: they live in a
service-role-only database table and are delivered by the `get-note` function.
