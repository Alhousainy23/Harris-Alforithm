# Harris-Algorithm
# Harris Corner Detectors Algorithm Article
** 1. The math behind Harris corner detector 
Harris corner detection Algorithm depends on the canny edge detection algorithm and the amount of change (Sobel x coordinate and Sobel y coordinate) 
We use Harris corner detection for feature extraction because it detects corners in the images, and there are some algorithms to use for feature extraction and matching. Still, the best Algorithm is called the Fast Algorithm acronym for (features from accelerated segmentation test ) but we are talking at another time.
Theory: we saw that corners are regions in the image with large variation in intensity in all directions. One early attempt to find these corners was made by Chris Harris & Mike Stephens in their paper A Combined Corner and Edge Detector in 1988, so now it is called the Harris Corner Detector. He took this simple idea to a mathematical form. It basically finds the difference in intensity for a displacement in all directions(U, V) . This is expressed as below
![img](https://www.google.com/url?sa=i&url=https%3A%2F%2Fm.youtube.com%2Fwatch%3Fv%3DWyrVzTRZuXA&psig=AOvVaw06uyLB7sKQLlhp95gz9f8y&ust=1716364816621000&source=images&cd=vfe&opi=89978449&ved=0CBIQjRxqFwoTCJCliKywnoYDFQAAAAAdAAAAABAE)

-----------------------------------------------------------------------------------------------------------------------------------------------------------------

