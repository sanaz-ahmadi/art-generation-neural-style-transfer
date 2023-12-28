<ul>
  <li>Implemented the Neural Style Transfer (NST) algorithm to generate artistic images by combining the content and style of two input images.</li>
  <li>Utilized the VGG-19 network for transfer learning.</li>
  <li>Created a cost function that minimizes both the style and content cost, both of which are computed.</li>
  <li>Trained the model to generate the artistic image that combines the content and style.</li>
</ul>


### steps followed by code:
1. **Transfer Learning**
2. **Neural Style Transfer (NST):**
   - 2.1) **Computing the Content Cost:**
        - 2.1.1) Make Generated Image G Match the Content of ImageC
        - 2.1.2) Content Cost Function 𝐽𝑐𝑜𝑛𝑡𝑒𝑛𝑡(𝐶,𝐺) --> `compute_content_cost`
   - 2.2) **Computing the Style Cost**
        - 2.2.1) Style Matrix --> `gram_matrix`
        - 2.2.2) Style Cost --> `compute_layer_style_cost`
        - 2.2.3) Style Weights --> `compute_style_cost`
    2.3) **Defining the Total Cost to Optimize** --> `total_cost`
3. **Solving the Optimization Problem:**
    3.1) Load the Content Image
    3.2) Load the Style Image
    3.3) Randomly Initialize the Image to be Generated
    3.4) Load Pre-trained VGG19 Model
    3.5) Compute Total Cost
        - 3.5.1) Compute Content Cost
        - 3.5.2) Compute Style Cost --> `train_step`
    3.6) Train the Model
