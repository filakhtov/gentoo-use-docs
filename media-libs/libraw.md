# media-libs/libraw

### lcms
Pass the `--enable-lcms` option to the configure script. Use the LittleCMS color management system to handle ICC color profiles when handling RAW images, e.g. loading profiles externally, from file, or using profiles embedded into RAW images.

It is recommended to enable this flag for more accurate color handling in RAW images.

### openmp
Pass the `--enable-openmp` option to the configure script. Use the OpenMP API to parallelize various image processing routines, such as interpolation, demosaicing, denoising, etc, across multiple cores, threads or processors.

This flag should be enabled if there is a need to parallelize RAW image processing.

### examples
Pass the `--enable-examples` option to the configure script. Build and install additional example programs:

- `raw-identify` - prints the values of the fields of the imgdata structure, metadata, white balance tables, etc;
- `simple_dcraw` - a simple "emulation" of `dcraw` tool reproducing some of its behavior;
- `4channnels` - splits RAW-file into four separate 16-bit grayscale TIFFs (per RAW channel);
- `unprocessed_raw` - extracts unaltered RAW data including masked pixels data;
- `mem_image` - writes data in PPM format;
- `dcraw_half` - demonstrates the use of C API by emulating the behavior of `dcraw -h` producing binary-identical results.
- `half_mt` - emulation of `dcraw -h` with additional options, i.e.: `-a` (automatic white balance over the entire image), `-w` (white balance of the camera), `-T` (output in the tiff format), and `-J` n (number of parallel threads launched for image processing);
- `multirender_test` - simple example of multiple rendering on one file without reopen;
- `postprocessing_benchmark` - print timings of RAW processing steps;
- `dcraw_emu` - complete emulation of dcraw.

This flag can be safely disabled if there is no need to use one of the aforementioned tools.

### jpeg
Pass the `--enable-jpeg` option to the configure script. Use the `libjpeg` library to provide support for lossy compressed DNG (Digital Negative) photo format.

It is safe to disable the flag, unless there is an explicit need to deal with lossy-compressed DNG images.

### jpeg2k
Pass the `--enable-jasper` option to the configure script. Use the `libjasper` library to provide support for the Redcode R3D proprietary RAW image format (JPEG2000 compressed RAW frames).

This flag should only ever be enabled if there is a need to handle Redcode RAW image format.
