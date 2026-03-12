---
title: "BOB is Getting More Reliable: The Jovian Hardfork"
slug: "bob-jovian-hardfork-op-stack-upgrade"
date: "2026-03-12"
description: "BOB Mainnet upgraded with the Jovian Hardfork, bringing a more predictable fee market and a tighter proving stack via OP Stack Upgrade 17."
author: "HighTower"
authorImage: "https://bvkmqlnhnryztqknjjah.supabase.co/storage/v1/object/public/content/news/HTW.png"
cover: "https://pbs.twimg.com/media/HDOpbgqWMAAWncO.jpg"
coverAlt: "BOB Jovian Hardfork"
tags: ["bitcoin", "bob", "l2", "infrastructure", "op-stack"]
---

# BOB is getting more reliable - here's why

BOB Mainnet upgraded today. 
Jovian Hardfork went live at 14:30 UTC as part of OP Stack Upgrade 17, and most users didn't notice a thing.

Three changes under the hood. The fault proof VM got updated to Go 1.24 via Cannon, this is the virtual machine that proves execution correctness onchain. Configurable Minimum Base Fee arrives as an option for chain operators, disabled by default: fewer priority fee auctions under load, smoother fee market overall. DA Footprint Block Limit is enabled by default, an in-protocol cap on data per block that cuts off a clean spam vector before it becomes a problem.

If you run an external node, this upgrade isn't optional. Nodes that aren't updated before activation will stop syncing. op-node at least v1.16.5, op-geth at least v1.101605.0, and --override.jovian=1773325801 on both clients.

From where we sit, this is exactly the kind of upgrade that builds long-term trust in a chain, just the foundation getting tighter. 

BOB is quietly becoming the kind of chain that doesn't make headlines for the wrong reasons - more predictable fee market, cleaner data layer, up-to-date proving stack. Not flashy, but exactly what a maturing L2 should look like.
