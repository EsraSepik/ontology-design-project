# Smart Recipe Ontology (SRO) Phase 2 - GitHub and Widoco Guide

This folder contains the Phase 2 deliverables prepared for the Smart Recipe Ontology project.

## Recommended repository structure

```text
smart-recipe-ontology/
├── ontology/
│   ├── smart-recipe-ontology-v2.ttl
│   └── smart-recipe-ontology-v2.owl
├── data/
│   └── sample_recipe_data_phase2.csv
├── queries/
│   ├── competency_queries.rq
│   └── query_results.txt
├── docs/
│   └── index.html                 # Replace with official Widoco output after running Widoco
├── reports/
│   ├── SRO_Phase2_Report.docx
│   ├── SRO_Phase2_Report.pdf
│   ├── SRO_Specification_Document_v2.docx
│   └── SRO_Specification_Document_v2.pdf
└── README.md
```

## Git commands

```bash
git clone https://github.com/<username>/smart-recipe-ontology.git
cd smart-recipe-ontology
mkdir -p ontology data queries docs reports
cp /path/to/sro_phase2/ontology/* ontology/
cp /path/to/sro_phase2/data/* data/
cp /path/to/sro_phase2/queries/* queries/
cp /path/to/sro_phase2/docs/* docs/
cp /path/to/sro_phase2/reports/* reports/
git add ontology data queries docs reports README.md
git commit -m "Phase 2: extend SRO ontology, data acquisition, research integration, and specification v2"
git tag v2.0
git push origin main --tags
```

## Widoco documentation command

If Docker is available, run Widoco as follows from the repository root:

```bash
docker run -ti --rm \
  -v "$PWD/ontology:/usr/local/widoco/in" \
  -v "$PWD/docs:/usr/local/widoco/out" \
  dgarijo/widoco \
  -ontFile in/smart-recipe-ontology-v2.ttl \
  -outFolder out \
  -rewriteAll \
  -webVowl
```

If you have the Widoco JAR locally:

```bash
java -jar widoco.jar \
  -ontFile ontology/smart-recipe-ontology-v2.ttl \
  -outFolder docs \
  -rewriteAll \
  -webVowl
```

After generating documentation, open `docs/index-en.html` or `docs/index.html` and verify that all SRO classes, object properties, datatype properties, and example individuals are visible.

## Replace placeholders before submission

In the two report documents, replace `<GITHUB_REPOSITORY_URL>` and `<WIDOCO_DOCUMENTATION_URL>` with your actual GitHub repository URL and the published documentation URL.
