# Tendon Transfer Planner

An interactive planner for tibialis posterior tendon transfer in foot drop. Drag the window point and the retinaculum point on the model, choose an insertion and a window height, and watch the dorsiflexion and hindfoot moments update.

## Try it

<img src="qr.png" alt="QR code that opens the planner" width="220">

Scan the code with a phone camera, or open [iressa8655.github.io/tendon-transfer-planner](https://iressa8655.github.io/tendon-transfer-planner/).

## How it works

The numbers come from the OpenSim Gait2392 musculoskeletal model with the tibialis posterior path rerouted.

- **Live mode.** On the author's computer, `platform_server.py` runs the OpenSim engine for every change.
- **Hosted mode (this site).** GitHub Pages cannot run OpenSim, so the same engine was run in advance over a grid of 9,300 routes. The page interpolates between grid points in the browser. Bend angles are calculated exactly from the model's bone frames.

The grid covers:

| Parameter | Range | Step |
|---|---|---|
| Mid-leg route | −35 to +40 mm | 2.5 mm |
| Retinaculum point | −35 to +25 mm | 2.5 mm |
| Window height | 4 and 12 cm above the medial malleolus tip | interpolated |
| Insertion | 6 sites | exact |

## Limitations

- Moments are capacity at full muscle activation, not moments during walking.
- Tendon paths are straight segments.
- The midfoot is one rigid segment with no talonavicular joint.
- The position of the retinaculum point has not been measured, and it largely sets the hindfoot direction.

For research and teaching only. Not for clinical decisions.

## Credits

Musculoskeletal model: Gait2392 by Delp, Loan, Hoy, Zajac, Topp, Rosen, Thelen, Anderson and Seth, licensed [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/). Computed with [OpenSim](https://opensim.stanford.edu/).
