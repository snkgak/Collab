# Collab
Geometry + mechanical code for collaborator use ONLY.

# 1. CT_geom_fc
- CT (processing code for uCT ROI image outputs)
- geom (calculates geometric properties)
- fc (for collaborator use)

  Function: This program reads grayscale .bmp images from CT, applies a theshold,
  removes everything except the bone, fills in pores, and calculates
  relevant geometric properties. Each slice is calculated individually.
  2 Excel spreadsheets are output containing slice by slice and average
  geometric properties or profiles. A .png image is output for each bone
  within the respective folder showing the bone's profile and major/minor
  axes.
  
  Use: After CT outputs have been rotated and ROIs have been batch-processed and 
  organized, run this code to get geometry and TMD values. Geometry outputs are
  needed to run bend_bose_excelgeom_fc.
  
# 2. bend_bose_excelgeom_fc
- bend (for processing 3/4 pt bending test outputs)
- bose (from tests performed on the BOSE system)
- excelgeom (imports specimen geometry from the excel file generated by CT_geom_fc)
- fc (for collaborator use)

  Function: This program reads in geometric and mechanical information to
  calculate force/displacement and stress/strain from bending mechanical tests.
  For femora, the assumption is that bending was about the ML axis with the
  anterior surface in tension. For tibiae, the assumption is that bending was
  about the AP axis with the medial surface in tension. The program adjusts for 
  system compliance and then uses beam bending theory to convert force-displacement 
  data to theoretical stress-strain values.  Mechanical properties are calculated 
  in both domains and output to a file "specimentype_date_mechanics.csv".  It also 
  outputs a figure showing the load-displacement and stress-strain curves with
  significant points marked.
  
  Use: After mechanical tests have been performed and CT_geom_fc has been run to
  calculate geometric properties, use this code to calculate mechanical properties.

