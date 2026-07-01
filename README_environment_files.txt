README — Computational Environment Files
==========================================

These two files were drafted to satisfy Reviewer Comment 5 (computational
environment / dependency manager) and are intended to be deposited in the
GitHub repository (https://github.com/Ning-lab-repo/Multimodal-MDD-UKB)
alongside the analysis code.

1. requirements.txt
   - Pins the Python package versions that are explicitly stated in the
     manuscript Methods (LightGBM 4.5.0, scikit-learn 1.5.2, SciPy 1.14.1,
     SHAP 0.46.0, lifelines 0.29.0, NetworkX 3.2.1), under Python 3.10.16.
   - IMPORTANT: this file lists only the packages named in the manuscript.
     Before final submission/deposition, regenerate it from the actual
     analysis virtual environment with:
         pip freeze > requirements.txt
     so that all transitive dependencies (pandas, numpy, etc., with their
     exact pinned versions) are captured, not just the top-level packages.

2. renv.lock
   - A skeleton lockfile for the R environment used for the KEGG /
     clusterProfiler pathway enrichment analysis, targeting R 4.4.1 and
     clusterProfiler from Bioconductor.
   - IMPORTANT: the exact clusterProfiler/org.Hs.eg.db versions and package
     hashes here are placeholders, since the manuscript text does not state
     a specific clusterProfiler version. Before deposition, regenerate the
     real lockfile from the actual R analysis project with:
         renv::init()
         renv::snapshot()
     which will record the exact versions and hashes actually used.

Once regenerated with the real environment, update the manuscript's
"Code Availability and Computational Environment" / "Data availability"
text if the recorded versions differ from those currently stated in the
Methods (e.g., if clusterProfiler's version needs to be added explicitly).
