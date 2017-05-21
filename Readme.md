[[中文版](./Readme_zh-TW.md)]

# Introduction
The scripts in this project are developed only for gcode generated by [KISSlicer](http://www.kisslicer.com/). To use the scripts in this folder, you should have [Python 3.x ](https://www.python.org/downloads/) installed.
You can run the script in KISSlicer,
> 1. Download the scripts to KISSlicer folder.
> 2. In KISSlicer, switch to `Printer` tab. Then select `Firmware` sub-tab.
> 3. add script command line in `Posr-Process`. ex: `dgm-temp-tower.py -p "<FILE>"`
> ![](./image/post-process.png)
>
> Use & to execute scripts sequentially
> ex: `dgm-heatbed-off.py "<FILE>" 1 & dgm-pause.py -p "<FILE>" 5`
> Turn off heatbed at 1mm height, and pause print at 5mm height.

Or run the script in Command Prompt
> `C:\KISSlicer> dgm-temp-tower.py yourfile.gcode`

# Usage of scripts
## Common arguments
* `-p，--pause`
  Before scripts end, wait any key to check messages. It's useful when the script is called in KISSlicer.

## Heatbed Off
- Description: Turn off heatbed at specified height
- Usage:
	dgm-heatbed-off.py [-p] input-file height
	* **input-file**:
	* **height**:

## Pause
- Description: Pause print at specified height
- Usage:
	dgm-pause.py [-p] [-z ZLIFT] [-x X_LOC] [-y Y_LOC] [-c] input-file height [height ...]
	* **input-file**:
	* **height**:
	* `-z ZLIFT`:
	* `-x X_LOC`:
	* `-y Y_LOC`:
	* `-c`:

## Temperature Tower
- Description: Insert temperature control command for temperature tower test
- Model: [Better Temperature Tower v5 220-180](https://www.thingiverse.com/thing:2222308)
- Usage:
	dgm-temp-tower.py [-p] [-zo Z_OFFSET] [-zs Z_STEP] [-to TEMP_OFFSET] [-ts TEMP_STEP] input-file
	* **input-file**:
	* `-zo Z_OFFSET`: The height of first test block. Default value is 1.8 mm.
	* `-zs Z_STEP`: The thickness of each test block. Default value is 7.0 mm.
	* `-to TEMP_OFFSET`: The temperature of first test block. Default value is 220 C.
	* `-ts TEMP_STEP`: The temperature increased for each test block. Default value is -5 C.
	* All default values of arguments are designed for [Better Temperature Tower v5 220-180](https://www.thingiverse.com/thing:2222308)
