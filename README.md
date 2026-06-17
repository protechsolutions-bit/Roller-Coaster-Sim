# Roller-Coaster-Sim

Loop Lab Arcade is a single-file, dependency-free roller coaster physics toy.

Open `index.html` in a browser to edit a smooth Bezier track, run the cart, and watch potential energy, kinetic energy, velocity, and G-force update live. The main app code, styling, markup, rendering, editor, and physics engine all live inside `index.html`.

## Controls

- Drag labelled anchor points and handles in edit mode.
- Use **+** in the sandbox tools, then click the canvas, to append a new labelled node.
- Drag empty canvas space to pan the sandbox.
- Use the mouse wheel or the sandbox **+ / −** buttons to zoom.
- Use **□** to fit the full track back into view.
- Use **Run** to start the coaster.
- Use **Reset** to restore the default hills-and-dips track.
- Adjust **Starting Velocity** to add more initial kinetic energy.
- Toggle **Stats for nerds** to reveal the formulas and current sampled track point.

## Physics Notes

The cart is locked to the spline and uses conservation of mechanical energy:

- `PE = m * g * h`
- `KE = E_total - PE`
- `v = sign * sqrt(2 * KE / m)`
- `G = ((v^2 / R) + g * cos(theta)) / g`

There is no friction. If the cart runs out of kinetic energy while climbing, its signed direction flips and it rolls backward naturally without adding extra energy. If it reaches a hard endpoint, the run settles at that terminal stop instead of bouncing forever.
