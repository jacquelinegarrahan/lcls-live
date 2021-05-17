# User Environment


- A compiled Bmad distribution, and enabled 
- Python 3.7 or greater environment with:
    - `pyepics`
    - `pytao`

- `$LCLS_LATTICE` environmental variable pointing to the LCLS-Lattice files
- `$ACC_ROOT_DIR` environmental variable pointing to the Bmad installation
- EPICS installation (for live PVs)
- Archiver access (for archived PVs)


## LCLS Production

Enable Bmad and and LCLS-Lattice:
```bash
source /usr/local/lcls/package/bmad_distributions/enable
```

## SLAC Public

This is for public linux machines such as:

- `centos7.slac.stanford.edu`

Enable Bmad and and LCLS-Lattice:
```bash
source /u/ad/cmayes/nfs/bmad_distributions/enable
```

## SLAC SDF

This is for SDF machines such as:

- `sdf.slac.stanford.edu`

Enable Bmad and and LCLS-Lattice:
```bash
source /gpfs/slac/staas/fs1/g/g.beamphysics/cmayes/bmad_distributions/enable_sdf
```

## Laptop

Install Bmad according to the official [Instructions](https://wiki.classe.cornell.edu/ACC/ACL/OffsiteDoc)
    
### Configuring remote access to EPICS and Archiver

`lcls-live` is packaged with tools for configuring remote access to both archiver and EPICS process variables. Both depend on environment variables for configuration.

For EPICS, these variables are:

| Variable            | Description                          |
|---------------------|--------------------------------------|
| CA_NAME_SERVER_PORT | Port for forwarding                  |
| LCLS_PROD_HOST      | Production host of process variables |
| SLAC_MACHINE        | Public SLAC machine for forwarding   |
| SLAC_USERNAME       | Username passed to ssh               |

The archiver requires:

| Variable           | Description                |
|--------------------|----------------------------|
| SLAC_ARCHIVER_HOST | SLAC archiver host machine |
| SLAC_USERNAME      | Username passed to ssh     |


The archiver and EPICS connections may be started using:  

"""
$ configure-archiver-remote
$ configure-epics-remote
"""
