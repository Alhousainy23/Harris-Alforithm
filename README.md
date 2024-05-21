# Harris-Algorithm
# Harris Corner Detectors Algorithm Article
* 1. The math behind Harris corner detector 
Harris corner detection Algorithm depends on the canny edge detection algorithm and the amount of change (Sobel x coordinate and Sobel y coordinate) 
We use Harris corner detection for feature extraction because it detects corners in the images, and there are some algorithms to use for feature extraction and matching. Still, the best Algorithm is called the Fast Algorithm acronym for (features from accelerated segmentation test ) but we are talking at another time.
Theory: we saw that corners are regions in the image with large variation in intensity in all directions. One early attempt to find these corners was made by Chris Harris & Mike Stephens in their paper A Combined Corner and Edge Detector in 1988, so now it is called the Harris Corner Detector. He took this simple idea to a mathematical form. It basically finds the difference in intensity for a displacement in all directions(U, V) . This is expressed as below

![Screenshot (6)](https://github.com/Alhousainy23/Harris-Algorithm/assets/125814743/5807cb3d-40bf-4115-8e33-646ac9c15331)


*  Step 1: Invariant Local Features: Detect interest points

  ![images(1)](https://github.com/Alhousainy23/Harris-Algorithm/assets/125814743/f405eefe-8a70-4ec7-84b5-fb14cb579920)

  
*  The picture is front it is  clear  the difference between two images through two images contain the same object, but the rotation is the difference between two images (right and left ) , one of     the best uses of the Harris corner detection algorithm is treated or play with the images although is the difference in brightness and rotation between them 
* Step 2: Extract invariant descriptors 
After detection, I need to make a description, and any photo consists of 3 types (edges - corners -flat region) 
1. region ⟶ any place in the photo not (corner - edge ), can detect easily any place in the photo. 
2. Edge ⟶ is difficult for matching with another photo because any edge is the amount of change in one direction only ( x coordinate - y coordinate - diagonal coordinate ) , and any edge not contain a lot of features or information .
3. The corner ⟶ is very easy to detect and matching with another image , because the corner is the amount of change in 2 directions, not one direction like edge, and based on this the corners contain a lot of features and information. 
![1_CCUCxtSCUdob70XMEE8Rwg](https://github.com/Alhousainy23/Harris-Algorithm/assets/125814743/f91f96e9-6a7b-4fb9-b409-29528b055059)


* They use a correlation matrix because it gives us (Eign values - Eign vectors ) 
each Eign vectors has an Eign value, and the Eign value sometimes is called Lambda, The Corner is identified by its large variation in both the x and y directions. Mathematically we can build what so-called Hessian matrix that states the variation (derivative) in the x, y, and xy directions. Let p be a pixel in the image I hessian matrix is defined as follows: 
* Where Ixx(p) is the second derivative of image in x direction at point p. Iyy(p) is the second derivative of image in y direction at point p.
*  Ixy(p) is the partial derivative in x and y at point p.

![Screenshot 2024-05-20 184622](https://github.com/Alhousainy23/Harris-Algorithm/assets/125814743/76b195a0-f6f6-4c5d-b727-183a0b829aba)

* Eigenvectors identify the direction of data variation and corresponding Eigenvalues identify the magnitude of variation in that direction. For example
* In the following figure, we have two eigenvectors u and v. Each vector has a length corresponding to its eigenvalue. So there is a large variation in the u direction and a lower variation in the v direction.
  ![Screenshot 2024-05-20 184849](https://github.com/Alhousainy23/Harris-Algorithm/assets/125814743/9cac0017-e8e2-45f9-a1ec-47582c34ec48)

--------------------------------------------------------------------------------------------------------------------------------------------------
# Harris Corner Detection Algorithm 
* The amount of change in y coordinates is called V, and the amount of change in x coordinates is called U, and E represents the Error Function for Harris Corners like in the following figure

![R7UV0](https://github.com/Alhousainy23/Harris-Algorithm/assets/125814743/e356efcd-04da-46b0-9676-531a0a06bf90)


* The following figure, it clears how to find the corners and how to represent the shape of the corners, it is moved the window on the picture for each pixels and after that calculate the difference between the window value now and the previous window value , and from the difference between values can detect the region is it ( Corner or edge or flat region)

![Screenshot 2024-05-20 190039](https://github.com/Alhousainy23/Harris-Algorithm/assets/125814743/5ce1efde-1358-4b9f-935c-5bb97db9d117)

* Small hint ⟶ Flat region ( it is the region that is obtained when the difference between values ( now window - previous window ) is equal = 0, and there was no effect on the coordinates
* How to obtain the difference between the new window value and the previous window value, there are following the next steps : 
1. Calculate the amount of change in ( X coordinate - y coordinate ) that is called partial derivative
2. Subtract the mean of the picture from the image gradient, because I need to reduce the offset value to represent the displacement.  
3. After that , we calculate the correlation matrix (Covariance Matrix) , because I need to obtain (eigenvectors, and eigenvalues) 
4. After obtained (eigenvector, eigenvalues) Values, now can detect the region is it ( Corner - Edge - Flat Region ) 
5. Finally, Put or apply a threshold on eigenvalues or use the Non-Maximum suppression method, because I need to obtain the maximum value in eigenvalues to represent or indicate the region is it contains important information or important features.

![Screenshot 2024-05-20 191747](https://github.com/Alhousainy23/Harris-Algorithm/assets/125814743/f4c99e75-3777-48d5-8529-e9bfb359e1d3)

*Some Hints 
1. When Compute Covariance: is it takes the amount of change from the Harris equation and applies Talyor Expansion that related to the derivative. in the Talyor expansion equation, it will be satisfied the first-order derivative only.
2. Harris Algorithm does not affect any rotation because it depends on the eigenvalues and eigenvectors 
3. There is two problems related to the Harris Algorithm , first The Harris Algorithm it affects when scaling is change ( zoom in or zoom out ) , not be able to detect in the status , second problem The Harris Algorithm not work with any Data Type , it works with float32 data type only .
