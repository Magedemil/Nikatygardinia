# KhedmaOS Migration — نقاطي (Nikatygardinia)

This app is being consolidated into **KhedmaOS**, the unified ministry platform built on the منظومة الخادم codebase in the `Magedemil/Claude` repository. The master blueprint lives there at `docs/khedmaos-migration-plan.md` (branch `claude/khedmaos-migration-plan-m3pqyn`).

## This app's role in the migration

- **What moves:** the leaderboard/podium, personal points search, gift-store catalog, and weekly schedule — into KhedmaOS public routes under `/kids` (no login, same as today), backed by narrow public views/RPCs instead of full-table reads, and keeping the installable PWA experience.
- **Privacy change:** the public leaderboard will show first name + initial only, with a per-member opt-out — today's app exposes every child's full name, grade, and attendance history to anyone with the URL, which is being fixed by design in KhedmaOS.
- **At cutover (Cutover #5, after servant-facing modules):** this domain redirects to KhedmaOS `/kids`; installed PWAs get a service-worker redirect page prompting installation of the new app. The OneSignal app here is consolidated into a single KhedmaOS OneSignal app (device re-opt-in on first visit).
- **Known issues NOT ported:** the fabricated "N enabled notifications" social-proof counter is dropped entirely; anon key no longer ships for open table access.

See the master plan for the full phase schedule, data mapping, and rollback procedure.
