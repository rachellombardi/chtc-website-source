


HTC Getting Started Summary
====================================

<b>Step One</b>

<details>
<summary>Learn the High Throughput Computing Strategy</summary>
<br>
Like nearly all large-scale compute system, users of both CHTC's High Throughput Computing and High Performance systems prepare their computational work and submit them as tasks called "jobs" to run on execution points. 
<br>
   <br>
High Throughput Computing systems specialize in running many small, independent jobs (< ~20 CPUs/job). On the other hand, High Performance Computing systems speicalize in running a few, very large jobs (~30+ CPUs/job).
<br>
   <br>
It is best to keep this distinction in mind when setting up your jobs. On the HTC system, smaller jobs (i.e., those requesting smaller amounts of CPU, memory, and disk resources per job) are easier to find a slot to run on. This means that users will notice they will have jobs start quicker and will have more running simultanioutsly. It is almost always beneficial to break up your analysis pipeline into smaller pieces to take advantage of getting more jobs up and running, quicker. 
<br>
   <br>
Unlike the High Performance System, CHTC staff do not limit the number of jobs a user can have running in parallel, thus it is to your advantage to strategize your workflow to take advantage of as many resources as possible. 
<br>
   <br>
More detailed information regarding CHTC's HTC system can be found in our overview guide: ----- 
</details>


<b>Step Two</b>

<details>
<summary>Log on to a an HTC System Access Point</summary>
<br>
Once your request for an account has been approved by a Research Computing Facilitator, you will be emailed login information.
<br>
   <br>
For security purposes, every CHTC user is required to be connnected to either a UW-Madison internet network or campus VPN and to use two-factor authenticaiton when logging in to your CHTC "access point" (also called a "submit server").  
<br>
</details>


<b>Step Three</b>

<details>
<summary>Learn to Submit HTCondor Jobs</summary>
<br>
Computational work is run on the CHTC's execution machines by submitting it as “jobs” to the HTCondor scheduler. Before submitting your own computational work, it is necessary to understand how HTCondor job submission works. The following guide is a short step-by-step tutorial onhow to submit basic HTCondor jobs: Practice: Submit HTC Jobs using HTCondor. <b>It is highly recommended that every user follow this short tutorial as these are the steps you will need to know to complete your own analyses.</b>
</details>

<b>Step Four</b>

<details>
<summary>Access your Data on the HTC system</summary>
<br>
<b>Upload data to CHTC</b>
When getting started on the HTC system, it is typically necessary to upload your data files to our system so that they can be used in jobs. For users that do not want to upload data to our system, it is possible to configure your HTCondor jobs to pull/push files using `s3` file transfer, or pull data using standard unix commands (`wget`). 
<br>
To learn how to upload data from different sources, including your laptop, see: 
   <br>
Transfer Files between CHTC and your Computer
   <br>
Transferring Files Between CHTC and ResearchDrive
   <br>
Using Globus to Transfer Files to and from CHTC
   <br>
Remotely Access a Private GitHub Repository

When uploading data to the HTC system, users need to choose a location to store that data on our system. There are two primary locations: /home and /staging. 
<br>
/home is more efficent at handling "small" files, while /staging is more effient at handling "large" files. For more information on what is considered "small" and "large" data files, see _____. 
<br>
</details>

<b>Step Five</b>

<details>
<summary>Install your Software</summary>
<br>
Our “Software Solutions” guides contain information about how to install and use software on the HTC system.
<br>
<br>
<b>Software Containers</b>
In general, we recommend installing your software into a "container" if your software relies on a specific version of R/Python, if your software has many dependencies, or if it already has a pre-existing container (which many common software packages do). There are many advantages to using a software container; one example is that software containers contain their own operating system, users with software containers have the most flexibility with where their jobs run on CHTC or the OSPool.
<br>
<br>
<b>Use Pre-installed Software in Modules</b>
CHTC's infrastructure team has provided a limited collection of software as modules, which users can load and then use in their jobs. This collection includes tools shared across domains, including COMSOL, ANSYS, ABAQUS, GUROBI, and others. To learn how to load these software into your jobs, visit ______.
<br>
<br>
<b>Access Software Building Tools: Log into Software Building Machines</b>
The HTC system contains several machines designed for users to use when building their software. These machines have access to common compilers (e.g., gcc) that are necessary to install many software packages. To learn how to submit an interactive job to log into these machines to build your software, see _____.  

Conda environments: It is possible to install software using miniconda.
<br>
</details>

<b>Step Six</b>




<details>
<summary>Prepare and Run one Test Job</summary>
<br>
Once your data and software are ready, up next is preparing an HTCondor submit file for one test job for your analysis. 
<br>
   <br>
It is important to run test jobs to make sure that your jobs are running as expected and producing the correct output. Additionally, many users are unsure of the amount of resources (memory, disk, number of cpus/gpus, maximum runtime limits) to request for their jobs; thus looking at the outputs of the `.log` file created at the end of jobs is very helpful for estimating future resource requests. By running a small amount of test jobs, it allows quicker troubleshooting and ensures your user priority is not lowered due to a large number of jobs going on hold for preventable reasons. 
<br> 
   <br>
While running your test jobs, make sure that your <code>/home</code> and <code>/staging</code> quotas are sufficient for when you are ready to scale out your analsys and make sure you like your organizatinoal system for the input/output files. Many users implement HTCondor features such as <code>initialdir</code> or <code>transfer_output_remaps</code> to help them save output results into specific "results" folders to make finding important files easier. 
<br>   
</details>

<details>
<summary>Submit Many Jobs by Adjusting your Submit File</summary>
<br> 




After following this tutorial, we <b>highly recommend</b> users review the "Easily Submit Multiple Jobs" guide to learn how you can configure HTCondor to automatically pass files or parameters to different jobs, return output to specific directories, and other easily automated organizational behaviors. 








