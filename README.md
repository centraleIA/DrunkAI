# DrunkAI / "Beurrinator"

Face-Detection AI with OpenCV and VGG19 to detect drunk people in a party created by [Andreis](https://github.com/AndreisPurim). It was based on a face-mask algorithm and a webcam face detector code for google colab. Since it was created in like 5 hours on a monday before the party, it is very messy and disorganized. I'll do my best to explain the logic and files.

Basically, I created a dataset with some pictures of sober and drunk people (there is none public on the internet, so I had to do it by hand, which is why it's quite bad), added on my google drive (infinite space). With that, I got a model [Haar Cascade model with openCV](https://www.pyimagesearch.com/2021/04/12/opencv-haar-cascades/) and started to detect the faces. After detecting the faces, I'd use a VGG19 model to try to predict if said person is drunk or not. The label is created automatically by the folders. After training, I re-saved the model on drive.

Then, to use in-real time, the main notebook gets the pre-trained model from the drive and uses a JS wrapper for Python (created with IPython library) that runs on Google Colab (Kaggle doesn't allow it). The JS Wrapper gets your webcam in real time and returns the frames to the loop. There, you send each frame to be classified by the model. Finally, he returns a percentage of drunkenness and soberness.

Since the dataset is terribly small and we have way more pictures of drunk people, it is terribly biased, so I added a few (terrible) compensation with the percentage levels for drunkeness. This can be fixed with time and the correct annotation of data (maybe using CVAT or anything like that).

Anyway, there are lots of things that need to be improved, I just need time.

Hugs and kisses to all Central-IA-ns. Good luck on your studies.

### Things to do:

- Change the code to not use my personal drive.
- Create a better dataset
- Make the detection better, using the annotated dataset, maybe new models (or just use the rest of the haar cascade to classify eyes and etc...)
- Make the post-processing deleted false-detections
- Organize and comment the code.
