# Root segmentation
The entire idea is based on biologists needing to measure the following:
 * main root length
 * auxiliary root lenght (individual lengths and sum)
 * number of auxiliary roots
These are the main aspects I would aim for.

## Proposed solution:
### Preprocessing
 * Denoising?
 * Maximum detection (Laplacian of Gaussian, Gaussian of Gaussian)
 * Hierarchy thresholding
 * Filtering objects based on their size (and other features?) to remove everything but plants
### Converting to topological graph
 * Skeletonize the mask
 * Convert to graph (smth like this https://github.com/Image-Py/sknw)
 * Find main root - not sure how (shortest path from top to bottom?, should include info from the raw/denoised image?)
 * Find auxiliary roots, deal with overlaps - no idea how

