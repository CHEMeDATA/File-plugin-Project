# File-plugin-Project
Discussion of a generic chemistry files parser and metadata generator.

## Identified files

We shall call an CHEMaDATA file type, a file which is recognized by a CHEMaDATA plug-in. The role of the plug-in is to parses the file and extract usefull data/metadata used to:
- identify the object(s) found in the file.
- generate a data json including the content of these object(s). This used for processing, visualization, etc.
- generate a manifest json including the data/metadata for these objects. This is used for Findability, registration, etc.
- optionally the manifest my include link to object visualizer (located in separate repository).
- optionally the manifest my include link to object converter (located in separate repository).
 Each plug-in has a specific repository allowing version control, etc.

Each object type has a json schema used to generate the manifest json and data json.

### Examples:

#### Chemistry mol file

The *mol* files may include one or more structures.
Each structure may be a 2D "flat" or 3D structure. (may be mol 2000, mol 3000 ?)

**IMPORTANT HERE**: There is no  1 file / 1 Object relation. On file may have multiplet object of different types....

#### Bruker NMR 1r file

The 1r file are processed NMR spectra.

They may correspond to different isotopes, Larmor frequency etc. (parameters found in separate files)
A 1r file may be:
- 1D spectra
- cross-section through a 2D spectrum (F1 or F2, in which case it has a row/col index)
- projection?

A core of metadata will be common to all types (isotope, spectral with, larmor frequency), others will be type specific (column index).

