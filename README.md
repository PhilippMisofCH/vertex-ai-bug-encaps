## Minimal working example to reproduce error with the Vertex AI API

Container image is taken from
[https://hub.docker.com/_/python/](https://hub.docker.com/_/python/)

```bash
$ apptainer shell --no-home python_3.10.sif
$ python --version
Python 3.10.13
$ python -m venv venv/
$ source venv/bin/activate
(venv) $ pip install --upgrade google-cloud-aiplatform==1.38.1 torch==1.13 lightning==2.1.2 torchvision==0.14.0 matplotlib==3.8.2 pandas==2.1.4 wandb==0.16.1 jsonargparse[signatures]==4.27.1 rich==13.7.0
(venv) $ pip freeze > requirements.txt
(venv) $ python launch_vertex_job.py script --name hello_world_script --path ./lecture_b/hello_world_vertex_ai/hello_world_script.py --requirements asciimatics --args --text1 "hello from" --text2 google > launch.log 2>&1
```

```bash
$ apptainer version
1.2.5
$ uname -a
Linux phi 6.7.0-arch3-1 #1 SMP PREEMPT_DYNAMIC Sat, 13 Jan 2024 14:37:14 +0000 x86_64 GNU/Linux
```
