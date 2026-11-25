# FORM. 0.2.0 beta

Deploy index.html and sw.js to the existing repository root. Leave all other deployment files in place. Update both users' installed apps before logging new workouts. Version labels are now beta-style (0.2.0 after 1.1.1); schema remains version 1 and existing storage keys and Drive snapshot format remain unchanged.

## New functionality
- Gym filters (chain / country / state / area / outlet), recent visits and custom gyms. Starter AF catalogue, not an exhaustive or real-time directory; add missing gyms. Official reference: https://www.anytimefitness.com/locations/ . Pelangi and AustinGreen labels supplied by user.
- Exercise/equipment catalogue, filters, previously performed/favourites and custom exercises. No fixed exercises; custom categories, freestyle, adding and removing exercises in a workout.
- Location-specific equipment profiles, unit, load convention, increment and setup notes. Give different physical machines distinct names. No cross-equipment strength conversion. Progression keyed by catalogue ID, gym, machine, unit and load convention.
- Only working-set weight and reps are entered. Valid values auto-save; blank sets do not count. Add/remove sets. Old RIR and warm-up data preserved but hidden and excluded from calculations. Legacy workout templates remain in stored data but new sessions use flexible selection. Unknown old gym/machine records stay separate and are never automatically attributed.
- Double progression suggests next load only if all comparable working sets reached top of range; actual effort is not inferred. Assisted/bodyweight/bands excluded from automatic weight increases. Direct sets are attributed to primary muscle only.
- Cloud sync/account separation and service-worker update mechanism retained. Short-lived Google access tokens still require reconnection. Conflicting snapshots still require manual resolution. No routine export; optional emergency backup retained.

## Validation and limits
Browser tests using simulated account/local storage verified legacy profile byte-for-byte on load, legacy set preservation, auto logging, finish/history, and separation of gym-specific baselines. Live Drive, mobile PWA update, account switching and multi-device conflicts require deployment tests. Older builds may reject new working sets with missing RIR; upgrade both devices before recording. Do not clear browser data or delete Drive snapshots. No paid service added.

## Deferred
Complete verified AF directory; photos of machines; structured seat/pulley settings (free-text setup notes available); saved routine templates, more detailed analytics, automatic conflict merging and cosmetic refinement.
