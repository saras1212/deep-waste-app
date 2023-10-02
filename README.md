# Deep Waste
You can find the research paper utilized in this study [here](https://www.aimspress.com/article/doi/10.3934/ctr.2023008), descriptive analysis of the data [here](https://colab.research.google.com/drive/1JPwI75T_PMlTITO3tDmIhGEVsIREnGHa?usp=sharing) and the process of developing this app [here](https://medium.com/@sumn2u/deep-learning-approach-to-manage-household-waste-via-mobile-app-4186292b266b).


## Table of Contents
[Summary](https://github.com/saras1212/deep-waste-app/blob/master/README.md#summary)
[Background](https://github.com/saras1212/deep-waste-app/blob/master/README.md#background)
[Features](https://github.com/saras1212/deep-waste-app/blob/master/README.md#features)
[How is it used?](https://github.com/saras1212/deep-waste-app/blob/master/README.md#how-is-it-used)
[Data sources and AI methods](https://github.com/saras1212/deep-waste-app/blob/master/README.md#data-sources-and-ai-methods)
[Challenges](https://github.com/saras1212/deep-waste-app/blob/master/README.md#challenges)
[What next?](https://github.com/saras1212/deep-waste-app/blob/master/README.md#what-next)
[Demo](https://github.com/saras1212/deep-waste-app/blob/master/README.md#demo)
[Available on](https://github.com/saras1212/deep-waste-app/blob/master/README.md#available-on)
[Getting started](https://github.com/saras1212/deep-waste-app/blob/master/README.md#getting-started)
[Structure](https://github.com/saras1212/deep-waste-app/blob/master/README.md#structure)
[Contributing](https://github.com/saras1212/deep-waste-app/blob/master/README.md#contributing)
[Acknowledgements](https://github.com/saras1212/deep-waste-app/blob/master/README.md#acknowledgments)
[License](https://github.com/saras1212/deep-waste-app/blob/master/README.md#license)

## Summary

An app that use [waste classification machine learning model](https://colab.research.google.com/drive/1yWqc8TRS0I21RdfHLPRTQIs37ANOx-Uq) to classify the waste and manage it effectively. It a standalone app and works without internet.

<img alt="Instructions"  src="./app_banner.png">

## Background
Waste identification is a crucial step in the waste management process that enables facilities to properly handle, recycle, and reduce their waste, while also ensuring compliance with regulations and tracking their progress over time. The integration of machine learning models with mobile devices can enhance the precision, ease, and effectiveness of waste management endeavors, as well as furnish valuable information for monitoring and decreasing waste.

In this app,  we have prepared a substantial collection of waste images and trained a machine learning model. The trained model is then installed on a mobile device, enabling real-time waste identification. By simply capturing an image of the waste with their mobile device, users can receive an instant classification of the waste into categories such as paper, plastic, glass, metal, and more, via the machine learning model.
With this approach, one can have many advantages such as:
- Convenience: By using mobile devices, waste identification can be performed anywhere, at any time, making it more accessible and convenient for users.
- Increased Accuracy: Machine learning models are trained on large datasets, which can result in improved accuracy compared to manual waste classification.
- Real-time Feedback: By using a mobile device, users receive instant feedback on the type of waste they are dealing with, allowing them to make informed decisions on how to properly manage the waste.
- Data Collection: The data collected through mobile waste identification can be used to track waste generation and management efforts over time, helping to identify areas for improvement and set new waste reduction goals.

## Features 
Here are some of its features:

📸 Snap or upload a picture of a waste <br>
📱 Install the app on your phone for easy access <br>
♻️ Learn how to recycle effectively using AI <br>
🥤 Keep track of how many waste items you've recycled<br>
🏆 Get rewarded for each managed waste <br>
🌍 Help to make our earth cleaner <br>
✨...and much more to come - all for free & no sign in needed!<br>

<a href="https://www.producthunt.com/posts/deep-waste?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-deep&#0045;waste" target="_blank"><img src="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=379129&theme=neutral" alt="Deep&#0032;Waste - Making&#0032;waste&#0032;management&#0032;fun&#0032;and&#0032;easy&#0032;&#0032; | Product Hunt" style="width: 250px; height: 54px;" width="250" height="54" /></a>

## How is it used?

After training the AI model, we export it to TensorFlow Lite for mobile device compatibility. Using the app, users take or upload a picture of their waste, which the model then analyzes and provides suggestions for waste management. When users successfully manage their waste, they receive rewards. To enhance the accuracy of the system, users can submit incorrect predictions and specify the type of waste.
## Data sources and AI methods
[Torch](https://pytorch.org) and [Keras](https://keras.io/api/applications/#mobilenet) provide the pre-trained models [DenseNet121](https://keras.io/api/applications/densenet/#densenet121-function) and [MobileNet](https://keras.io/api/applications/mobilenet/), respectively, which we utilize for our image recognition models. These models were initially trained on ImageNet. We then fine-tuned MobileNet using the [TrashNet data collection](https://github.com/garythung/trashnet) to classify garbage material.
Then resutlant model are then converted into `tflite` file, making it accessible for processing in mobile devices

## Challenges
This project classifies most of the waste but for some, it's still a problem. These images whose accuracy is less than 45 or with wrong prediction needs to be find into the model so that machine can learn from it. Besides that, some of the devices has problem running the model resulting crashing the whole application.

## What next?
The plan is to add a way to support internationlization. The language support will help to reach more people and lessen the boundries. 
## Demo
[![Deep Waste](https://img.youtube.com/vi/9hKCymDleco/0.jpg)](https://www.youtube.com/watch?v=9hKCymDleco "Deep Waste")

## Available on 
[Google Play](https://play.google.com/store/apps/details?id=com.hai.deep_waste)

[App Store](https://apps.apple.com/app/deep-waste-ai/id6445863514?platform=iphone)
## Getting started
1. Install Flutter. See https://flutter.io/setup/

2. and clone this repository.
3. Move to `deep-waste-app` directory.
4. Run `flutter run` command.

## Structure
The main classes are under `lib` directory.

directory | description

    assets
    ├── models
    # waste classification model
    lib
    ├── ...
    ├── components                   # reusable components
    ├── constants                    # constants used in project
    ├── models                     # data structure to define the shape of data
    ├── screens                    # different view used in the app
    ├── controller                    # an intermidiate between view and model responsible for updating model and manupluates the view of the app    
    ├── test                    # Test files (alternatively `spec` or `tests`)
    └── routes.dart             # maps urls for navigation
    └── ...



## Contributing

Contributions are always welcome. Feel free to report Issue or send Pull Request.

How to report an Issue: https://docs.github.com/en/communities/maintaining-your-safety-on-github/reporting-abuse-or-spam#reporting-an-issue-or-pull-request

How to issue a Pull Request:

1. Fork the repository: Click on the fork button in the top right corner of Github. This will make a copy of the repository that will be available on your personal Github space.

2. Clone the repository: Go to your fork on GitHub, click the green "Code" button, and copy the clone HTTPS link. This next step should be completed through the command line. Navigate to the folder where you want to save the project by using the command "cd". Next, run the command "git clone url", where url is the link you copied from your fork. 

3. Create a new branch: Navigate to the folder that was created by the clone by using the command "cd deep-waste-app". When creating a branch, it is very important that you create your new branch off of the master branch. To do so, first run the command "git checkout master". Next, to create your branch, run "git branch new-branch", then "git checkout new-branch". After this command you should recieve the output "Switched to branch 'new-branch'.

4. Contribute: Make changes to the existing project.

5. Commit your changes: Use the command "git add filename" to stage your modified file(s). You may also use the command "git add ." to add all files, folders, and subfolders. To learn more about "git add" check out this link: https://github.com/git-guides/git-add . Next, run the command "git commit -m "commit message"", where "commit message" is a meaningful message that allows others to understand the changes you made and why you made them. 

6. Push your changes: It is time to push the changes to the current branch of your forked repository. Run the command "git status" to make sure that you are on your newly created branch. Run the command "git push --set-upstream origin new-branch". 

7. Create a pull request: Make a pull request to the original repository. In Github, go to your forked repository and click the "Compare & pull request" button. Add in a meaningful title, a comment, and then press the “Create pull request” button.


## Acknowledgments

## License
```
Copyright 2023 Suman Kunwar

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
Feel free to reach out to us at sumn2u@gmail.com, to Suman directly if you have any questions or feedback! Hope you find this useful 💜
