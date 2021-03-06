# OGC Linked Data API Profile
A profile (of various Semantic Web standards) that provides a data model for OGC LD API systems.

This profile specifies the "shape" of data elements needed for instnaces of OGC APIs but additionally requires certain Linked Data characteristics of data. The result is a requirement for "OGC _LD_ API" data that is a superset of OGC API data and a subset of (the infinite) Linked Data world.

The classes of data required for an OGC API are:

1. _LandingPage_
2. _FeatureCollections_
3. _Feature_

Our interpretation of this is that the following Semantic Web / Linked Data classes of object correspond to those above:

1. `dcat:Dataset` (and possibly a `dcat:DataService` but this isn't implemented yet) - as per [DCAT]()
2. `geo:FeatureCollection` - as per [GeoSPARQL 1.1]()
3. `geo:Feature` - as per the original [GeoSPARQL]()

The OGC LD API requires data objects in of these classes to have certain properties - titles, IDs, geometries etc. - and a [SHACL Shape validator]() is provided to validate that data to be used by API instances actually does contain these elements.

This profile is hosted online in [Linked Data](https://www.w3.org/standards/semanticweb/data) form using a persistent web address:

* <https://w3id.org/profile/ogcldapi>


## License  
This code is licensed using the [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) licence. See the [LICENSE file](LICENSE) for the deed. 

Note [Citation](#citation) below for attribution.


## Citation
To cite this profile, please use the following (formulated in [BibTex](http://www.bibtex.org/)):

```
@software{ogcldapi-profile,
  author = {{SURROUND Australia Pty Ltd}},
  title = {{OGC Linked Data API Profile}},
  version = {1.0},
  date = {2021},
  publisher = {{SURROUND Australia Pty Ltd}},
  url = {https://w3id.org/profile/ogcldapi}
}
``` 


## Contact
*publisher:*  
![](style/SURROUND-logo-100.png)  
**SURROUND Australia Pty. Ltd.**  
<https://surroundaustralia.com>  

*creator:*  
**Dr Nicholas J. Car**  
*Data Systems Architect*  
SURROUND Australia Pty. Ltd.  
<nicholas.car@surroudaustralia.com>  
<https://orcid.org/0000-0002-8742-7730>
