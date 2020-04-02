# Production Example and Convergence Testing

One of the contribution requirements of a new technique is a training
convergence test, to ensure that the users can achieve the same benefits
mentioned in the documentation. At the same time, this can serve as a good
example for using the technique in more realistic models.

This example and test will either live in TF Official Models
or in a fork of it, with the following process.

1. During the review of the proposal RFC, the Official Models team will
   review it and determine whether the technique will live in TF Official
   Models or a fork, based on the motivation for a user to use it.

2. Reproducing the results from the proposal RFC will take time. While
   the contributor implements to library, they can start implementing
   the example and test, while building local TFMOT pip package from source.

3. The final example and test must abide by the Official Models standards,
   though to start, the contributor should prioritize reproducing the results.
     * TODO(TFMOT): link to standards when available.

4. Create a single PR with the example and test.
     * MOT will first review it and reproduce the expected results.
     * If the example lives in TF Official Models, they will review it
       and provide a verbal approval.

5. After the PR approvals, MOT will create a stable release that includes the
   new technique.

6. If the example lives in Official Models:
   * the minimum MOT version is bumped there and Official Models gives a final
     approval for merging the PR.
   If it lives in the fork, then its minimum version will be bumped and TFMOT
   will do a final approval.

7. The technique is released in pip with a production-level example and
   convergence test. 


## Integration Details

The following are temporary and will be updated as the integration point
becomes smoother.

1. The current integration lives in
   [resnet_imagenet_main.py](https://github.com/tensorflow/models/blob/master/official/vision/image_classification/resnet/resnet_imagenet_main.py), but is being moved
   to [classifier_trainer.py](
   https://github.com/tensorflow/models/blob/master/official/vision/image_classification/classifier_trainer.py).
2. The current integration needs to be modularized before new techniques are
   integrated.
   * All model optimization flags should be grouped in one major config object
     for users to view only if they are interested in model optimization.
   * All model optimization code should be as self-contained as possible.
   * The model optimization library should only be imported when the model
     optimization flags are used.

The following are in progress:
1. The fork of Official Models does not exist yet.


