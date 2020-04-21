

Hadoop MapReduce Twitter-follower count code for CS6240 - Spring 2020

Code author
-----------
Srikanth Babu Mandru

Execution
---------
All of the build & execution commands are organmvn -vized in the Makefile.
1) Unzip project file.
Also, download and put the input file in the 'input' folder.
2) Open command prompt.
3) Navigate to directory where project files unzipped.
4) Edit the Makefile to customize the environment at the top.
	Sufficient for standalone: hadoop.root, jar.name, local.input
	Other defaults acceptable for running standalone.
	Provide "max" in Makefile. 
5) For running the Standalone Hadoop version, use the following command:
	make switch-standalone		-- set standalone Hadoop environment (execute once)
	make local
6) For Pseudo-Distributed Hadoop version, use the following commands: (https://hadoop.apache.org/docs/current/hadoop-project-dist/hadoop-common/SingleCluster.html#Pseudo-Distributed_Operation)
	make switch-pseudo			-- set pseudo-clustered Hadoop environment (execute once)
	make pseudo					-- first execution
	make pseudoq				-- later executions since namenode and datanode already running 
7) For AWS EMR Hadoop execution, use the following commands: (you must configure the emr.* config parameters at top of Makefile)
	make upload-input-aws		-- only before first execution
	make aws					-- check for successful execution with web interface (aws.amazon.com)
	make download-output-aws			-- after successful execution & termination
}


Input:
-------------------------
For input, Create "input" directory and place the dataset into that directory for execution



Log files description:
-------------------------
Log files are provided in "HW2/logs/" directory. I have printed the output "number of triangles" and "number of PATH2" in the bottom of syslog files.

Report file :
-------------------------
Report is placed at "HW2/Srikanth_Mandru_HW2.pdf"


Output file description:
-------------------------
For the output files, I just included the first 1000 records of the first reducer output file as 'part-r-00000-head' in output-# directories of output folder (# - represents the run number).
