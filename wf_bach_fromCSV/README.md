# Batch from CSV

![exemple_1](https://github.com/Franck-Demongin/NX_ComfyUI_Workflow/assets/54265936/1ce9d605-d86e-421d-9036-429f34cd3a37)


A workflow designed to simplify the generation of reference grids from the content of CSV files used to style prompts.
It is suitable for CSV files with the following characteristics:
- a header line with two fields. The first contains the name of the field (for example _Double Exposure_), the second its value (_"double exposure shot"_).
- the "value" field can contain commas if it is surrounded by quotation marks " but only the first 3 will be retrieved (a value such as _"photorealistic, professional, Skin details, RAW Photo, ultra detailed"_ will be truncated into _"photorealistic, professional, Skin details"_)

## Features

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

## Usage

- fill in the fields in group 1 _Config_.
- if it is inactive, activate group 2 _Generate Image_ (right-click on the group header > Set Group Nodes to Always), set the rendering parameters for your images (choice of template, sampler, negative prompt, watermark characteristics, etc), run the image rendering and... wait! 
- You can restart the rendering of a specific image if there are any misfires in the batch: enter its number in the Select field and restart the rendering; only this image will be recreated.
- when all the images have been generated (and corrected if necessary), deactivate group 2 (right-click > Bypass Group Nodes) and activate group 3 _GRID_, set the grid parameters (number of columns, thumbnail sizes, etc.) then render again. The generated grid will be saved in the same directory as the images.

![hero_wf_batch_from_CSV](https://github.com/Franck-Demongin/NX_ComfyUI_Workflow/assets/54265936/868a6f4d-4761-4448-9181-9be49a279f49)

***Enjoy!***

