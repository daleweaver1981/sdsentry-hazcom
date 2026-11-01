# SDSentry HazCom plugin for Claude

Look up the Safety Data Sheet (SDS) for a workplace chemical, and see whether the sheet is hosted by the manufacturer or is a third-party copy. Get a small or mid-sized workplace ready for OSHA Hazard Communication (HazCom, 29 CFR 1910.1200).

## What it includes

- **SDSentry MCP server** (`https://sdsentry.0xpi.com/mcp-sds`, no sign-in) with six free, read-only tools:
  - `find_safety_data_sheet` looks up the SDS for one named product. It returns the PDF link, says whether the PDF is manufacturer-hosted or a third-party copy, and gives the manufacturer, CAS numbers, the revision date printed on the sheet and a confidence level. If it cannot identify the product reliably, it says so and does not substitute another product's sheet.
  - `find_sds_for_inventory` runs the same lookup for a list of up to 10 products and returns one row per product. A product it could not finish within the call's time limit, or after the free per-minute lookup limit, is listed as not looked up yet, so you can send it again.
  - `search_sds` returns up to 5 matching sheets by product or manufacturer name.
  - `ghs_pictogram` explains a GHS pictogram (GHS01 to GHS09): what it means and the hazard classes it covers.
  - `hazcom_2024_deadlines` lists the compliance dates of OSHA's 2024 HazCom update, as extended by 91 FR 1695 (January 15, 2026).
  - `check_hazcom_readiness` explains the employer dates (as necessary by 20 Nov 2026 for substances and by 19 May 2028 for mixtures) and the four things a facility needs: current SDSs, GHS labels, a written program and documented training.
- **Prompts** (MCP prompts on the same server): `find-sds` (look up one chemical's SDS, with its host and printed revision date) and `hazcom-readiness` (check what your facility needs before the 2026 and 2028 dates, with a free self-audit).
- **Skills**
  - `sds-lookup` teaches Claude to fetch the real SDS before answering hazard, PPE, storage, first-aid or spill questions, and never to substitute another product's sheet.
  - `hazcom-readiness` walks an employer through a gap check, builds a chemical inventory with SDS links, and drafts a written HazCom program and a training sign-in sheet.

## Example prompts

- "Find the SDS for Clorox disinfecting wipes and tell me what PPE my cleaners need."
- "We're a 6-person dental office. Are we ready for OSHA HazCom?"
- "Here are the 12 chemicals in our shop. Build me a chemical inventory with SDS links and a written HazCom program."

## Notes

Always confirm that a sheet matches the exact product and revision you have on site. The guidance is general and is not a legal determination.

SDSentry (https://sdsentry.0xpi.com/) is SDS and HazCom management software from 0xpi (Dale Weaver, sole proprietor). The plugin and its tools are free and need no account.

Support: https://sdsentry.0xpi.com/ · Privacy: https://sdsentry.0xpi.com/privacy.html

## License

MIT
