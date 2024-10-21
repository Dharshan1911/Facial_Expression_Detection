DEPENDENCIES
Hit the following in CMD/Terminal if you don't have them already installed:

pip install tensorflow
pip install opencv-python
That's it for now.

So let's take a brief look at each Step.

STEP 1 - Implementation of OpenCV HAAR CASCADES
I'm using the "Frontal Face Alt" classifier for detecting the presence of Face in the WebCam. This file is included with this repository. You can find the other classifiers here.

Next, we have the task to load this file, which can be found in the label.py program. E.g.:

# We load the xml file
classifier = cv2.CascadeClassifier('haarcascade_frontalface_alt.xml')
Now, everything can be set with the Label.py program. So, let's move to the next Step.

STEP 2 - ReTraining the Network - Tensorflow Image Classifier
We are going to create an Image classifier that identifies whether a person is sad, happy and so on and then show this text on the OpenCV Window. This step will consist of several sub steps:

We need to first create a directory named images. In this directory, create five or six sub directories with names like Happy, Sad, Angry, Calm and Neutral. You can add more than this.

Now fill these directories with respective images by downloading them from the Internet. Ex: In "Happy" directory, fill only images of happy faces.

Now run the "face-crop.py" program as suggested in the video

Once you have only cleaned images, you are ready to retrain the network. For this purpose, I'm using Mobilenet Model which is quite fast and accurate. To run the training, hit the go to the parent folder and open CMD/Terminal here and hit the following:

python retrain.py --output_graph=retrained_graph.pb --output_labels=retrained_labels.txt --architecture=MobileNet_1.0_224 --image_dir=images
That's it for this Step.

STEP 3 - Importing the ReTrained Model and Setting Everything Up
Finally, I've put everything under the "label_image.py" file from where you can get everything. Now run the "label.py" program by typing the following in CMD/Terminal:

 python label.py
It'll open a new window of OpenCV and then identifies your Facial Expression. We are done now!

Contributing Guidelines
Thank you for considering contributing to the "Facial-Expression-Detection" project!

Code of Conduct
Before you start contributing, please read and adhere to our Code of Conduct. We expect all contributors to follow these rules and maintain a respectful and inclusive environment for everyone.

Getting Started
1.Fork the Repository: To contribute, fork the main repository to your GitHub account.

2.Clone the Repository: Clone your forked repository to your local machine:

git clone https://github.com/your-username/Facial-Expression-Detection.git
3.Set Up Development Environment: Install the necessary dependencies if you haven't already. You can do this by running the following commands:

pip install tensorflow
pip install opencv-python
4.Create a Branch: Create a new branch for your contribution. Choose a descriptive name for the branch that reflects the nature of your contribution.

git checkout -b feature/your-feature-name
5.Make Your Changes: Make the necessary changes and additions in your branch.

6.Commit Your Changes: Make clear, concise, and well-documented commit messages. Reference any relevant issues or pull requests in your commits.

git commit -m "Add new feature"
7.Push Your Changes: Push your branch to your GitHub repository:

git push origin feature/your-feature-name
8.Create a Pull Request: Create a pull request from your forked repository to the main repository.
