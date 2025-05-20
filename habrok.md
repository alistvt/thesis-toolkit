# 🦅 Hábrók mini-wiki

Hábrók original Wiki is very big, so I understand if you as a lazy student don't want to read it all. (I'm kidding, I don't accept lazy students!)
Therefore I write this little Wiki for you to help you jump into the meat of the project rather than wasting lots of hours on the documentation.
But this is the way I do it and I'm comfortable with it, so maybe you find a better way and then tell me, maybe we decide to update this page!

## How to upload my code?
In Hábrók Wiki they recommend to connect to a ftp protochol, etc.
I recommend you use your GitHub for it. Here is how to do:

[1] make a github repository for your project
[2] share it with me! (repo settings -> collaborators -> ...)
[3] make a fine-grained token for this repository:
  - profile settings -> developer options -> fine-grained token -> select the project
  - grant the repository permissions -> contents -> read and write
  - save your token
[4] connect to habrok in ssh
[5] clone your repository:
  - `git clone https://oauth2:<your-fine-grained-token>@github.com/owner/repo.git`

Now you will have your code in Habrok. You can modify your code through your local editor (like VsCode) and push it to github, then go to Habrok pull the changes, or vice versa.

## Running and setting up python


## GPU Jobs

### Creating a Job
You need to make a file like `<JOB-NAME>.sh` and inside the file you mention what you want to do.
If you need a GPU Job and want to use `transformers` package, the following code would do the most for you:

```
#!/bin/bash
#SBATCH --time=00:60:00
#SBATCH --partition=gpu
#SBATCH --gpus-per-node=v100:1
#SBATCH --mem=40GB

export ="/scratch/$USER";
export HF_HUB_CACHE="/scratch/$USER";
module load PyTorch/2.1.2-foss-2023a-CUDA-12.1.1;
source ~/envs/<ENV-NAME>/bin/activate;

cd /scratch/$USER/<PROJECT-DIRECTORY>;
python <YOUR-PYTHON-FILE>
```

💡 Here are the things you need to know:

- remember to modify the time if you need
- time between 0 to 4 hours are categorized into short jobs and will be executed faster, then until 24 hours are medium jobs, and after that is considered long jobs.
- gpus-pernode can take two options: a100 or v100. a100 has 40GB or GPU memory and v100 has 32GB. So if you encounter memory issues change it.

### Job actions
- you can submit your job with `sbatch <JOB-NAME>.sh`
- you can view the status of your job with `squeue -u $USER` or through the Hábrók web gui.
- you can view all of the jobs with `squeue` command. maybe you want to see what jobs your friends are running. the name of a job sometimes says a lot.(😈)
- cancelling jobs: I don't know the command! I do it through web GUI.
- when your job starts running, an output file is generated (at the location that you submitted the job). it's named like `output_<TIMESTAMP>.out`.
- you can change the name and location of that output file. (I won't tell you how. figure out yourself.)
