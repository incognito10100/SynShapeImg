This project involves generating synthetic datasets of geometric shapes and provides a method for visualizing and managing these datasets. The code is designed to create and save images of different shapes, generate labels for these images, and handle variations to create unseen datasets for testing purposes.

The objective of this project is to provide a framework for generating controlled image datasets. These datasets can be used for training and evaluating machine learning models, particularly in scenarios where varied but predictable image data is required. By generating synthetic data, we can create large and diverse datasets without the need for real-world data collection, which is often time-consuming and expensive.

### 1. **Import Libraries**

The following libraries are imported to facilitate file operations, numerical computations, image processing, and data management:

- **`os`**: For directory and file operations.
- **`numpy`**: For numerical operations and creating images.
- **`cv2`**: For image creation and manipulation.
- **`pandas`**: For creating and saving labels in CSV format.

### 2. **Define Parameters**

The parameters set up the configurations for generating images:

- **`output_dir`**: Directory where the generated images and labels will be saved.
- **`image_size`**: Tuple specifying the dimensions of the images (width, height).
- **`num_samples_per_class`**: Number of images to generate for each shape type.
- **`shape_types`**: List of shape types to be generated (e.g., 'circle', 'square', 'triangle').
- **`shape_colors`**: List of colors for the shapes. Currently, only white is used.

### 3. **Create Shape Images**

The `create_shape_image` function generates an image of a specified shape (circle, square, or triangle) with a given size and color:

- **Circle**: Drawn with `cv2.circle` at the center of the image.
- **Square**: Drawn with `cv2.rectangle` at specific coordinates.
- **Triangle**: Filled using `cv2.fillPoly` with three vertices.

### 4. **Save Images for Each Shape**

The `save_images_for_shape` function handles saving images:

- It creates the necessary directory if it doesn't exist.
- For each sample, it generates an image of the specified shape and saves it with a filename that includes the shape type and an index.

### 5. **Generate and Save Images**

The `main` function:

- Iterates through each shape type.
- Calls `save_images_for_shape` to generate and save images for each shape type into the designated directories.

### 6. **Create Labels CSV File**

The `create_labels_csv` function generates a CSV file with image paths and their corresponding labels:

- It iterates through each shape type and image file.
- Compiles a list of file paths and labels.
- Saves this information into a CSV file for easy use in machine learning tasks.

### 7. **Generate Unseen Dataset**

The code segment for generating an unseen dataset follows a similar structure to the primary dataset generation:

- **Parameters**: It uses a different output directory and adjusts the parameters for the unseen images.
- **Image Generation**: Shapes are created with slightly different sizes or positions to simulate unseen data variations.
- **CSV Creation**: Labels are created for the unseen images in the same manner as for the primary dataset.

