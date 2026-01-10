# Jabberwocky Voron Tap Mods (User_Mod/<your-folder>)

This folder contains two Voron Tap adapter variants and an insert-placement diagram for the generic adapter. Use the files and instructions below to print, install, and (for the Chaotic Labs variant) modify wiring safely.

Files included
- `Jabberwocky CNC VORON TAP adapter.stl` — Generic Voron Tap adapter (requires two 3 mm inserts; see PDF)
- `Jabberwocky NH36_Mounting_Bracket for ChaoticLabCNCTapPobe.stl` — Chaotic Labs / NH36-specific mounting bracket and adapter (wiring-aware)
- `Jabberwocky CNC VORON TAP Adapter.pdf` — Insert location diagram (shows where to place the two 3 mm inserts)
- `README.md` — This file

Which file to use
- Use `Jabberwocky CNC VORON TAP adapter.stl` for a standard Voron Tap installation. This model requires two 3 mm inserts per the PDF.
- Use `Jabberwocky NH36_Mounting_Bracket for ChaoticLabCNCTapPobe.stl` when installing on a Chaotic Labs Voron tap where the Chaotic wiring interferes with the generic adapter. This variant requires wiring modification per the NH36 wiring diagram (see “Wiring modification” below).

Important safety note — wiring & power
- Do not perform any wiring work while the machine is powered or connected to mains.
- If you are not comfortable working with electronics, ask a qualified person to do the wiring changes.
- The Chaotic Labs variant requires wiring changes according to the NH36 wiring diagram. This README contains high-level guidance; explicit wiring steps will be added once the NH36 wiring diagram / pin mapping is reviewed.

Wiring modification — required reference documents
To modify the TAP cable for the NiteHawk (NH36) board you will need both documents:
- NiteHawk-36 toolboard documentation (Nightawk 36 board wiring / pinout):
  https://docs.ldomotors.com/en/Toolboard/nitehawk-36
- CNC Tap Build Guide (ChaoticLab TAP probe manual):
  https://github.com/Chaoticlab/CNC-Tap-for-Voron/blob/951225ebef3c1753b8fc599a90948c430e2c5943/Manual/CNC_VORON_TAP_V2_BUILD_GUIDE_20240222.pdf

How to use these documents together
1. Open both documents side-by-side (or print the relevant pages). Identify:
   - On the TAP manual: connector pinout for the probe end and the wire colors used in the TAP cable.
   - On the NiteHawk-36 doc: the connector pinout for the NH36 input (which pins accept probe signals, power, ground, etc.).
2. Document current wiring:
   - Photograph the existing TAP connector and cable.
   - Label each wire (numbered or color-coded) so you can map original → new locations.
3. Compare pinouts and plan the mapping:
   - For each TAP wire, determine whether it must be moved to a different pin on the NH36, require a different connector, or requires splice/retermination.
4. Prepare tools and materials:
   - Soldering iron and solder or quality crimp connectors
   - Heat shrink tubing
   - Multimeter
   - Tie wraps / adhesive mounts to secure wires
   - Replacement connector housings if required (confirm exact part number from the docs)
5. Implement the mapping carefully (power OFF):
   - Cut and reterminate wires only after confirming your mapping.
   - Use proper strain relief and insulation.
   - Securely fasten the wiring away from moving parts.
6. Verify before powering:
   - Use a continuity/multimeter check to confirm each TAP signal/power/ground is connected to the intended NH36 pin.
   - Confirm no shorts between power and ground.
7. Power on and test:
   - Power the system and test probe functions in a safe mode (manual probe tests, reduced-power checks).
   - Watch for unexpected heating, smoke, or incorrect voltages — power off immediately if detected.

Wiring-modification checklist (safety)
- [ ] Power is disconnected before any work begins.
- [ ] Wires are labelled and photographed before cutting.
- [ ] You have the correct connector housings/pins (if replacing).
- [ ] Solder joints/crimps are insulated with heat shrink.
- [ ] Continuity and voltage checks done before finalizing.
- [ ] Wiring is secured away from moving parts.

Print settings (recommended starting point)
- Material: PLA or PETG (use PETG if the part will see elevated temps)
- Layer height: 0.20 mm
- Infill: 15–25%
- Perimeters (walls): 2–3
- Print temperature: 200–220 °C (PLA) / 230–250 °C (PETG)
- Bed temperature: 60 °C (PLA) / 70–80 °C (PETG)
- Supports: minimal; enable where model shows overhangs >45°
- Orientation: Print the adapter with the main flat face on the bed (see preview in slicer)

Bed height & printer setup — IMPORTANT (applies to both variants)
- Installing these adapters often requires increased clearance between the print bed and the tap/nozzle assembly.
- For example, on an Ender 5 Plus with a standard bed a solid spacer and raising the bed to >23 mm were required to achieve correct clearance.
- After changing bed height, re-level the bed and verify Z offsets and probe/endstop behavior to avoid crashes.

Inserts — the generic adapter
- The generic `Jabberwocky CNC VORON TAP adapter.stl` requires two 3 mm inserts. See `Jabberwocky CNC VORON TAP Adapter.pdf` for exact hole locations.
- Installation notes for heat-set or press-fit inserts are included in this README.

Assembly — generic adapter
1. Clean printed parts and remove supports.
2. Install the two 3 mm inserts per `Jabberwocky CNC VORON TAP Adapter.pdf`.
3. Align adapter to the Voron Tap mount and secure with M3 screws (hand-tighten; do not overtighten).
4. Verify clearance with wiring and moving parts; re-check after first test run.

Chaotic Labs variant — overview and wiring modification
- Purpose: `Jabberwocky NH36_Mounting_Bracket for ChaoticLabCNCTapPobe.stl` repositions/mounts to avoid Chaotic Labs wiring routing.
- Follow the steps above using the two docs linked earlier to map and modify the TAP cable.

Troubleshooting
- Part won’t seat: confirm slicer scaling = 100% and measure printed dimensions. If holes are too small, open by +0.1–0.3 mm.
- Inserts won’t seat: for heat‑set inserts reduce temperature slightly or pre-warm part; for press-fit try reaming slightly larger.
- Wiring issue after install: power down, re-check wire labels and continuity. If unsure, revert changes and get assistance.
- Bed/clearance issues: if your bed requires significant raising, re-check endstop/probe offsets and Z travel limits before applying power.

Files to include in a release
- Include the two .stl files and `Jabberwocky CNC VORON TAP Adapter.pdf`.
- Add photos of the installed parts (top/bottom) and a short installation video if possible.

Credits & license
- Designer: <Your Name / GitHub handle>
- Contributors: list as needed
- License: See repository root LICENSE. If none, consider adding a license (e.g., CC BY-SA 4.0 for models).

Contact / support
- Open an issue in this repo or contact @<your-github-handle> with questions or test-fit reports.

Changelog
- v1.0 — Initial release: `Jabberwocky CNC VORON TAP adapter.stl`, `Jabberwocky NH36_Mounting_Bracket for ChaoticLabCNCTapPobe.stl`, `Jabberwocky CNC VORON TAP Adapter.pdf`, README (updated with bed height and wiring doc links)