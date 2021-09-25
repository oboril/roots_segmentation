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
### Segmenting the root
 * Find main root - not sure how (shortest path from top to bottom?, should include info from the raw/denoised image?)
 * Find auxiliary roots, deal with overlaps - no idea how

### Random ideas
Use some maximum detection which is aware of directionality - some thing like canny edge detector, but for maxima

The leaves can be probably deleted manually, although and automated approach would be cool

How to deal with crossing roots? Could some clever manipulation with gradients around the crossing reveal which bits are in the foreground/background?

One possible constrain could be that roots can branch only once - the main root can branch to auxiliary roots, but the auxiliary roots cannot brach further

This link might be relevant: https://link.springer.com/chapter/10.1007/978-3-319-21963-9_2

