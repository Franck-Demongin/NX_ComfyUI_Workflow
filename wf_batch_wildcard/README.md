# Batch from Wildcard

![exemple_1](https://github.com/Franck-Demongin/NX_ComfyUI_Workflow/assets/54265936/83a0fd4d-1580-41c2-b528-7b67f0148a13)

A workflow designed to simplify the generation of reference grids from the content of wildcard lists

## Features

- choice of file to analyse
- selection of starting index and number of lines to be generated (allows large lists to be 'split')
- choice of image destination directory in the ComfyUI "output" folder
- 4 prompts for each wildcard with the keyword _WILDCARD_. 
- for each wildcard, an image is created with the rendering of the 4 prompts and the wildcard value as a watermark
- create a reference grid with the generated images (works best with square images)

## Usage

Fill in the fields in the "PRESETS" group. 4 prompts, retaining the _WILDCARD_ keyword, Wildcard file source, starting index, selection range and output folder.
Set the KSampler parameters Model, Seed, Steps, CFG, Sampler and Scheduler.

To generate a batch, activate GENERATE in the "Fast Group Muter" node and deactivate GRID.  
To generate a grid, activate GRID and deactivate GENERATE. 

> [!NOTE]
> If you don't want to use the 4 prompts, disable the Loaders and the corresponding KSamplers and disconnect the KSamplers' image outputs from the "Make Image Batch" node.

> [!NOTE]
> The order of the prompts for each wildcard is determined by the order in which the KSamplers are connected to the "Make Image Bach" node.

![hero_wf_batch_wildcard](https://github.com/Franck-Demongin/NX_ComfyUI_Workflow/assets/54265936/dc94ca8e-3edc-4d17-ad91-5011ea41068f)



