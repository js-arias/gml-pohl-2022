# Pohl et al Unrotated Paleoclimate Models

This set of climate modes is imported from Pohl et al. (2022),
which are found in the [associated data](https://zenodo.org/record/6620748)
in that paper.

The climate reconstructions are unrotated
to present coordinates using the PaleoMap rotation model
[(Scotese, 2016)](https://github.com/js-arias/gm-paleomap),
so they can be used with any rotation model.

The climate types are taken directly from the Pohl et al. (2022) dataset
using the following conventions
to make them more or less compatible with the [EarthByte model](https://github.com/js-arias/gm-earthbyte):

Climate              | Key
-------------------- | ---
ice sheets           | 5
tundra               | 101
cold dry winter      | 103
cold dry summer      | 104
cold humid           | 105
temperate dry winter | 106
temperate dry summer | 107
temperate humid      | 108
desert               | 109
steppe               | 110
savanna              | 111
monsoon              | 112
tropical humid       | 113

Note that ice sheets follow climate model reconstructions.

## Time frame

The rotations are defined from 540 million years ago
(up to 600 for the plate motion model)
to today,
in time stages of 20 million years.

## Pixelation

The model is available in three resolutions:
e360 (360 pixels in the equatorial ring),
e180,
and e120.
For reference,
Pixel IDs are stored as `pixel-ids-xxx.tab`,
in which `xxx` is used to indicate the resolution.

## File descriptions

The model is stored in the file `pohl-landscape-unrot-xxx-20.tab`,
in which `xxx` is the pixel resolution
and 20 is the time resolution (in million years).

A color key, which is compatible with color blindness
and can be used with the `plates timepix map` [command](https://github.com/js-arias/earth),
is stored in the file `pohl-landscape-key.tab`.

## Rotating the model

To rotate the paleolandscape model,
use the command `plates` from the [earth package](https://github.com/js-arias/earth):

```bash
plates timepix rotate --model <your-model> --output <output-landscape-model> pohl-landscape-unrot-xxx-20.tab
```

Note that in such cases,
only pixels associated with a defined plate
will be rotated;
therefore,
some past features that appear in the original landscape model
might be lost.

## Citation and data license

This model is the product of the direct processing
of the Pohl et al. (2022) climate simulations.
As such,
the original publication should be cited
when the model is used.
Relevant papers are given in this file
and provided as bibTeX.

It is not required to cite this repository,
but if you do not include the model in the supplementary material
of your publication,
it might be a good idea to link this repository
and help others to replicate or re-use your analysis.

## Disclaimer

As the climate model was simulated
using the paleogeography model of Scotese (2016),
it is possible that when rotating it
with a different model,
some of the climate zones do not fit well.

As the models are a product of a pixelation of vectorial models,
it is possible that some pixels will not be defined,
particularly in the boundaries of plates.
Depending on the usage of the models,
this problem will be either annoying
(for example,
a deep ocean pixel in the middle of a continent)
or critical
(if the feature of interest is near the absent pixel).
So be careful when using the models.

## References

Pohl, A., Hearing, T.W., Franc, A., Sepulchre, P., Scotese, C.R.
(2022)
Dataset of Phanerozoic continental climate and Köppen–Geiger climate classes.
Data in Brief, 43: 108424.
DOI: [10.1016/j.dib.2022.108424](https://doi.org/10.1016/j.dib.2022.108424).

Scotese, C.R.
(2016)
PALEOMAP PaleoAtlas for GPlates.
URL: <https://www.earthbyte.org/paleomap-paleoatlas-for-gplates/>.
