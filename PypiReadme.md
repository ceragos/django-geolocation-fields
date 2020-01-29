django-geolocation-fields
-------------------------
A Django app to facilitate the manipulation of Geolocation objects in a GeoDjango app without using a spatial database.

Detailed documentation is in the "docs" directory.

Quick start
-----------

The project is still in development

Here is an example that uses it https://github.com/syk1k/django-geolocation

1. Add "geolocation_fields" to your INSTALLED_APPS setting like this:
    ```python
    INSTALLED_APPS = [
        #...
        'geolocation_fields',
    ]
    ```

2. Add a PointField to a model:
    ```python
    from geolocation_fields.models import fields
    field_name = fields.PointField(verbose_name='field_name')
    ```

3. Configurations 
    To have more control over the package, you can canfigure it yourself

    By default the PointField's widget only display the map, 
    you can also chose to display the editable input field in the settings
    ```python
    GEOLOCATION_FIELD = {
        'display_input': True, # Display the input field. False to remove
    }
    ```

    This version of the package integrate leaflet only.
    Here is the default configuration for the fields (PointField for the moment).
    The configurations uses leaflet Map options. Check the leafletJS 
    [doc here](https://leafletjs.com/)
    ```python
    GEOLOCATION_FIELD = {
        "provider": "leaflet", # Two provider: Leaflet, Mapbox
        "center" : [0,0],
        "zoom": 12,
        'display_input': False,
    }