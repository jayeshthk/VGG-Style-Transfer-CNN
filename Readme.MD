# Style Transfer Application using Convolutional Neural Networks

## Overview

This project demonstrates a style transfer application using Convolutional Neural Networks (CNNs). Style transfer is a technique in neural networks where the style of one image is applied to the content of another image. This is accomplished by leveraging the features learned by a pre-trained VGG19 model.

## Getting Started

### Prerequisites

- Python 3.x
- PyTorch
- torchvision
- PIL
- matplotlib
- numpy

You can install the required packages using pip:

```bash
pip install torch torchvision pillow matplotlib numpy
```

### Code Description

1. **Load and Prepare Images:**

   - Load content and style images.
   - Resize the style image to match the content image dimensions.

2. **Model Setup:**

   - Use the VGG19 model pre-trained on ImageNet for feature extraction.
   - Freeze the model parameters to avoid updating them during optimization.

3. **Feature Extraction:**

   - Extract features from specific layers of the VGG19 model to capture both content and style information.

4. **Gram Matrix Calculation:**

   - Compute the Gram matrix for style representation, which helps capture the correlations between different feature maps.

5. **Optimization:**

   - Define the loss functions for content and style.
   - Use an Adam optimizer to iteratively adjust the target image to minimize the total loss, which is a combination of content loss and style loss.

6. **Results:**
   - Save the final styled image and display intermediate results during optimization.

### Mathematical Basis

![reserch_paper_arch](/images/res_paper_total_loss.png)
![mathematical_impl](/images/math_expl.png)

## Usage

1. Place your content and style images in the `images` directory.

2. Run the notebook `introyt1_tutorial.ipynb`. The notebook will perform style transfer and display the results.

3. The final styled image and intermediate results will be shown in notebook

```python
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(20, 10))
ax1.imshow(im_convert(content))
ax2.imshow(im_convert(target))
```

### Example

After running the code, you should see:

- `input_content.jpg`: The original content image. (me🙃)
- `input_style.jpg`: The original style image.
![in_out.jpg](style_transfer_initial.png)

- `target.jpg`: The final output image with the style of `input_style.jpg` applied to the content of `input_content.jpg`.
  ![output](/images/style_transfer_result.png)

## Results

- After running final cell, you should be getting imposed result on style image on content image.

```python
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(20, 10))
ax1.imshow(im_convert(content))
ax2.imshow(im_convert(target))
```

- Final Result => ![style_transfer_result](/images/style_transfer_result.png)

## References

- [Gatys et al. (2016) - A Neural Algorithm of Artistic Style](https://arxiv.org/abs/1508.06576)

- [Gatys et al. - Image Style Transfer Using Convolutional Neural Networks](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)

- [Gram Matrix Wikipedia](https://en.wikipedia.org/wiki/Gramian_matrix)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```

```
