# Segment Anything Meets Point Tracking

SAM-PT is an extention of the [Segment Anything Model](https://github.com/facebookresearch/segment-anything) (SAM) for zero-shot video segmentation. This is a simple yet effective point-based perspective in a video object segmetation research.

## Video Object Segmentation Demo

Annotators only provide a few points to denote the target object at the first video frame to get video segmentation results. Below are a few examples that are provided 
<p float="left">
  <img alt="street" src="assets/climbing.gif?raw=true" width="48%" /> 
  <img alt="bees" src="assets/Dog_after.gif?raw=true" width="48%" /> 
  <img alt="avatar" src="assets/Violet_jump.gif?raw=true" width="48%" />
  <img alt="horsejump-high" src="assets/Violet_typing_after.gif?raw=true" width="48%" />
</p>

## Interactive Point-Based Video Segmentation

Annotators can interactively add or remove points to refine the segmentation results.
<p float="left">
  <img alt="camel" src="assets/interactive-camel.gif?raw=true" width="96.5%" />
  <img alt="drift" src="assets/interactive-drift-straight.gif?raw=true" width="96.5%" />
  <img alt="loading" src="assets/interactive-loading.gif?raw=true" width="96.5%" />
</p>

## Documentation
This is a guideline to how to get the program running!

1. [Getting Started](./docs/01-getting-started.md): Learn how to set up your environment and run the demo.
2. [Prepare Datasets](./docs/02-prepare-datasets.md): Instructions on acquiring and prepping necessary datasets.
3. [Prepare Checkpoints](./docs/03-prepare-checkpoints.md): Steps to fetch model checkpoints.
4. [Running Experiments](./docs/04-running-experiments.md): Details on how to execute experiments.

## References

 [SAM](https://github.com/facebookresearch/segment-anything), [PIPS](https://github.com/aharley/pips), [CoTracker](https://github.com/facebookresearch/co-tracker), [HQ-SAM](https://github.com/SysCV/sam-hq)
