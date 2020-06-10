# Police Data Initiative Officer Shootings Analysis

- Datasets from [PDI](https://www.policedatainitiative.org/datasets/officer-involved-shootings/)
- No need to download files locally when you can use Python Pandas and read_csv / read_excel to parse and display data nicely
- TODO: further analysis

## Links to Datasets (with some comments/witty criticism)

```python
police_shooting_datasets = {
    'Seattle_WA': 'https://data.seattle.gov/api/views/mg5r-efcm/rows.csv?accessType=DOWNLOAD',
    'Tacoma_WA': 'https://data.cityoftacoma.org/api/views/4zem-9yq6/rows.csv?accessType=DOWNLOAD',
    'Waterbury_VT': 'https://data.vermont.gov/api/views/du86-kfnp/rows.csv?accessType=DOWNLOAD',
    'Fairfax_VA': 'https://opendata.arcgis.com/datasets/f4d29ffadcd34a52bcecefef6f0146da_1.csv',
    'Hampton_VA': 'https://data.hampton.gov/api/views/nhh2-ywzf/rows.csv?accessType=DOWNLOAD',

    # BULLSHIT : need to create an account to view data (in Socrata site like other sites but this one is locked behind account auth)
    'Austin_TX': 'https://data.austintexas.gov/api/views/eqwy-k8kh/rows.csv?accessType=DOWNLOAD',


    'Dallas_TX': 'https://www.dallasopendata.com/api/views/4gmt-jyx2/rows.csv?accessType=DOWNLOAD',
    'Philadelphia_PA': 'https://phl.carto.com/api/v2/sql?q=SELECT+*,+ST_Y(the_geom)+AS+lat,+ST_X(the_geom)+AS+lng+FROM+shootings&filename=shootings&format=csv&skipfields=cartodb_id',
    'Portland_OR': 'https://public.tableau.com/views/PPBOpenDataDownloads/OIS-All.csv?:showVizHome=no',
    'Cincinnati_OH': 'https://data.cincinnati-oh.gov/api/views/r6q4-muts/rows.csv?accessType=DOWNLOAD',

    # only 2016
    'Henderson_NV': 'https://cityofhenderson.com/docs/default-source/police-docs/police-data-initiative/2016-hpd-ois-incidents.csv?sfvrsn=2',

    # only excel format
    'Sparks_NV': 'http://www.sparkspolice.com/wp-content/uploads/2019/04/2000-2018-SPD-OIS-Incidents-1.xlsx',

    # points to invalid page
    'LasCruses_NM': 'https://goo.gl/vtX1bC',


    'Charlotte_NC': 'https://opendata.arcgis.com/datasets/595b1e7d04a54d36a166340a4fdf6e3e_11.csv?outSR=%7B%22latestWkid%22%3A2264%2C%22wkid%22%3A102719%7D',

    # no excel ugh
    'Springfield_MO': 'https://www.springfieldmo.gov/3755/Officer-Involved-Shootings',

    # not found
    'Lansing_MI': 'http://data-lansing.opendata.arcgis.com/404',
    'Louisville_KY': 'https://data.louisvilleky.gov/sites/default/files/2020%20LMPD%20OIS%20Database%20-%205-6-2020_0.xlsx',
    'Bloomington_IN': 'https://data.bloomington.in.gov/dataset/8a7416cf-5362-4b2e-851d-e9ce3b0c9043/resource/9f06e35a-a956-4bd6-bf5f-6e117623167c/download/2020-first-quarter-officer-involved-shootings.xlsx',

    # have to click button
    'Indianapolis_IN': 'https://www.projectcomport.org/department/IMPD/schema/officerinvolvedshootings/',

    # no shooting data
    'StJohn_IN': 'https://www.stjohnin.com/PD/PDI/',

    # must click button
    'Atlanta_GA': 'http://opendata.atlantapd.org/Crimedata/OfficerInvolvedShootings.aspx',

    
    'Jacksonville_FL': 'http://transparency.jaxsheriff.org/OIS/Export',
    'Orlando_FL': 'https://data.cityoforlando.net/api/views/6kz6-6c7n/rows.csv?accessType=DOWNLOAD',
    'Hartford_CT': 'https://data.hartford.gov/api/views/dzbp-kiee/rows.csv?accessType=DOWNLOAD',
    'Norwich_CT': 'https://www.norwichct.org/Archive.aspx?ADID=922',
    'Denver_CO': 'https://www.denvergov.org/media/gis/DataCatalog/denver_police_officer_involved_shootings/csv/denver_police_officer_involved_shootings.csv',
    'LA_CA_Suspect': 'https://data.lacounty.gov/api/views/d6xt-ws3m/rows.csv?accessType=DOWNLOAD&bom=true&format=true',
    'LA_CA_Deputy': 'https://data.lacounty.gov/api/views/xutq-azb6/rows.csv?accessType=DOWNLOAD',
    'LA_CA_NonSuspect': 'https://data.lacounty.gov/api/views/3q3t-7t2n/rows.csv?accessType=DOWNLOAD',

    # pdf only
    'Redondo_CA': 'https://www.redondo.org/civicax/filebank/blobdload.aspx?BlobID=37552',


    'SF_CA': 'https://www.sanfranciscopolice.org/sites/default/files/2020-02/SFPDListOfOISInv20200205.pdf',
    'Tucson_AZ': 'https://opendata.arcgis.com/datasets/abb29a901bfd4d63a8148e0b34d99c48_34.csv?outSR=%7B%22latestWkid%22%3A2868%2C%22wkid%22%3A2868%7D'
}
```