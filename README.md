# A-Neo4j-Based-Knowledge-Graph-for-Drought-and-Food-Insecurity-Early-Warning-system
Knowledge Graph-Based Drought and Food Insecurity Early Warning System
Reading the report and the Cypher appendix first, so the README reflects your actual graph design and queries.

Almost done: I've written the README and am now saving the files and notes.

I've written the README for the DroughtKG project and copied your Neo4j Browser screenshots into an `images/` folder under clean names. It sits in a `DroughtKG/` subfolder so it doesn't overwrite the earlier README.

**What the README contains:**
- Motivation and key features.
- The graph model: a Mermaid schema diagram, your `db.schema.visualization()` screenshot, and a relationship-semantics table.
- A table of the 15 datasets with row counts and properties, plus the node and relationship counts (894 nodes, 1,474 relationships).
- Setup and build steps for Neo4j Desktop, with a warning that Phase 1 wipes the database.
- Example Cypher queries and the 5.23 risk-score rules.
- The visualization gallery, future work, citation and license placeholder.

**Things to check before you push:**
- **Repo layout:** your script loads the CSVs from `raw.githubusercontent.com/BONANASSER/DroughtKG/main/...`, so the README says to keep them at the repo root. It also expects the Cypher script at `cypher/drought_kg.cypher` and the report at `docs/`. I can extract the script from the appendix .docx into that file if you want.
- **Data provenance:** neither document says where the 15 CSVs came from or whether they are real or synthetic. I left a hidden `<!-- TODO -->` comment in the Datasets section for you to fill in. A reviewer will likely ask about this.
- **Script issues I listed under "Known Limitations":**
  - Query 5.24 uses `c.ndvi_previous`, which isn't in the schema, so every row comes out `STABLE`.
  - Severity values differ between queries: `'High'` in 5.5 and 5.6, `'Severe'`/`'Extreme'` in 5.22 and 5.23.
  - `AFFECTS`, `INDICATES` and `CAUSES` are region-and-year joins, so they are not validated causal links.
- **Report leftovers:** the report still has drafting text, including "(Insert Neo4j graph screenshot here.)", a "Figures to include" list, and an IEEE style note.
- **Naming mismatch:** the report says `WaterResource`, but the script and schema image use `WaterSource`. The README follows the script.
- I didn't use the second schema screenshot (`CALL_db_schema_visualization___visualisation.png`) because it duplicates the one I included.

Files are in /mnt/user-data/outputs/DroughtKG:
- README.md
- images/kg-overview.png
- images/schema-visualization.png
- images/reasoning-chain.png
- images/reasoning-paths-by-region.png
- images/ngo-programs-regions.png
- images/ngo-support-region-network.png
- images/region-agriculture-crop.png
- images/west-arsi-neighbourhood.png
