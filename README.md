[![Gitpod ready-to-code](https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/DraTeots/simple_eic_tutorials)

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/DraTeots/simple_eic_tutorials/master)

```
# to install libraries
!pip install -r requirments.txt
```

# simple_eic_tutorials
Simple tutorials in python in dealing with EIC data



# Tools, books, tutorials

- [Uproot tutorial](https://www.youtube.com/watch?v=FoxNS6nlbD0)
- [Uproot totorial on GitHub](https://github.com/jpivarski-talks/2020-04-08-eic-jlab)
- [git tutorial](https://git-scm.com/docs/user-manual)
- [uproot manual](https://uproot.readthedocs.io/en/latest/)
- [awkward array](https://awkward-array.readthedocs.io/en/latest/)
- [filter by strings discussion](https://github.com/scikit-hep/uproot4/discussions/230)

### Install on your machine

- [Anaconda python](https://www.anaconda.com/products/individual)
- [Visual Studio Code](https://code.visualstudio.com/)
- PyCharm
- GitKracken for git

### File format

- [G4E output file format](https://escalate.readthedocs.io/projects/g4e/en/latest/output.html)

### How to look at ROOT file

http://jsroot.gsi.de/5.8.1/


### ToDo List

1. Send you jlab email 
2. Try play with simple.root file
3. Get coding environment working
5. Don't get stuck


### ToLearn List

1. Numpy
2. Pandas
3. Matplotlib
3. [uproot](https://github.com/scikit-hep/uproot) (to manipuate with root files)
4. [Uproot tutorial vieo](https://www.youtube.com/watch?v=FoxNS6nlbD0), [uproot tutorial repo](https://github.com/jpivarski-talks/2020-04-08-eic-jlab)
4. Read about git and github


### Planning and calendar

#### Global plan

1. Select tracks with Protons and Pi minus mesons
2. Plot track momentum and energies
3. Apply filters on where Lambda decayed, look at central and far forward part
4. Look lambda effective mass (what is effective mass, how we plot it)
5. Hit occupancy for the detector (looking at hits from proton and pion from lambda)
6. Look different beam energies

Information: 

PDG - particle data group

- [Lambda at PDG](https://pdg.lbl.gov/2018/listings/rpp2018-list-lambda.pdf)
- [PDG particle codes](https://pdg.lbl.gov/2007/reviews/montecarlorpp.pdf)

#### Local assignments

1. Selecting Protons and Pi-,
   
   to select particular particles, we will use `trk_pdg`, to plot momentums we 
us `trk_mom`. 
   `trk_pdg` for pion is -211
   `trk_pdg` for proton is 2212
   
    1. Plot distribution of all momentums (no filtering trk_mom of everything)
    2. Plot distribution of  momentums for trk_pdg==-211 and trk_pdg==2212 
    3. Create a new notebook called Lambda, and copy paste opening file, 
       getting tracks (.array() method) and plotting 1, 2
       
2. Plot Vertex Decay Z 

   1. Plot distribution of trk_vtx_z filtering that particle is a proton

3. Effective mass from Lambda (Lecture), how to plot it! 
   1. Run g4e_k_lambda_18on275_10k_l2.run.root file 
   2. Find energy for Proton and Pion: 
       - E_proton = sqrt( Proton_momentum**2 + Proton_mass**2 )
       - E_pion = sqrt(Pion_momentum**2 + Pion_mass**2 )
       - Proton mass = 0.93827 GeV
       - Pion mass = 0.1349 GeV
       - Proton and pion momentums are taken for trk_mom
   3. Effective mass of Lambda:
   ```
   MassLambda = sqrt( (E_proton + E_pion)**2 - (Proton_momentum_x + Pion_momentum_x)**2 - (..._y)**2 - (..._z)**z )
   Where 
   Proton_momentum_x, Pion_momentum_x = trk_mom * trk_vtx_dir_x
   ```
   
      
   
   
```
+---------------------+
|trk_count            |     # A number of tracks in an event
|trk_id               |     # Unique number/id of this particle inside the event
|trk_pdg              |     # Type of the particle
|trk_level            | 
|trk_vtx_x            | 
|trk_vtx_y            | 
|trk_vtx_z            | 
|trk_vtx_dir_x        |     # Track direction x,y,z
|trk_vtx_dir_y        | 
|trk_vtx_dir_z        | 
|trk_mom              |     # Track momentum
+---------------------+ 
```

### Calendar


| Day           | On Sch. | Description               |
| ------------- | ------- | ------------------------- |
| Feb Tu 9      |  +      | Project planning          |
| Feb Fr 12     |  +      | Scott status presentation |
| Feb Tu 16     |         |                           |
| Feb Fr 19     |         | Group meeting             |
| Feb Tu 23     |  +      | Task (1)                  |
| Feb Fr 26     |  +      | Task (2)                  |
| **Mar Tu 2**  |         | Task (3)                  |
| Mar Fr 5      |         | Group presentation        |
| Mar Tu 9      |         |                           |
| Mar Fr 12     |         | Results/Expected Results  |
| Mar Tu 16     |         |                           |
| Mar Fr 19     |         | Group meeting             |
| Mar Tu 23     |         |                           |
| Mar Fr 26     |         | Discussion/Conclusion     |
| Mar Tu 30     |         |                           |
| Apr Fr 2      |         | Final results to the group|
| Apr Tu 6      |         |                           |
| Apr Fr 9      |         | Presentation dry run      |

- Results/Expected Results-March 12th
- Discussion/Conclusion-March 26th
- Abstract-April 16th
- Presentation Slides-April 23rd
- Senior Research Symposium-May 12th
- Final research paper/proposal-May 14th


