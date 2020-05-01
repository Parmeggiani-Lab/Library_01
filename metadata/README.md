How to write hub_info.json
```
If you want to build the Hub_info.json and not write it by hand:
```
In the elfin/elfinpy folder there is a hubinfo_convert.py which can convert your csv into json. Make sure it is the newest version, consider downloading it from the branch.

The csv should be written as:

first line:   pdbName.pdb, oligormerisationState (as dimer / trimer), symmetric / asymmetric,
second line:  firstChainName, firstChainNfree?, firstChainCfree?, SecondChainName, …

if your chain is free at the N-term insert: N_free otherwise insert N_oligo

Example:

darp_aC2_GFP.pdb, heterodimer, asymmetric
B, darp, N_free, C_oligo, C, darp, N_oligo, C_free



```
If you want to write the json by hand:
```

general structure:

  „HubPdbName“:{
        "symmetric“:BOOL (true / false),
        "oligomer_type“:“(trimer / dimer)“,
        "component_data":{
            "chain A":{
                "single_name":"D18",
                "c_free":false,
                "n_free":true
            },
            "B":{
                "single_name":"D18",
                "c_free":false,
                "n_free":true
            },
            "C":{
                "single_name":"D18",
                "c_free":false,
                "n_free":true
            }
        }
    },


Empty structure:

  "":{
        "symmetric":,
        "oligomer_type":"",
        "component_data":{
            "":{
                "single_name":"",
                "c_free":,
                "n_free":
            },
            "":{
                "single_name":"",
                "c_free":,
                "n_free":
            },
            "":{
                "single_name":"",
                "c_free":,
                "n_free":
            }
        }
    },
