# media-sound/easyeffects

### calf
Pull in the [media-plugins/calf](../media-plugins/calf.md) package as a dependency and make sure it has the `lv2` flag enabled. Calf is an LV2 and JACK audio plugin pack geared towards a professional audience.

It is safe to disable this flag.

### doc
Pull in the [gnome-extra/yelp](../gnome-extra/yelp.md) package as a dependency to install the Gnome help viewer tool Yelp, so that users can access Easy Effects documentation.

This flag can be safely disabled.

### mda-lv2
Pull in the [media-plugins/mda-lv2](../media-plugins/mda-lv2.md) package as a dependency to install LV2 port of the MDA plugins by Paul Kellet. It is a collection of 36 high-quality plugins for a variety of tasks, such as multi-band distortion, compressor, limiter, gate, signal generator, etc.

It is safe to disable this flag.

### zamaudio
Pull in the [media-plugins/zam-plugins](../media-plugins/zam-plugins.md) package as a dependency - a collection of LV2/LADSPA/VST/JACK audio plugins for sound processing developed in-house by [ZamAudio](https://www.zamaudio.com/?p=976).

This flag can be safely disabled.
