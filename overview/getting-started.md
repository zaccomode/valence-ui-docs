---
description: 'Last updated: 4.0.0'
---

# 🏄‍♂️ Getting started

Valence is designed to be usable across  web-apps and native applications (via something like Capacitor.JS). Its functionality can also be expanded using Plugin packages, which provide novel features that may not be necessary for every developer.

## About the Core packages

```bash
npm install @valence-ui/core @valence-ui/utils
```

Valence 4 lists `react` and `react-dom` 19.1.0 as peer dependencies, so make sure your project is on React 19 before upgrading.

Valence's two core packages, `core` and `utils`, are required for all projects that use Valence. `utils` includes basic type declarations and low-level utilities, and `core` contains components, hooks, and the "meat" of the system.

{% hint style="warning" %}
**Updated in Valence 4**

Valence 4 requires **React 19**. It also replaces the `variant` prop with the [material system](../core-concepts/materials/README.md) — see the [4.0.0 update notes](../update-notes/4.0.0.md) for the full migration guide.
{% endhint %}

{% hint style="info" %}
**Updated in Valence 3**

Discipline packages have now been retired. This means that all components previously kept within the `app` package have been consolidated into the `core` package.
{% endhint %}

## About the Plugin packages

Plugin packages are completely optional packages that provide specific and sometimes niche utilities and components.

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>Valence Carousel</strong></td><td>A custom horizontal carousel component designed for maximum usability in desktop and mobile environments.</td><td></td><td><a href="../valence-plugins/valence-carousel/">valence-carousel</a></td></tr></tbody></table>
