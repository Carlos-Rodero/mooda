# Package overview

Oceanobs package primary goal is to help scientists to understand their oceanographic data, i.e., to facilitate the read and the analysis of data coming from marine observatories. The package contains modules with functions to read data in different formats and translates them into an internal data format called WaterFrame. The object WaterFrame includes the scientific data and metadata but also provides for functions to process the data and make plots.

Data imported to a WaterFrame will include QC Flags. If the original data does not contain the flags, they will be created during the importation. The flags help decide if the data is useful for a particular study.

Oceanobs, like most of the python package, contains many modules with different classes and functions. Each module will execute a part of the specific data study. We divide the modules into three types (view Fig. 1):

* Data access modules: These contain classes to download, open, and translate data incoming from marine observatories to a WaterFrame;
* Analysis modules: These provide functions and classes for processing and analyzing data already in a WaterFrame;
* App modules: These contain a set of classes and services to offer apps to help users to use oceanobs without the need of typing code.

<center>
    <figure>
        <img src="./img/package/module_types.png" alt="Module types of oceanobs" style="height:50px">
        <figcaption> Figure 1: Module types of oceanobs </figcaption>
    </figure>
</center>   

Data access modules are located in oceanobs/access folder. At the moment we only have implemented a module called egim.py. The module is used to download data from EMSO Generic Instrument Modules ([EGIMs](http://www.emsodev.eu)). Following the general idea of the access modules, the downloaded data is saved in WaterFrames so that it can be easily analyzed.

Oceanobs can also read netCDF files (with SeaDataNet format) and serialized WaterFrames as Pickle files. The functions to open this type of data have been implemented directly in the WaterFrame object since these files are not specific to a specific platform.

Analysis modules are located in the root of the package. Right now, we have waterframe.py, that contains the code of the WaterFrame object, and plotmap.py, that is a module to make data visualization on a static map.

App modules are located in oceanobs/app/[name of the app] folder. The idea is that each app will be placed in a different folder inside oceanobs/app folder. We have developed an app called "Module for Ocean Observatory Data Analysis" (MOODA). With MOODA, users could use most of the oceanobs package functionalities without the need of write code.