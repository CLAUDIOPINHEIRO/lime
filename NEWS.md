# lime 0.4.0.9999

* Add `preprocess` argument to `lime.data.frame` to keep it in line with the 
  other types. Use it to transform your data.frame into a new input that your
  model expects after permutations

# lime 0.4

* Add support for image explanation. The dispatch will be on paths pointing to
  valid image files. Image explanations can be visualised using 
  `plot_image_explanation` (#35)
* Add support for neural networks from the `keras` package
* Add `as_classifier()` and `as_regressor()` for ad-hoc specification of the 
  model type in case the heuristic implemented in `lime` doesn't hold. 
  `as_classifier()` also lets you add/overwrite the class labels.
* Use `gower` as the new default similarity measure for tabular data
* If `bin_continuous = FALSE` the default behavior is now to sample from a 
  kernel density estimation rather than assume a normal distribution.
* Fix bug when numeric features in the training data were constant (#56)
* Fix bug when plotting regression explanations with `plot_explanations()` (#60)
* Logical columns in tabular data is now supported (#75)
* Overhaul of `plot_text_explanation()` with better formatting and scrolling
  support for many explanations
* All plots now show the fit of the explainer so the user can assess the quality
  of the explanation

# lime 0.3.1

* Added a `NEWS.md` file to track changes to the package.
* Fixed bug when explaining regression models, due to drop=TRUE defaults (#33)
* Integer features are no longer converted to numeric during permutations (#32)
* Fix bug when working with xgboost and tabular predictions (@martinju #1)
* Training data can now contain `NA` values (#8) 
* Keep ordering when plotting with `plot_features()` (#38)
* Fix support for mlr by extracting predictions correctly
* Added support for `h2o` (@mdancho84) (#40)
* Throws meaningful error when all permutations have 0 similarity to original
  observation (#47)
* Explaining data can now contain `NA` values (#45)
* Support for `Date` and `POSIXt` columns. They will be kept constant during
  permutations so that `lime` will explain the model behaviour at the given 
  timepoint based on the remaining features (#39).
* Add `plot_explanations()` for an overview plot of a large explanation set
