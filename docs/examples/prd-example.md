# Notification Preferences: PRD One-Pager

**Status:** Approved

**Author:** @janedoe

**Date:** 2024-03-15

**GitHub Issue/Project:** #42

## 1. Context (The "Why")

Users receive 12+ emails per week from our platform with no way to control frequency or type. Support tickets about "too many emails" have increased 40% QoQ. Unsubscribe rates are climbing, which risks losing engaged users entirely.

## 2. Job Stories (The "Who & What")

* **Story 1:** When I receive a marketing email I don't care about, I want to turn off that specific category, so I can stay subscribed to the updates that matter to me.
* **Story 2:** When I'm onboarding a new team, I want to temporarily mute non-critical notifications, so I can focus on setup without inbox noise.
* **Story 3:** When I'm evaluating our notification system as an admin, I want to see what emails each role receives by default, so I can configure sensible defaults for my organization.

## 3. Functional Requirements

* [x] **Preference center:** A single page where users can toggle notifications by category (product updates, billing, security, marketing).
* [x] **Frequency control:** Per-category options for immediate, daily digest, weekly digest, or off.
* [x] **Mute period:** Users can snooze all non-critical notifications for 1, 7, or 30 days.
* [ ] **Admin defaults:** Org admins can set default preferences per role (deferred to v2).

## 4. Success Metrics

* **Primary Metric (The North Star):** Reduce email unsubscribe rate from 4.2% to below 2% within 90 days of launch.
* **Counter Metric (The Guardrail):** Maintain current click-through rate on critical notifications (security alerts, billing) above 35%.

Is this referenced in a planning tool?

* **Reference:** [Linear project NOTIFY-2024](https://linear.app/example)

## 5. Scope & Constraints

* **In-Scope:** User-facing preference center, per-category toggles, frequency options, mute feature.
* **Out-of-Scope:** Admin defaults (v2), push notification preferences (separate PRD), SMS channel.
* **Constraints:** Must work within existing email service provider (SendGrid). Cannot require database migration during peak hours.
* **Risks:** Users may over-mute and miss critical security notifications. Mitigation: security and billing categories cannot be fully disabled, only set to digest.

## 6. Review & Decisions

| Date | Reviewer | Decision/Feedback |
| :---- | :---- | :---- |
| 2024-03-18 | @cto | Approved. Security notifications must remain mandatory — added as constraint. |
| 2024-03-20 | @design | Preference center mockups approved. Mute UI simplified to single toggle + duration picker. |

## Appendix: Implementation Notes

* Figma mocks: [Notification Preferences v1](https://figma.com/example)
* SendGrid webhook docs: [Event Webhooks](https://docs.sendgrid.com/example)
