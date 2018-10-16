1. I've made no adjustments to the spreadsheet, since in my case 1,4 GiB of RAM seems enough for the OS and Impalad isn't installed in the cluster yet.

2. The Workload Factor affects the `mapreduce.job.maps` and `mapreduce.job.reduces` Gateway Settings, and it stands for the number of single tasks (maps or reduces) that should run in one NodeManager.