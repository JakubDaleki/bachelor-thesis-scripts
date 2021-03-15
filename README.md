The goal of the project was to localize marker on image.

![Image of marker](https://github.com/JakubDaleki/bachelor-thesis-scripts/blob/main/Znacznik_v2.png =250x)

For this purpose I trained and tested various deep neural networks. For labeling dataset I created tool called "labeler.py" which is placed in tools directory, along with other helpful scripts for augmentation and preparing data.

The first approach was object detection based. The goal was to return vector of 8 (x, y) pairs of special artifacts of markers. For this purpose I used resources provided in object_detection directory.
Due to the fact, it could be a little bit less intuitive for neural network to learn returning a vector and results of neural networks were not satisfying, I decided to try segmentation. For this approach I created a script (generate_output_mask.py in tools), which transformed vector of 8 (x, y) pairs into mask of objects (circles and rectangles). This approach was much more accurate, but more computationally expensive. All resources needed for training are available in object_segmentation directory.
