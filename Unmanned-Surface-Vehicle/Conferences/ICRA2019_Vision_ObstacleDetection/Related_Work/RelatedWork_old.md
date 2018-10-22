1.  The majority of approaches that were developed for autonomous ground vehicles rely on estimation of the ground plane, and cannot be readily applied to the aquatic environment of the USVs. A common practice for obstacle detection in marine envi- ronment is the use of RADAR, sonar, or LIDAR. 

2. Almeida et al. [19] proposed obstacle detection using on-board radar. They experi- enced difficulties in detecting small obstacles that were located in the near proximity (closer than 200m) of the boat. The size and power consumption of radar units represent an additional challenge in application on small-sized USVs. Several approaches have therefore focused on obstacle detection using cameras.Larson et al. [20] present advances in obstacle avoidance for USVs and point out the use of cameras. Their approach to obstacle detection with monocular camera relies on horizon estimation and image segmentation.

3. Guo et al. [21] use an omni-directional camera to detect obstacles in water, based on the difference between two consecutive frames and foreground extraction 

4. Gal [22] uses edge detection approaches to detect the horizon line, and then search for obstacles below the estimated horizon. A major drawback of the method described in [22] is ap- proximation of the sea-edge with a straight line. This assumption is often violated, especially in coastal waters and in marina, where the horizon does not correspond to the edge of water.

5. The method described in [22] also relies on a sharp boundary between sea and sky when estimating the horizon line. In practice, however, this boundary is often blurred due to unfavorable weather conditions (haze, overwhelming cloudiness, fog), sun glitter, and reflections of the surrounding environment in water, making estimation of the exact position of the horizon difficult

6. Osborne et al. [23] propose a method capable of tracking objects on both visible and thermal imagery. They detect obstacles based on agglomerative clustering oftemporally stable features and track stable object clusters frame- to-frame.

7. Cane et al. [24] proposed obstacle detection and tracking based on saliency maps with wake and glint suppression and achieve excellent results on the open-seas dataset [25], which is part of the PETS2016 [26] challenge.

8. Wang et al. [27–29] propose a vision-based obstacle detectionthat incorporates a stereo camera system. They use saliency de- tection in left camera to detect obstacles under the estimated sea edge and motion estimation to refine the output from saliency detection. Using epipolar constraints of stereo camera system and template matching, they search for correspondences of detected obstacles in right camera. In [29] they proposed disparity filtering to further improve position of the correspondences. However, their assumption of sharp boundary between sea and sky is often violated in practice. They also rely solely on the left camera for obstacle detection

9. Wang et al. [30] present stereo vision based obstacle detection. They estimate the sea surface by fitting a plane to the 3-D point set of the reconstructed scene. By aligning the reconstructed 3-D points with the sea surface, they compute oc- cupancy grid and height grid, based on which the obstacles above water are detected. A calm sea may lack texture, which results in poor 3-D reconstruction of the sea, and consequently inaccurate sea surface estimation. In addition, such approach requires objects to significantly protrude through the water surface in order to be distinguished as obstacles. This assumption is violated for small buoys and floating debris.

10. Huntsberger et al. [31] propose a stereo vision based navigation using a Hammerhead system. They generate dense range images, project range data into 2-D grid map, and perform spatial and temporal filtering on the map. For each map cell they compute a hazard probability, which serves for detecting and tracking discrete objects. However, the Hammerhead system cannot be used on small-sized USVs due to its dimensions, and suffers from the assumption that all obstacles stick out of the water.

11. Huntsberger et al.[17] attempted to address this issue using stereo systems, but require large baseline rigs that are less appropriate for small vessels due to the increased instability and limit pro- cessing of near-field regions.

12. Recently, Kristan et al. [7] proposed a graphical model for monocular obstacle detection via semantic segmentation of the observed marine scene. The algorithm generates a water seg- mentation mask, and treats all objects in the water region as ob- stacles. The model assumes that an image of marine environment can be partitioned into three distinct and approximately parallel semantic regions: sky at the top, ground or haze in the middle, and water at the bottom of the image. The semantic structure is enforced by fitting vertically distributed Gaussian components and regularizing the result with a Markov random field. This ap- proach significantly outperforms the related approaches on the task of marine obstacle detection. It successfully detects obstacles protruding through the surface and floating obstacles, does not assume a straight water edge, and runs in real-time. Nevertheless, the SSM [7] still fails in the presence of visual ambiguities. For example,when the boat faces open water and the horizon is hidden by the haze, the SSMapproach drastically over- or under-estimates the extent of the water region.

13. Socek et al.[14] assumed a static camera and apply back- ground subtraction combined with motion cues. However, background subtraction cannot be applied to a highly dynamic scenes encountered on a moving USV

14. Santana et al.[13] applied fusion of Lukas–Kanade local trackers with color overseg- mentation and a sequence of k-means clusterings on texture features to detect water regions in videos.

15. Alternatively, Fefilatyev and Goldgof [15] and Wang et al.[16] applied a low-power solution using a monocular camera for obstacle detection. They first detect the horizon line and then search for a potential obstacle in the region below the horizon. A funda- mental drawback of these approaches is that they approximate the edge of water by a horizon line and cannot handle situa- tions in coastal waters, close to the shoreline or in marina. At that point, the edge of water does not correspond to the hori- zon anymore and can be no longer modeled as a straight line. Such cases call for more general segmentation approaches.

16. Many unsupervised segmentation approaches have been proposed in literature. Khan and Shah [18] used optical flow, color, and spatial coordinates to construct features which are used in single Gaussians to segment a moving object in video.

17. Nguyen and Wu [19] proposed Student-t mixture models for robustifying segmentation.

18. Improved segmentation can be achieved by applying Bayesian regularization scheme in Gaussian mixture models, however, care has to be taken at initialization [20].

19. Felzenszwalb and Huttenlocher [21]have proposed a graph-theoretic clustering to perform segmentation of color images into visually-coherent regions.

20. 