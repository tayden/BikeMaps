Bike-maps
=========
######TODO: Flesh out Readme

[http://bikemaps.org]

###A [SPARLab](http://www.geog.uvic.ca/spar/) project. 
A database driven webapp that allows users to submit bike accidents and near-misses. Data is analyzed to detect areas/routes with high traffic and rates of incidents.  


##### Requirements
  + Django==1.6.4
  + Python==2.7.6
  + psycopg2==2.5.3
  + Markdown==2.3.1
  + Pillow==2.4.0
  + Whoosh==2.5.7
  + django-appconf==0.6
  + django-compressor==1.4
  + django-crispy-forms==1.4.0
  + django-debug-toolbar==1.2.1
  + django-djconfig==0.1.4
  + django-haystack==2.1.0
  + django-infinite-scroll-pagination==0.1.1
  + django-geojson==2.5.0
  + pytz==2014.4
  + six==1.7.3
  + sqlparse==0.1.11
  + wsgiref==0.1.2

##### People
  + Dr. Trisalyn Nelson (Project Lead)
  + Taylor Denouden (Developer)
  + James Stephaniuk (Developer)


##### Setup
  Starting this django project requires the following:

  Prereqs:
    A postgresql database named bikeDB with postgis extension installed 
    All requirements
      + pip install -r requirements.txt

  Then, run:
    python manage.py syncdb
    python manage.py loaddata spirit_init
    python manage.py createcachetable spirit_cache
    # python manage.py collectstatic # In future, after static root is set (not yet implemented)

  Then running
    python manage.py runserver
    and visiting localhost:8000 should show the page on any dev computer


##### Data output
  Data is output by loggin into an admin account and selecting "Data to GeoJson" under the user dropdown menu in the navbar
  This geojson data can be used directly by QGis or converted to a shapefile using ogr2ogr tools.
  The easiest method to convert the output geojson text to a shapefile is to copy it from the webpage and
    past into the "Convert from GeoJSON" box at http://ogre.adc4gis.com/
