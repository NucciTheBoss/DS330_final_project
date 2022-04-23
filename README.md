# DS330_final_project
Visualizing some Spotify data!

## Launch Jupyter/Dask container on Roar

#### Step 1 - Log onto Roar

```
ssh <psu_user_id>@submit.aci.ics.psu.edu
```

#### Step 2 - Get submit node hostname

```
hostname
```

#### Step 3 - Start interactive batch job

```
qsub -I -A <allocation_name> -l nodes=1:ppn=20 -l pmem=5gb -l walltime=08:00:00
```

#### Step 4 - Get batch job node host name

```
hostname
```

#### Step 5 - Launch Jupyter server in interactivate batch job

```
singularity run ~/work/DS330/spotify-data-project.sif
```

#### Step 6 - Log into specific submit node host name

```
ssh <psu_user_id>@<submit_node_host_name>
```

#### Step 7 - Use ssh to bind batch job and submit node

```
ssh -N -f -L localhost:8889:localhost:8888 <psu_user_id>@<interactive_batch_job_host_name>
```

#### Step 8 - Use ssh to bind submit node with your local system

```
ssh -N -f -L localhost:8890:localhost:8889 <psu_user_id>@<submit_node_host_name>
```

#### Step 9 - Open Jupyter Lab in your web browser

Enter the following web address into your address bar:

```
localhost:8890
```

**IMPORTANT:** You will be prompted to enter a token passphrase before you will be allowed to use Jupyter. Copy and paste the token passphrase printed out by Jupyter in the interactive batch job into the prompt.

