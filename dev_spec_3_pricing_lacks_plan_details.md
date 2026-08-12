# Pricing lacks plan details — dev spec
Site: voicenotes.com · Priority 3 · High · Effort: Medium (2-5 days)

## Problem
The pricing page presents bare price points without plan names, feature comparisons, or billing frequency, forcing visitors to guess the value and actual cost.

## Evidence (from the live site)
> prices: $0 $9 /user $24 /user
> h2: Frequently asked questions

## Current state
h1: not specified; cta: not specified; notes: Prices shown as $0, $9 /user, $24 /user with no plan names or billing period.

## Required change
h1: not specified; cta: not specified; notes: Add plan names, feature lists, and billing period (monthly/annual) next to each price.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add plan names, feature lists, and billing period (monthly/annual) next to each price.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_pricing_lacks_plan_details` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
