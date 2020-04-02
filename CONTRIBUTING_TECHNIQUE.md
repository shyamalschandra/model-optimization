# Guidelines for Contributing a New Technique

The following are guidelines for contributing a complete technique to the
toolkit, for example, connection pruning.

We will be evolving these guidelines to make the process more effective, and
as we receive more contributions. For example, we are working on creating a
repository of training scripts for
different models and tasks aimed at simplifying technique validation
([issue](https://github.com/tensorflow/model-optimization/issues/133)),
making the project contributor-friendly
([issue](https://github.com/tensorflow/model-optimization/issues/131)), and
having reproducible results.


## Contribution Process

It's recommended to go in this order.

1. Before anything else, provide a proposal RFC, purely with what you would tell a
   user to motivate them to use this technique. If approved, you will then be matched with a
   sponsor, following the [general TF RFC process](https://github.com/tensorflow/community/blob/master/governance/TF-RFCs.md).
   * How the technique fits in the rest of the toolkit (e.g. in combination)
     and what use cases does it better address or start addressing.
   * Experiment results with not only accuracy but also deployment metrics (e.g. model,
     storage space, latency, memory).
   * TODO(tfmot): link to sample pruning RFC once submitted.

2. In parallel:
   * Provide a [design RFC](https://github.com/tensorflow/community/blob/master/governance/TF-RFCs.md) under [model-optimization/community/rfcs](https://github.com/tensorflow/model-optimization/blob/master/community/rfcs). Once the sponsor considers it ready, there will be rounds of comments
     and design review meetings.
     * Focus foremost on the aspects that affect the end-to-end experience for the user of your technique.
     * API and implementation should strive for similarity with existing
       techniques to provide the best user experience.
     * TODO(tfmot): link to sample pruning RFC once submitted.
   * Start prototyping and building the library in a fork of TFMOT. If prior
     extensive results don't exist, you may need to start this earlier to create
     the proposal RFC.

3. Upon approval of design RFC, upstream existing code into TFMOT
   and start development there.
      * Some internal processes will be started, in preparation for launch.

4. Implement according to design while in parallel, creating the demonstration
   that the user story works (e.g. a training convergence test).
      * The training convergence test will either live in TF Official Models
        or in a fork of it. TODO(tfmot): link to integration process.

5. Documentation and tutorials:
   * Overview page that requires minimal end-user domain knowledge.
     * TODO(tfmot): link to QAT page, as well as, template, when submitted.
   * Colab example that covers the single most critical path.
     * TODO(tfmot): link to QAT page, when submitted.
   * Comprehensive guide that covers all usage patterns and navigates users
     to the APIs for their use case.
     * TODO(tfmot): link to QAT page, when submitted.
   * TODO(tfmot): link to consistent user experience RFC when submitted.

6. Packaging and release:
   * releases are managed by the TensorFlow Model Optimization team. Work with
     them to produce and test pip packages as well as generate API docs.
   * days before the release date:
     * The API docs will not be checked in, but should be tested and
       ready to submit.
     * The other documentation will be be checked in, but not linked in the
       navigation bar. The colabs should use a stable release, as opposed to
       a test release.

7. Collaborative blog post (optional)
   * samples: [pruning
     API](https://medium.com/tensorflow/tensorflow-model-optimization-toolkit-pruning-api-42cac9157a6a)
     and [post-training integer quantization](https://medium.com/tensorflow/tensorflow-model-optimization-toolkit-post-training-integer-quantization-b4964a1ea9ba)
