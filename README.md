# material-informatics
aspiring to do a startup around the material informatics field sharing my journey abt my day to day projects how i build various  applications around this field ..


# retrieving the bandgap and density of Si from the materials project database using my unique api id given
from mp_api.client import MPRester

api_key = "**********************"

with MPRester(api_key) as mpr:
  docs = mpr.materials.summary.search(
      material_ids=["mp-149"],
      fields=["material_id", "formula_pretty", "band_gap", "density"],
  )
  for doc in docs:
    print(
        f"Material: {doc.formula_pretty} | Band Gap: {doc.band_gap} eV |"
        f" Density: {doc.density}"
    )

# the respective output of the above code is given below

Output()
✓ Retrieved 1 SummaryDoc documents in 0.6s
Material: Si | Band Gap: 0.6102999999999996 eV | Density: 2.3128002565764314
