AKSHAY PAKHARE — WEBSITE v2 — PRIVATE REVIEW BUILD
==================================================

FILES
  index.html              the whole site (one file)
  AkshayPakhare_CV.pdf    CV linked from the site
  404.html                shown for a wrong address
  robots.txt              asks search engines not to index the site
  _headers                security headers (read by Cloudflare Pages and Netlify)

Upload ALL of these files, keeping them in the same folder.

HOSTING IT PRIVATELY (Cloudflare Pages + Access, free)
  1. Create a free account at cloudflare.com. Turn on two-factor
     authentication before anything else.
  2. Workers & Pages -> Create -> Pages -> "Upload assets".
     Drag in the files above. You get an address like
     akshay-pakhare.pages.dev
  3. Zero Trust -> Access -> Applications -> Add an application ->
     Self-hosted. Point it at that address. Session duration: 24 hours.
  4. Add a policy: Action "Allow", rule type "Emails", and list the
     exact email addresses of your reviewers.
  5. Send them the link. Each person enters their email, receives a
     one-time code, and then sees the site. Nobody else gets in.

WHEN YOU ARE READY TO GO PUBLIC
  - Delete the Access policy (or set it to allow everyone).
  - Delete robots.txt and the "noindex" line near the top of index.html,
    so Google can find the site.
  - Optional: attach your own domain in the Pages project settings.

NOTES
  - The site is static HTML: no database, no logins, no server code.
  - Fonts load from Google Fonts; everything else is inside index.html.
  - The CV in this build has the home address, personal phone, personal
    email and the referees' contact details removed.
