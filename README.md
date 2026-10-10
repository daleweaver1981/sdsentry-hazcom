# SDSentry HazCom plugin for Claude

Find the manufacturer Safety Data Sheet (SDS) for any workplace chemical, and get a small or mid-sized workplace ready for OSHA Hazard Communication (HazCom, 29 CFR 1910.1200).

## What it includes

- **SDSentry MCP server** (`https://sdsentry.0xpi.com/mcp-sds`, no sign-in) with two free, read-only tools:
  - `find_safety_data_sheet` returns the manufacturer SDS PDF, manufacturer, CAS numbers and a confidence level for a named product. If it cannot identify the product reliably it says so.
  - `check_hazcom_readiness` explains the employer HazCom deadline and the four things a facility needs: current SDSs, GHS labels, a written program and documented training.
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
