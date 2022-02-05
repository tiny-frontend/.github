# About tiny frontend

## Before we start

### 👍 What tiny frontend is

- An example of implementation of a micro frontend architecture
- Aimed at solving "vertical" slicing

### 🙅‍ What tiny frontend isn't

- The One True Way to micro frontend

## Philosophy

This implementation is very inspired [by the architecture we are using at Cazoo](https://medium.com/cazoo/how-to-build-micro-frontends-with-react-271e651272bc).

Here are a few guiding principles:

- ⚛️ Use the framework (in this case React) as the runtime glue
- 😌 Host shouldn't need anything special to consume a tiny frontend
- 💪 Be typesafe
- 👀 Ensure shared dependencies are compatible at build time
- ✅ Automatic opt-in for non-breaking changes
- 💥 Manual opt-in for breaking changes

This approach works well in an environment where teams have clear domain boundaries and own their whole stack.

It is targeted at solving the "horizontal" slicing problem you can encounter in such environment:
`Team A` wants to show a component on a page owned by `Team B`.

For example:
- Consumer finance team wants to show a financing calculator on some marketing page
- Payment team want to show a payment component in the Checkout flow
- Logistics team want to let customer reschedule their order in the My Account section
- Content team deploys a Header and Footer used throughout apps on the site

However, it doesn't aim at solving the "vertical" slicing problem:
`Team A` and `Team B` own full apps on the domain, with client side navigation working between apps.
