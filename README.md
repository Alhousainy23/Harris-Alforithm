# Harris-Algorithm
# Harris Corner Detectors Algorithm Article
* 1. The math behind Harris corner detector 
Harris corner detection Algorithm depends on the canny edge detection algorithm and the amount of change (Sobel x coordinate and Sobel y coordinate) 
We use Harris corner detection for feature extraction because it detects corners in the images, and there are some algorithms to use for feature extraction and matching. Still, the best Algorithm is called the Fast Algorithm acronym for (features from accelerated segmentation test ) but we are talking at another time.
Theory: we saw that corners are regions in the image with large variation in intensity in all directions. One early attempt to find these corners was made by Chris Harris & Mike Stephens in their paper A Combined Corner and Edge Detector in 1988, so now it is called the Harris Corner Detector. He took this simple idea to a mathematical form. It basically finds the difference in intensity for a displacement in all directions(U, V) . This is expressed as below
![Screenshot (6)](https://github.com/Alhousainy23/Harris-Algorithm/assets/125814743/5807cb3d-40bf-4115-8e33-646ac9c15331)
-----------------------------------------------------------------------------------------------------------------------------------------------------------------
*  Step 1: Invariant Local Features: Detect interest points
  ![images(1)](https://github.com/Alhousainy23/Harris-Algorithm/assets/125814743/f405eefe-8a70-4ec7-84b5-fb14cb579920)
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
*  The picture is front it is  clear  the difference between two images through two images contain the same object, but the rotation is the difference between two images (right and left ) , one of     the best uses of the Harris corner detection algorithm is treated or play with the images although is the difference in brightness and rotation between them 
* Step 2: Extract invariant descriptors 
After detection, I need to make a description, and any photo consists of 3 types (edges - corners -flat region) 
1. region ⟶ any place in the photo not (corner - edge ), can detect easily any place in the photo. 
2. Edge ⟶ is difficult for matching with another photo because any edge is the amount of change in one direction only ( x coordinate - y coordinate - diagonal coordinate ) , and any edge not contain a lot of features or information .
3. The corner ⟶ is very easy to detect and matching with another image , because the corner is the amount of change in 2 directions, not one direction like edge, and based on this the corners contain a lot of features and information. 
![1_CCUCxtSCUdob70XMEE8Rwg](https://github.com/Alhousainy23/Harris-Algorithm/assets/125814743/f91f96e9-6a7b-4fb9-b409-29528b055059)

----------------------------------------------------------------------------------------------------------------------------------------------------------
