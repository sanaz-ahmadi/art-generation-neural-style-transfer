<ul>
  <li>Implemented the Neural Style Transfer (NST) algorithm to generate artistic images by combining the content and style of two input images.</li>
  <li>Utilized the VGG-19 network for transfer learning.</li>
  <li>Created a cost function that minimizes both the style and content cost, both of which are computed.</li>
  <li>Trained the model to generate the artistic image that combines the content and style.</li>
</ul>


### steps followed by code:
1. Transfer Learning
2. Neural Style Transfer (NST):
   - Computing the Content Cost:
        - Make Generated Image G Match the Content of ImageC
        - Content Cost Function 𝐽𝑐𝑜𝑛𝑡𝑒𝑛𝑡(𝐶,𝐺) --> `compute_content_cost`
   - Computing the Style Cost
        - Style Matrix --> `gram_matrix`
        - Style Cost --> `compute_layer_style_cost`
        - Style Weights --> `compute_style_cost`
    - Defining the Total Cost to Optimize --> `total_cost`
3. Solving the Optimization Problem:
   - Load the Content Image
   - Load the Style Image
   - Randomly Initialize the Image to be Generated
   - Load Pre-trained VGG19 Model
   - Compute Total Cost
        - Compute Content Cost
        - Compute Style Cost --> `train_step`
   - Train the Model
