# Advanced_Project
This was my advanced project submitted as part of an integrated masters course in mathematics at Brunel University London. You can find  the full text in `Advanced_Project (8).pdf`. The abstract:

><em>In this paper, we explore some of the foundational concepts in linear algebra. We aim to provide intuition behind commonly used propositions and a number of proofs are given for some non-trivial results. After the fundamental concepts are covered, we delve into two types of matrix decomposition leading ultimately to an explorations of the singular value decomposition. This is followed by a practical investigation where some python code has been written to allow the reader to easily apply this decomposition to both grey scale and coloured images. We finish with some recommendations as to further practical work that could be undertaken.<em>

I implemented a python object which can be used by Data Scientists. This can be found in `Practical/main.py`.

This code primarily focuses on the implementation and usage of Singular Value Decomposition (SVD) for images. It aims to demonstrate various ways of decomposing an image into its red, green, and blue (RGB) components and reconstructing it using reduced numbers of singular values.

## Libraries & Modules

1. **matplotlib.pyplot**: Used for plotting images and charts.
2. **numpy**: Used for matrix operations and calculations.
3. **PIL.Image**: Utilized for loading and manipulating images.
4. **os**: Used for retrieving the base name of a file path.

## Class: `image_svd`

### Attributes:
- `path`: The path to the image file.
- `image`: A PIL Image object loaded from the provided path.
- `color_map`: A list denoting the names of RGB colors.

### Methods:

1. **get_component(index: int)**: Retrieves a 2D matrix of color intensities. The provided index determines the color (0 for red, 1 for green, and 2 for blue).

2. **get_all_components()**: Retrieves three 2D matrices corresponding to the RGB components of the image.

3. **plot_image()**: Displays the original image using matplotlib.

4. **plot_component(index: int)**: Plots a 2D matrix of color intensities for a given RGB component.

5. **plot_all_components()**: Displays each RGB component of the image side by side.

6. **var_singular(matrix: np.matrix, scale: bool = True)**: Returns the variance explained by the singular values. Offers an option to scale the matrix.

7. **plot_singular(matrix: np.matrix, total: int = 20)**: Visualizes the variance explained by the singular values using a bar chart.

8. **rank_k_approximation(matrix: np.matrix, num_components: int)**: Returns a rank-k approximation of a matrix using a specific number of singular values.

9. **recombine_rgb(components: tuple)**: Recombines the RGB components into a single image.

10. **plot_n_approximations(matrix: np.matrix, n_plots: int, color_index: int, title: str = "", scale: bool = True)**: Displays approximations of a specific RGB component using an increasing number of singular values.

11. **plot_n_approximations_rgb(n_plots: int, title: str = "")**: Plots n approximations for each RGB component, then shows the recombined RGB approximations.

12. **plot_singular_rgb(num_components: int)**: Plots the explained variance percentage for the singular values of each RGB component.

### Helper/Utility Methods:

1. **__convert_index_color(index: int)**: Converts a numeric index to its corresponding RGB name.

2. **__scale_matrix(matrix: np.matrix)**: Scales and centers a matrix.

3. **__perform_svd(matrix: np.matrix)**: Performs the Singular Value Decomposition on a matrix.

4. **__plot_bar_1d(values: np.array)**: Plots a bar chart for a 1D numpy array.

5. **__rank_k_approximation(matrix_U: np.matrix, matrix_s: np.ndarray, matrix_V: np.matrix, num_components: int)**: Returns a rank-k approximation using provided U, singular values, and V matrices.

## Example Usage:

The given code concludes by loading an image named "colourful_image.jpg", decomposing it, and plotting approximations using RGB components.

```python
test = image_svd("colourful_image.jpg")
test.plot_n_approximations_rgb(5)
plt.show()
```

This example will plot five approximations of the image using varying numbers of singular values for each RGB component and display the result.

## Note:

While the code structure provides a comprehensive exploration of image decompositions using SVD, optimizations, and enhancements can be made to improve efficiency and expand functionalities.

