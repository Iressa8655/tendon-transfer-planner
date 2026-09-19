# Tendon Transfer Planner

An interactive planner for tibialis posterior tendon transfer in foot drop. Drag the window point and the retinaculum point on the model, slide the insertion along the midfoot, choose a window height, and watch the dorsiflexion and hindfoot moments update.

## Try it

<img src="qr.png" alt="QR code that opens the planner" width="220">

Scan the code with a phone camera, or open [iressa8655.github.io/tendon-transfer-planner](https://iressa8655.github.io/tendon-transfer-planner/).

The first version is kept at [iressa8655.github.io/tendon-transfer-planner/v1](https://iressa8655.github.io/tendon-transfer-planner/v1/).

## What is new in version 2

- **The insertion slides along the midfoot.** Six sites are joined by straight lines, from the navicular through the three cuneiforms and the cuboid to the base of the fifth metatarsal. The lateral cuneiform site now sits on the dorsal surface of its bone.
- **The best insertion is marked for every route.** It is the point with the largest dorsiflexion moment arm at 14 degrees of dorsiflexion, the most the ankle needs in walking. A small plot above the slider shows the whole line, and a gold diamond marks the best point on the foot.
- **Supination and pronation on one scale.** The size of the hindfoot moment is drawn for both directions, and colour and words give the direction.
- **Three anatomical parts.** The moment is split into inversion or eversion, adduction or abduction, and dorsiflexion or plantarflexion, for the subtalar joint alone or for the ankle and subtalar joints together. The subtalar axis turns with the ankle angle, so the split changes with it.
- **Arrows for the three parts on the model**, drawn end to end so they visibly add up to the whole moment.

## How it works

The numbers come from the OpenSim Gait2392 musculoskeletal model with the tibialis posterior path rerouted.

- **Live mode.** On the author's computer, `platform_server.py` runs the OpenSim engine for every change.
- **Hosted mode (this site).** GitHub Pages cannot run OpenSim, so the same engine was run in advance over a grid of 63,550 routes. The page interpolates between grid points in the browser. The grid is split into one small file per insertion position, and only the two either side of the slider are needed to answer. Bend angles are calculated exactly from the model's bone frames.

The grid covers:

| Parameter | Range | Step |
|---|---|---|
| Mid-leg route | −35 to +40 mm | 2.5 mm |
| Retinaculum point | −35 to +25 mm | 2.5 mm |
| Window height | 4 and 12 cm above the medial malleolus tip | interpolated |
| Insertion | 0 to 5 along the midfoot line | 0.125 |

## Limitations

- Moments are capacity at full muscle activation, not moments during walking.
- Tendon paths are straight segments, and the insertion line runs straight between the six sites.
- The midfoot is one rigid segment with no talonavicular joint.
- The position of the retinaculum point has not been measured, and it largely sets the hindfoot direction.

For research and teaching only. Not for clinical decisions.

## Credits

Musculoskeletal model: Gait2392 by Delp, Loan, Hoy, Zajac, Topp, Rosen, Thelen, Anderson and Seth, licensed [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/). Computed with [OpenSim](https://opensim.stanford.edu/).
