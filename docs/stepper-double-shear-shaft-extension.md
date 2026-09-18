# ZeroG Stepper Double-Shear Shaft Extension

> Experimental note: this is not a standard ZeroG, Monolith, or Voron method.
> It is a proposed shaft-extension approach for short-shaft NEMA 17 steppers and
> has not been validated with long-term printer runtime. Treat the calculations
> below as assumptions and rough comparison work, not certified mechanical design.

## Goal

Some ZeroG-style double-shear motor arrangements want an effective shaft reach of
about 47 mm, but common NEMA 17 motors such as the StepperOnline
`17HS19-2004S1` have a 5 mm D-shaft that is only about 26 mm long.

This note documents a proposed way to extend the shaft while also giving the
outer support bearing an 8 mm surface to run on:

- Motor: StepperOnline `17HS19-2004S1`, 5 mm D-shaft, about 26 mm long
- Target effective shaft reach: about 47 mm from the motor face
- Sleeve: 8 mm OD x 5 mm ID stainless tube or bushing
- Extension: 5 mm precision dowel pin
- Suggested sleeve overlap on existing motor shaft: about 10-12 mm
- Retaining compound: Loctite 638 or Loctite 648
- Outer support bearing: 8 mm ID bearing placed over the sleeved section

## Concept

The stainless sleeve bridges the original motor shaft and the dowel extension.
The 5 mm dowel continues the shaft inside the sleeve, while the sleeve presents
an 8 mm outside diameter for the outer bearing.

```text
Motor face                                                    outer support
   |                                                              bearing
   v                                                                v

   original 5 mm motor D-shaft, about 26 mm
   =========================================
                         |<-- 10-12 mm -->|
                         |  overlap on    |
                         | original shaft |
                         v                v

                         +-----------------------------------------+
                         | 8 mm OD x 5 mm ID stainless sleeve     |
                         +-----------------------------------------+
                                          ==========================
                                          5 mm precision dowel pin

   ^ pulley area                         ^ bearing should sit where
     remains on the                      the dowel is inside the
     original shaft                      sleeve, not beyond it

   Approximate target reach from motor face: 47 mm
```

## Assembly Notes

The assembly order matters because retaining compound can trap air or hydraulic
pressure inside a close-fitting sleeve.

1. Deburr and clean the motor shaft, sleeve bore, and dowel pin.
2. Dry-fit the sleeve on the motor shaft and the dowel in the sleeve.
3. If the tube is too tight, deburr first. If it still will not slip on
   controllably, use a sharp 5.02 mm hand reamer to create a controlled slip fit.
4. Apply Loctite 638 or 648 to the motor shaft and inside the near end of the
   sleeve.
5. Fit the sleeve onto the motor shaft first, targeting about 10-12 mm overlap.
6. Wipe excess retaining compound before it reaches the bearing surface.
7. Apply retaining compound to the dowel and the open end of the sleeve.
8. Insert the dowel into the sleeve after the sleeve is already on the motor
   shaft, allowing displaced air and excess compound to escape from the open end.
9. Let the retaining compound cure fully before installing belts or applying
   radial load.

Avoid bonding the dowel into the sleeve first and then pressing the combined
part onto the motor shaft. That can trap air and compound in the blind interface
and make the parts stop short of their intended position.

## Bearing Placement

Place the outer 8 mm bearing over the section of sleeve where the 5 mm dowel pin
is inside the sleeve. Do not place the bearing outboard of the dowel-supported
region.

The sleeve should be treated as a composite section: stainless tube plus 5 mm
steel core. The bearing load should land on the fully supported part of that
section.

## Stiffness Comparison

The main mechanical reason this looks attractive is bending stiffness. A bare
5 mm shaft is relatively flexible. The proposed sleeved section behaves more
like an 8 mm composite shaft over the part where the 5 mm core is present.

Using a simple beam comparison and assuming similar steel moduli:

- A solid 8 mm shaft has about `(8 / 5)^4 = 6.55` times the second moment of area
  of a solid 5 mm shaft.
- An 8 mm OD x 5 mm ID stainless sleeve around a 5 mm steel core is roughly in
  the same range for bending stiffness in the sleeved region.
- In the earlier rough model, a sleeved arrangement with about 10 mm overlap had
  lower pulley deflection than a continuous bare 5 mm x 47 mm shaft under the
  same radial load.

These are unvalidated calculations. They are useful for comparison, but they do
not prove fatigue life, bond strength, runout, bearing fit, or printer reliability.

## Main Risks

- Runout from imperfect concentricity between the motor shaft, sleeve, and dowel
- Tube OD tolerance being unsuitable for the bearing fit
- Sleeve ID tolerance being too loose or too tight for reliable retaining-compound bonding
- Weak bond from poor cleaning, insufficient cure time, or excess gap
- D-shaft flat reducing bond area on the original motor shaft
- Bearing load landing outside the dowel-supported sleeve section
- Belt tension or pulley position differing from the assumptions used here

## Validation Checklist

Before installing in a printer:

- Confirm the sleeve OD is appropriate for the actual 8 mm bearing fit.
- Confirm the sleeve slides on with a controlled slip fit after deburring.
- Confirm the dowel has a controlled slip fit in the sleeve.
- Verify the assembled shaft reaches about 47 mm from the motor face.
- Verify at least about 10-12 mm sleeve overlap on the original shaft.
- Check visible runout with a dial indicator if available.
- Spin the bearing on the sleeved section by hand and feel for tight spots.
- Confirm the pulley still clamps securely to the intended shaft section.
- Let Loctite 638 or 648 cure fully before tensioning belts.
- Start with conservative belt tension and re-check runout, bearing feel, and
  any witness marks after early runtime.

## Status

This is a candidate method for experimenters who already understand the risks of
modifying a stepper shaft support arrangement. The more conventional solutions
remain using a proper long-shaft motor or a published ZeroG/Monolith-compatible
short-shaft double-shear arrangement that does not rely on a bonded shaft
extension.
