# Luma Extensions — StatickBoost

This branch contains the signed theme and module catalogs for Luma.

- `catalog.json` — signed theme catalog, supported from Luma 0.5.2.
- `themes/<id>/<version>.json` — downloadable theme packages.
- `modules.json` — signed module catalog, supported from Luma 0.5.4.
- `modules/<id>/<version>/Luma.Module.*.dll` — actual executable modules, downloaded separately from the application installer.

In Luma, open Extensions, choose a module and download it. A Modules button appears on the right after the first installation. It opens the installed tools. Installed modules can be used offline and can be updated, disabled or removed through the catalog.

From Luma 0.5.7 Extensions opens with separate Functions and Themes sections, each with its own installed filter and catalog refresh. VPN Reconnect and Gaming Panel require Luma 0.5.7; Monitor and Diagnostics retain their original packages and support Luma 0.5.4 or later.

VPN Reconnect is opt-in. It checks the existing VPN through its local proxy, retries after three health failures or engine exit, keeps the chosen server and application list, and respects manual disconnect. Gaming Panel stores user-selected executable paths, launches games on demand and displays the existing room's participant presence and latency. It does not alter routing or promise lower game latency.

The catalogs are signed by StatickBoost. Luma verifies publisher signatures, package size and SHA-256 before installing and again before loading code. Dependencies and signing keys are not distributed in this branch. Do not edit signed JSON files manually; regenerate catalogs with the original signing key.

Module API version: 1. The main application is the module host; it contains shared networking and interface helpers but does not contain the monitor or diagnostics module views. New module versions must preserve compatibility with the declared host API and minimum application version.
