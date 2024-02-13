# NX_ComfyUI_Workflow

Workflows for ComfyUI, Stable Diffusion's nodal interface

## Usage

- Drag the image of a workflow directly onto the ComfyUI interface to load it.
- Drag the PNG image of a workflow directly onto the ComfyUI interface to load it.
Open a workflow file in JSON format from the ComfyUI sidebar > Load

If some nodes appear in red, they have not yet been installed.
Use [ComfyUI_Managers](https://github.com/ltdrdata/ComfyUI-Manager) to easily install the missing nodes.

## Batch from CSV

![_grid_styles](https://github.com/Franck-Demongin/NX_ComfyUI_Workflow/assets/54265936/7216bf93-4a32-4e4b-9b7b-1273a42c04b4)

A workflow designed to simplify the generation of reference grids from the content of CSV files used to style prompts.
It is suitable for CSV files with the following characteristics:
- a header line with two fields. The first contains the name of the field (for example _Double Exposure_), the second its value (_"double exposure shot"_).
- the "value" field can contain commas if it is surrounded by quotation marks " but only the first 3 will be retrieved (a value such as _"photorealistic, professional, Skin details, RAW Photo, ultra detailed"_ will be truncated into _"photorealistic, professional, Skin details"_)

### Features

- choice of file to parse, name, extension and paths: _File Name_, _Extension_ and _Path to CSV_
- selection of CSV line to use (0 to generate all): _Select_
- number of header lines to ignore: _Skip Lines_
- customisable prompt containing the *\_keyword\_* token (it will be replaced by the terms extracted from each line of the CSV file): _Prompt_
- automatic watermarking of each image with the value of the name field and the number of lines in the CSV file (except header lines)
- create a reference grid with the generated images (works best with square images)
- Image viewer for easy consultation of the images created

> [!NOTE]
> _The path to the directory containing the CSV files can be absolute or relative. Use an absolute path to indicate a directory outside the ComfyUI installation folder.
> If the CSV files are in the ComfyUI installation directory, you can try using a relative path starting with ./ (./input/CSV/ for example. Don't forget the final /!)._

### Usage

- fill in the fields in group 1 _Config_.
- if it is inactive, activate group 2 _Generate Image_ (right-click on the group header > Set Group Nodes to Always), set the rendering parameters for your images (choice of template, sampler, negative prompt, watermark characteristics, etc), run the image rendering and... wait! 
- You can restart the rendering of a specific image if there are any misfires in the batch: enter its number in the Select field and restart the rendering; only this image will be recreated.
- when all the images have been generated (and corrected if necessary), deactivate group 2 (right-click > Bypass Group Nodes) and activate group 3 _GRID_, set the grid parameters (number of columns, thumbnail sizes, etc.) then render again. The generated grid will be saved in the same directory as the images.

![wf_batch_from_CSV](https://github.com/Franck-Demongin/NX_ComfyUI_Workflow/assets/54265936/bc54c114-1aac-4c05-af02-ce6fde11e79b)

***Enjoy!***

