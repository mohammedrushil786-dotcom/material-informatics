# Material Informatics

A personal journey toward building impactful solutions at the intersection of materials science, data science, and intelligent design.

I am a first-year Materials Engineering student at VNIT Nagpur, exploring how machine learning, materials databases, and computational tools can accelerate innovation in materials discovery. This repository is a reflection of my learning process, experiments, and early projects as I work toward building a startup in materials informatics and pursuing higher studies abroad.

## Why this field?

Materials shape the future of energy, electronics, healthcare, transportation, and sustainability. Traditional trial-and-error development is slow and expensive. Materials informatics combines data-driven methods, computational modeling, and AI to discover, optimize, and predict material properties faster.

My goal is to build tools and applications that make materials research more efficient, intelligent, and accessible.

## Project focus

This repository documents my early exploration into material property retrieval using open materials databases and Python-based workflows.

- Learning how to query materials databases
- Understanding structure-property relationships
- Exploring data-driven material discovery
- Building small applications that can scale into startup ideas

---

# Silicon Property Retrieval from the Materials Project Database

This project demonstrates how to retrieve material properties from the Materials Project API using Python.

The example below fetches the band gap and density of silicon (`mp-149`).

## Setup

1. Install the Materials Project API client:

```bash
pip install mp-api
```

2. Set your API key as an environment variable instead of hardcoding it in the script.

```bash
export MP_API_KEY="your_api_key_here"
```

## Python code

```python
import os
from mp_api.client import MPRester

api_key = os.environ["MP_API_KEY"]

with MPRester(api_key) as mpr:
    docs = mpr.materials.summary.search(
        material_ids=["mp-149"],
        fields=["material_id", "formula_pretty", "band_gap", "density"],
    )

    for doc in docs:
        print(
            f"Material: {doc.formula_pretty} | Band Gap: {doc.band_gap} eV | "
            f"Density: {doc.density}"
        )
```

## Output

```text
✓ Retrieved 1 SummaryDoc documents in 0.6s
Material: Si | Band Gap: 0.6102999999999996 eV | Density: 2.3128002565764314
```

---

## What I am learning

- Python for scientific computing and data analysis
- Materials databases and APIs
- Data extraction and interpretation
- Visualization and project documentation
- Building reproducible workflows for research and product ideas

## My long-term vision

I aim to build a startup in materials informatics that bridges scientific research and practical innovation. My future work will focus on creating tools that help researchers and industries discover better materials faster, more intelligently, and with less cost.

This repository is one step in that direction.

## Future roadmap

- Explore more materials and property datasets
- Build ML models for property prediction
- Create material screening dashboards
- Develop beginner-friendly applications for materials discovery
- Turn experiments into startup-ready prototypes

---

## Connect with me

I am building my journey one project at a time — from learning the fundamentals to creating solutions with real-world impact.

This is not just a code repository; it is my digital portfolio and a record of my growth in materials informatics.
