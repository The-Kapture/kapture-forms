# Kapture Forms: positioning

**Kapture Forms is the free way to build onboarding forms that ask one thing at a time.** Conditional steps,
progressive disclosure, branching and lead capture, previewed live and exported as one HTML file. It is free because
it is how people meet Kapture: every export makes a member, every form is styled with Komponents, and every form
that needs wiring is a Kapture job.

Decided 27 Oct 2026 (Rodney: "reposition and rebrand it as a free tool that solves onboarding form logic").

## Assessment of what existed

The `kapture-forms` repo (The-Kapture/kapture-forms) is a Next.js marketplace for paid compliance form packs, with its
own Supabase and Stripe, a £29 price floor and a 70/30 publisher programme. It has one live pack (UK care staff
onboarding, with kooper · care). Its CLAUDE.md says it is served from the kooper-care deployment and needs its own
accounts to run alone. A marketplace of regulated packs needs publishers, editorial review and per-sector compliance
before it earns; the onboarding-logic problem underneath it is universal and can be solved now, inside Studio, on
infrastructure that already runs.

## The new shape

| | Before | Now |
|---|---|---|
| Promise | Regulator-mapped compliance packs | Onboarding forms that ask one thing at a time |
| Price | £29 per pack, £29 a month hosted | Free; export needs a free Kapture account |
| Where | Separate Next.js app, own Supabase and Stripe | Kapture Studio app, `/app/forms` |
| Job | A product to sell | A lead magnet that feeds Komponents, Studio Plus and Kapture services |
| Compliance packs | The product | A later premium layer, if the marketplace is revived |

## Who it is for

Agencies, consultants, studios and small service businesses who onboard clients through a contact form that asks
everything at once. Their problem: long forms lose people, and conditional logic is either missing or locked in a
paid form tool.

## What ships (live in this branch)

- `/app/forms`: three templates (client onboarding, lead qualifier, event registration) plus blank; steps and
  questions edited in place; "Only show if" branching on any earlier answer; live preview; warnings when a form cannot
  capture a lead (no email on a step everyone sees), has a broken branch or an insecure address.
- Export: one self-contained HTML file on the Komponents multi-step runtime, posting answers as JSON to the owner's own
  https endpoint (CRM webhook, Zapier, Make, a form backend). Copy as JSON too. Both sit behind the free-account gate.
- Cross-sells under the builder: style it with Komponents, wire it with Ask a pro, have Kapture build the journey on
  thekapture.com.
- SEO: SoftwareApplication (free) and FAQPage structured data, sitemap entry, footer and launcher links, and a card on
  `/website-komponents`.

## Funnel

1. Search or a link brings someone to a free form tool.
2. They build a form; export asks for a free Kapture account (lead captured, member created in Wix).
3. The form ships with "Made with Kapture Forms" in its source and Komponents tokens: restyling leads to the
   configurator, then a Komponents licence or Studio Plus.
4. "Wire it into your CRM" books Ask a pro; complex journeys go to Kapture's build offers on thekapture.com.

## Brand

"Kapture Forms", carrying the Kapture name as Studio does (rule 6 of "Kapture pricing, offers and brand story"). One
typeface and the Studio colours in the app; exported forms are deliberately neutral (Graphite theme) so they belong to
the owner.

## Next

- Save forms to the member's account (a Wix CMS collection, like SkriptsScripts), so they can be edited later.
- A hosted endpoint option that drops answers into the owner's Wix CRM (needs Rodney's go-ahead: it handles other
  people's personal data).
- Decide the future of the paid compliance marketplace in `kapture-forms`; its positioning note points here.
