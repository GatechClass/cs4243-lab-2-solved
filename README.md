# cs4243-lab-2-solved
**TO GET THIS SOLUTION VISIT:** [CS4243 Lab 2 Solved](https://mantutor.com/product/cs4243-instructions-solved-6/)


---

**For Custom/Order Solutions:** **Email:** mantutorcodes@gmail.com  

*We deliver quick, professional, and affordable assignment help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;113853&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS4243 Lab 2 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
This lab has four parts. For each of the first three parts, implement the outlined functions in lab2.py and run them in the notebook lab2.ipynb. For the Q&amp;A in Part 4, write your answers directly into the notebook. Expected outputs to each cell in the notebook are supplied as reference but your outputs do not need to match exactly.

Upload to Canvas your completed lab2.py and lab2.ipynb by zipping them into a file named AXXX1_AXXX2.zip, where AXXX is the student number of the group members. Submit one file per group. Missing files, incorrectly formatted code that does not run, etc. will be penalized.

Objective

This lab will cover edge detection using the Canny edge detector and line and circle detection from these edges using the Hough Transform (see Figure 1). We will apply the concept of Hough transform for reflective symmetry detection in Lab 3.

Figure 1. From the original RGB image, detect the edges using the Canny Edge Detector

(Part 1) before applying the Hough Transform to detect lines (Part 2) and circles (Part 3).

Note: We will use the coordinate convention illustrated on the right where the top left corner is the origin, row# is x (1st coordinate) and column# is y (2nd coordinate). For instance, in the diagram at the right, the image shape is (4,3), the intensity value at origin (x0, y0) = (0,0) is 2, and the intensity value at point (x1, y1) = (3, 2) is 3.

Part 1: Canny Edge Detection (30%)

This part detects the edges which will be fed as inputs to the Hough transform in Parts 2 and 3. To implement Canny Edge detection, perform the following steps

1. Pre-processing by blurring the image:

<img draggable="false" role="img" class="emoji" alt="▪" src="https://s.w.org/images/core/emoji/15.1.0/svg/25aa.svg"> make_gaussian_kernel()takes in two parameters: kernel size ksize and Gaussian standard deviation sigma and generate the corresponding Gaussian kernel

<img draggable="false" role="img" class="emoji" alt="▪" src="https://s.w.org/images/core/emoji/15.1.0/svg/25aa.svg"> cs4243_filter()is provided for you and applies your generated Gaussian kernel

3. Perform non-maximum suppression on the gradient magnitude matrix 𝐺! to obtain a singlepixel wide gradients 𝐺%.

<img draggable="false" role="img" class="emoji" alt="▪" src="https://s.w.org/images/core/emoji/15.1.0/svg/25aa.svg"> non_maximum_suppression()skips interpolation and simply uses the nearest available neighbouring pixel values, with the choice in neighbouring pixel depending on the orientation 𝐺” (see Fig. 2 on right).

Figure 2. Non-maximum suppression without interpolation partitions the orientation into ranges. For example, 22.5&amp; ≤ 𝐺” &lt; 67.5&amp; uses pixels a as the neighbouring pixels for comparison, −22.5&amp; ≤ 𝐺” &lt; 22.5&amp; uses pixels b as neighbours, etc.

4. double_thresholding()thresholds the single-pixel wide gradients 𝐺% with a high threshold 𝜏’ and a low threshold 𝜏( to generate the strong edges 𝐸) 𝜏’ and weak edges 𝐸* = 𝜏’ &gt; 𝐺% &gt; 𝜏(. Note that 𝐸) and 𝐸* are now binary images (0 for background, 1 for edge). The thresholds 𝜏’ and 𝜏( should be set adaptively based on the gradient magnitudes present in 𝐺%, i.e. 𝜏’ , and 𝜏( = min 𝐺% + 𝑓 where 𝑓’ and 𝑓( are given as inputs.

5. edge_linking()performs a naïve version of edge linking by checking all edge pixels of 𝐸+ to see if they have a strong edge in the 8-pixel neighbourhood. Make multiple passes, where in each pass, linked weak pixels are removed from the weak pixel set and added to the strong pixel set. Stop when no more weak pixels get linked or when the maximum number of passes is reached. The resulting strong pixel set will be a complete (or approximate) edge image. For efficiency, you are strongly recommended to vectorise your implementation.

Part 2: Line Detection with Hough Transform (20%)

Use the detected edges from Part 1 to detect straight lines. Recall the normal form of a line representation with parameters 𝜌 and θ, the normal line length and angle.

1. Quantize the parameter space for 𝜌 and 𝜃 based on the min and max value for that parameter and an interval size. The min and max of 𝜌 spans from −𝑑 to 𝑑, where 𝑑 is the length of the image diagonal, while 𝜃 spans from 0 to 𝜋. The interval will be user-defined and determines the quantization or bin coarseness in the accumulator array. Index the quantized spaces for 𝜌 and 𝜃 with 𝑟 and 𝑡 respectively. When mapping from (𝜌, 𝜃) to (𝑟, 𝑡) treat the lower bound of the interval range as inclusive and upper bound as exclusive. When mapping from (𝑟, 𝑡) to (𝜌, 𝜃), apply the interval lower limit of the interval. For example, if the interval for 𝜃 is ,-, the quantization is split from A0, ,-C , A,- , ,.C A,. , /-,C , [ /-, , 𝜋] and 𝜃0 associated with 𝑡 = 1 is ,-. As default, use an interval of 1 pixel and %12, for 𝜌 and 𝜃 respectively.

2. Create a 2D accumulator array A of dimension (𝑅 × 𝑇) and initialize all entries to 0, where R and T are total number of bins for 𝜌 and 𝜃 based on the chosen quantization for step 1.

4. find_peak_params()performs non-maximum suppression similar to Lab 1 and finds the local maxima in A to return the associated 𝑟, 𝑡. This function is provided for you. It has as inputs a threshold on accumulator values and a window size when searching for local maxima. Part 3: Circle Detection with Hough Transform (20%)

Use the detected edges from Part 1 to detect circles. A circle is parameterized by center coordinates (𝑎, 𝑏) and radius 𝑟6. The steps are analogous to Part 2, with a few changes to improve efficiency.

1. Quantize the parameter space in the same way as Part 2. The limits of 𝑎 and 𝑏 span from 0 to H and 0 to W respectively, with (H, W) being the dimension of the image (we are only interested in circles whose centres lie within the image frame). The limits of 𝑟6 range from

𝑟738 to 𝑟7:; which are either user-defined or set to defaults of 3 and the image diagonal length respectively. Use an interval of 1 pixel for all 3 parameters.

2. Create a 3D accumulator array A of size (𝑅 × 𝐻 × 𝑊) based on the quantization of step 1.

3. hough_vote_circles()iterates through each pixel on the edge image. For every

candidate radius value r, an edge pixel will cast a vote for circles of radius r, centred at itself.

• A naïve way to cast votes on a perimeter around pixel 𝑖 located at K𝑥3,𝑦3N, would be to iterate through each bin of 𝑟 and each value θ in the range from 0 to 2π and solve for 𝑎 = 𝑥3 + 𝑟 × 𝑐𝑜𝑠 𝜃 and 𝑏 = 𝑦3 + 𝑟 × 𝑠𝑖𝑛 𝜃.

• The naïve formulation is redundant because it is always the same circle of votes cast relative to K𝑥3,𝑦3N for some fixed radius 𝑟. The relative votes can therefore be solved for in advance, e.g. using skimage.draw.circle_perimeter and added directly to the accumulator array A. This process is illustrated in Fig. 3 below.

4. Use the provided find_peak_params() to detect the local maxima.

Figure 3. (a) Given an edge image and an accumulator array, we can generate a pre-defined (quantized) circle of votes. (b) – (d) This vote circle can be added to relative to each edge pixel in the image. The final detected circle is based on the local maximum in the accumulator array. Note the padding in the accumulator array denoted by the grey shading to accommodate out-of-range votes. Part 4: Exploratory Questions (30%)

• Weighted Voting (5%): Apply your hough_vote_circles()to the image coins.png. Are you able to find all the circles? What adjustments can you make to the votes cast to ensure that circles of all sizes are detected? Hint: Run find_peak_params() and visualize the bin counts. Each bin is associated with the number of edge pixels that cast a vote. How is this affected by the circle size?

Weight your votes accordingly similar to the previous question.

• Interval / Bin Size (10%):

• Test your implementation of hough_vote_circles_grad()on the image

penny_farthing.png. Comment on your results. Are you able to find any circles? To make this part more intuitive, you can also set the weight of each vote to 1 so that you can determine the number of edge pixels which cast a vote in that bin.

• The default interval setting of 𝑟, 𝑎, and 𝑏 is 1. Repeat the previous step with interval sizes of 3 and 5 for all three parameters. Again, comment on your results and explain the difference in result when the interval was set to 1. What do you think will happen if the interval size is set to a large value like 10 or 20?
