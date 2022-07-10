```yaml
ImageProcessor:
  image_cleaner_type: MARSImageCleaner
  
  MARSImageCleaner:
    picture_threshold_pe:
      - [type, "LST*", 8.5]
      - [type, "MST*NectarCam", 9.0]
    boundary_threshold_pe:
      - [type, "LST*", 4.75]
      - [type, "MST*NectarCam", 4.5]
    keep_isolated_pixels: false
    min_picture_neighbors: 2
    
  ImageQualityQuery:
    quality_criteria:
      - ["enough_pixels", "lambda im: np.count_nonzero(im) > 2"]
      - ["enough_charge", "lambda im: im.sum() > 50"]
```