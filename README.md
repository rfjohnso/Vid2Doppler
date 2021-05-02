# Vid2Doppler: Synthesizing Doppler Radar Data from Videos for Training Privacy-Preserving Activity Recognition

This is the research repository for Vid2Doppler (CHI 2021) containing the code for:

* Generating synthetic Doppler data from videos
* Evaluating the activity recogntion classifier trained on synthetically generated Doppler data only, on the real world Doppler dataset presented in the paper.

More details for the project can be found here.

## Environment Setup

We first recommend setting up `conda` or `virtualenv` to run an independent setup.

After cloning the git repository, in the Vid2Doppler folder:

1. Create a conda environment: 

```
conda create -n vid2dop python=3.7
conda activate vid2dop
pip install -r requirements.txt
```

2. Install the [pybody library](https://github.com/MPI-IS/mesh) for the `mesh` visualization. In particular:

```
git clone https://github.com/MPI-IS/mesh.git
```
In the mesh folder, run:
```
BOOST_INCLUDE_DIRS=/path/to/boost/include make all
```
Now go to the `Python` folder in `Vid2Doppler` and replace the `meshviewer.py` installed by pybody with the custom one:
```
cp meshviewer.py $CONDA_PREFIX/lib/python3.7/site-packages/psbody/mesh/meshviewer.py
```
In case of using some other virtual environment manager, replace the `meshviewer.py` file installed by psbody with the one provided.

3. Run the following command in the `Python` folder to get the pretrained VIBE pose model in the:
```
source ../Environment/prepare_data.sh
```

## Dataset and Models

Use the links below to download the:

* [Real world Doppler dataset](https://www.dropbox.com/s/adh22md432ixq7v/data.zip?dl=0) collected across 10 participants and 12 activities. Details found in paper here. 
* [Deep learning models](https://www.dropbox.com/s/a10ec6lau3loeec/models.zip?dl=0) for our classifier trained solely on synthetically generated Doppler data and encoder-decoder NN.
* [Sample Videos](https://www.dropbox.com/s/bt67l4d1g7mjm9g/sample_video.zip?dl=0) for demo purposes.

You can download and unzip the above in the `Vid2Doppler` folder.


## Usage

	python doppler_from_vid.py --input_video YOUR_INPUT_VIDEO_FILE

	Other options:
		--visualize_mesh : output visualized mesh
		--wireframe : output wireframe video results (otherwise, output mesh video results)


 



