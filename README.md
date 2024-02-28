# JLCPCB Kicad 8 CI flow
To use this, enable actions for your github repo, then add the two .yml files to your `.github/workflows/` folder. Add the `scripts` directory to the root of your repo as well.
You need to adjust the kicad_project_name to match whatever your `*.kicad_pro` is and workflow_project_dir to the directory of the project file (`.` if in root).\
It is also required to update the Archive Artifact action path to match the workflow_project_dir env variable.

The default behavior with these flows unchanged is to do design review ERC & DRC on any pushes or PRs to main, and when any PR is merged to main, it will generate the assembly documents required for JLCPCB to make and assemble the board.

The scripts directory contains the information about installing kicad, python, and any used libraries. The two python scripts are used for formatting the BOM and CPL to JLC format.
