# Project: Use a Pre-trained Image Classifier to Identify Dog Breeds
![Screenshot from 2023-11-05 15-44-50](https://github.com/gatwirival/DogBreeds/assets/61587290/00e1b746-edd7-408b-b60a-06272572a9b1)


Image classifier to identify dog breeds by drawing upon libraries and automating scripts to solve complex problems quickly. 
This project was part of the [AI-Programming with Python Nanodregree by Udacity](https://www.udacity.com/course/ai-programming-python-nanodegree--nd089).

## Objective
- Determine the correct identification of images with dogs, regardless of breed misclassification, and distinguish non-dog images.
- Accurately classify the breed of dogs in the identified dog images.
- Evaluate which convolutional neural network (CNN) architecture, such as ResNet, AlexNet, or VGG, is the most effective for achieving both of these objectives.
- Factor in the time and computational resources required to achieve these objectives optimally, and assess if there are alternative solutions that can yield sufficiently accurate results within a more reasonable time frame.

## Specifications
#### Timing Code
Implementing Time functions.

#### Command Line arguments
Enable arch argument
```
adds command line argument for '--arch' default='vgg'
```
 Enable dogfile argument
 ```
adds command line argument for '--dogfile' default='dognames.txt'
```
Enable dir argument
```
python check_images.py --dir pet_images/
```

### Pet Image Labels
Correct Function Call
```
'in_arg.dir' is passed as an argument inside check_images.py while calling the get_pet_labels function.
```

Handling hidden files

These files can be useful for system configuration, considering them as regular input files could cause potential bugs in your program as it scales. Moreover, the origin of such bugs is often difficult to trace due to the hidden status of these files.
```py
results_dic = dict()


    for imagefile in listdir(image_dir):  
        emptystr = " "
        namelist = imagefile.lower().strip().split(".")[0].split("_")
        cleanimagefile = emptystr.join([str(item) for item in namelist if item.isalpha()])
        results_dic[imagefile] = [cleanimagefile]
            
    
    return results_dic
```
Dictionary returned is in the correct format.
```
Dictionary key and label  retrieves 40 key-value pairs. e.g:- {'Poodle_07956.jpg': ['poodle'], 'fox_squirrel_01.jpg': ['fox squirrel'] ... }
```

### Classifying Images

Correct Function Call
Appends images_dir to each value before making the function call.

`classifier(images_dir+users_key, model)`

Output Formatting
Convert the output to lower case and strip any whitespaces

Verifies and stores results in appropriate way. Displays output when the function call is made.
Appends 1 to correct label, and 0 to falsely classified values

## Classifying Labels as Dogs

Matches between Classifier and Pet Image Labels have both labels classified as "dogs" or "not dogs" as appropriate for the labels.

Non-matches between Classifier and Pet Image Labels correctly classify each label as "dogs" or "not dogs"



