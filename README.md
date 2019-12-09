# webcam_point_features
Detection of ORB features from online webcam imges.

ORB comes from Oriented FAST and ROTED BRIEF, as the name implies, is built on the FAST key point detector and the BRIEF descriptor which has been recently developed. These two techniques have good performance at low cost.

As for the FAST detector, it is useful to find key points in defined real-time systems that coincide with certain visual characteristics, for example parallel mapping. Its operation is to start by detecting relatively fast points in the image and then the FAST system chooses a parameter, an intensity threshold between the central pixel and those in a circular ring around the center. Its drawback is that this system does not produce a corner measurement and its responses are very extensive at the edges. The solution to this problem has been to use a Harris corner measure to reorder the FAST key points. If we take into account a target number N of key points, first a threshold is set sufficiently lower to obtain more than N key points, then we can organize them according to the measure of Harris and choose the top N points. Another drawback of FAST is that it is not capable of producing multi-scale functions. To solve this problem, a pyramid must be used to scale the image and produce fast characteristics, which have been filtered by Harris. Regarding orientation, ORB uses a pyramidal structure that studies the same image at different resolutions and uses QUICK techniques to find the key points in each resolution.

As for the descriptor, BRIEF (Binary Robust Independent Elementary Features) uses a bit string of a constructed image patch from a set of binary intensity tests. BRIEF is very sensitive to rotation in the plane, so its matching performance decreases sharply when varying by a few degrees. The solution to this problem is that BRIEF should be directed following the orientation of the key points.

## Sources:

https://medium.com/@deepanshut041/introduction-to-orb-oriented-fast-and-rotated-brief-4220e8ec40cf

https://docs.opencv.org/3.0-beta/doc/py_tutorials/py_feature2d/py_orb/py_orb.html

http://www.willowgarage.com/sites/default/files/orb_final.pdf


