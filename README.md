# 🚀 [GLG](https://glginsights.com/) project

## A match made in machine learning heaven: 🙋 ➡️ 🤓 linking every request to the best expert

👏  By [Ying Hu](https://www.linkedin.com/in/ying-hu-math/), [Cody McCormack](https://www.linkedin.com/in/codymccormack/) and [Cris Fortes](https://www.linkedin.com/in/crisfortes/)

## Presentation

You can see a recording of our presentation here: [GLG Project Presentation](https://youtu.be/roA-0QMAdJQ).

You can see our slide deck here:[GLG Project Slide Deck](https://github.com/LaplaceCherub/glg-project/blob/main/Presentation/FourthBrain%20MLE%20Capstone%20Presentation%20-%20GLG%20-%2020221206.pdf).

## Context

Ying, Cody and Cris are students of [FourthBrain's](https://fourthbrain.ai/) [Machine Learning Engineer course](https://fourthbrain.ai/courses/machine-learning-engineer/), cohort 9 (August-December 2022). This repository (repo) is part of our capstone project, a required deliverable from our curriculum. For that we've chosen to work on the [GLG](https://glginsights.com/) project.

## The problem

[GLG](https://glginsights.com/)'s business largely revolves around matching clients, requesting insights on a specific topic, with an expert on that topic from their large database so that they can meet by phone, video or in person. Visually: 

![GLG problem](https://user-images.githubusercontent.com/110877253/205419935-651c3d3a-972e-471f-9491-45c6426184f2.png)

Since they receive hundreds of these requests per day, we wanted to explore how machine learning could help automate and scale the process. 

## The solution

![Solution](https://user-images.githubusercontent.com/110877253/206084965-2f0e34b7-04be-46f4-879d-5620393f27f8.png)

## Data + Model

![Models](https://user-images.githubusercontent.com/110877253/206085500-43a33b64-dd34-4b34-88c4-d19f8a44d259.png)

## Demo

![Demo](https://i.giphy.com/media/GMSpp7FQSZdnXPHyfS/giphy.webp)

You can watch an HD product demo here: [GLG Project Demo](https://youtu.be/H9BZQdG0qCA).

## Results
![Results](https://user-images.githubusercontent.com/110877253/206085155-9523f20d-d83a-4e48-add1-c32d772388c2.png)

## MLE Stack

![Stack](https://user-images.githubusercontent.com/110877253/206085235-dd4101f4-9e32-417f-b98d-81f876216ecc.png)

## Future work

1. Improve the Topic Modeling: 
- Training an LDA model on a more diverse [dataset](https://components.one/datasets/all-the-news-2-news-articles-dataset/)
- Using semi-supervised learning method (SentenceTransformers + Label Propagation)

2. Expand the scope of the project: 
- Building the expert(s) recommendation model 
- Adapting our models to cover non-English languages 
  (GLG also has offices in Europe, Asia, and the Middle East)

## Deployment Instructionss

This app can be (relatively, see note 1 below) easily deployed using Docker. The instructions to deploy in the cloud or locally are the same.

- Clone this repository, either on a local machine or in a cloud instance

- Navigate to the flask_app folder

- Build the Docker image, using the command `docker build -t image_name .`

- If you don't have Docker installed locally or in the cloud instance, you will have to[install](https://docs.docker.com/get-docker/) and [activate](https://docs.docker.com/config/daemon/systemd/) the Daemon in order to build a Docker image.
  
- Run the Docker image using the command `docker run -d --rm --name container_name -p 8000:8000 image_name`
- Navigate to either your local host, port 8000, or the public IP of the cloud instance, port 8000. E.g. 127.0.0.0:8000 

**NOTE 1:** This application depends on prebuilt machine learning models that were saved using [Pickle](https://docs.python.org/3/library/pickle.html) files. The idea of Pickle files is that they can be built once and ported to any other machine. However, in testing we found that this was often not the case. If the app crashes when you try to run it, this is most likely the problem, and you need to take the steps below to remediate the issue:

  - Open Dockerfile, and remove the `#` from the 3rd line from the bottom, so that it reads `RUN python model_maker.py`

Then you can pick up from the step `docker build -t image_name .` above.

**NOTE 2**: this will slow down the Docker image build considerably, and might take up to 20 minutes, depending on your machine.

## License


MIT License

Copyright (c) 2022 Cody McCormack, Cris Fortes and Ying Hu

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
  
