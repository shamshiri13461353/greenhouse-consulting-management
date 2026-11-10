# Greenhouse Consulting — Management Portal

Independent management frontend for the greenhouse consulting platform.

- Frontend: static HTML hosted with GitHub Pages.
- Backend: existing Supabase project (shared with grower and expert environments).
- Entry page: `index.html`
- Expert invitation acceptance: `accept-invitation.html`
- Grower invitation / password recovery: `accept-grower-invitation.html`

## Security

The browser uses only the Supabase publishable key. Never add a service-role or secret key to this repository. Authorization remains enforced by Supabase authentication, role checks, database policies, and Edge Functions; hiding a page is not an access-control mechanism.

## Deployment

GitHub Actions deploys the repository root to GitHub Pages. In repository Settings → Pages, select **GitHub Actions** as the build and deployment source.

The reset-password redirect in the admin page points to this site's `accept-grower-invitation.html`. The Supabase Auth redirect allow-list must include this URL before password recovery is tested here.

Expert invitation emails must also be configured to redirect to this site's `accept-invitation.html`; this depends on the existing Supabase Auth / Edge Function redirect configuration and is not changed by this repository deployment.
