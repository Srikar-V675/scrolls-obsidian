---
date: 2024-11-09 11:53
tags:
  - documentation
project: "[[SyncWise]]"
publish: true
---

# syncwise adding filtering and ordering in drf reference

**PROJECT:** [[SyncWise]]

To implement filtering of records in your Django REST Framework (DRF) API using query parameters, you can utilize the built-in filtering capabilities provided by DRF. This allows you to create flexible APIs that can handle various filtering criteria for your dashboards or other frontend components.

### Steps to Implement Filtering with Query Parameters in DRF

1. **Install Django Filter**: First, ensure you have the `django-filter` package installed. This package provides easy integration with DRF for filtering querysets.

   ```bash
   pip install django-filter
   ```

2. **Add to Installed Apps**: Include `django_filters` in your `INSTALLED_APPS` in `settings.py`:

   ```python
   INSTALLED_APPS = [
       ...
       'django_filters',
   ]
   ```

3. **Configure DRF to Use Django Filter**: Update your `settings.py` to include the default filter backends:

   ```python
   REST_FRAMEWORK = {
       'DEFAULT_FILTER_BACKENDS': (
           'django_filters.rest_framework.DjangoFilterBackend',
           'rest_framework.filters.OrderingFilter',  # Optional: for ordering
           'rest_framework.filters.SearchFilter',  # Optional: for search functionality
       ),
   }
   ```

4. **Define Your ViewSet with Filtering**: In your viewset, specify which fields can be filtered. You can use the `filterset_fields` attribute to define this.

   Here’s an example of a viewset that allows filtering:

   ```python
   from rest_framework import viewsets
   from django_filters import rest_framework as filters
   from .models import StudentMetadata  # Assuming this is your model for student metadata
   from .serializers import StudentMetadataSerializer

   class StudentMetadataFilter(filters.FilterSet):
       cgpa = filters.RangeFilter()  # Allows filtering by CGPA range
       user__username = filters.CharFilter(field_name='user__username', lookup_expr='icontains')  # Filter by username

       class Meta:
           model = StudentMetadata
           fields = ['cgpa', 'user__username']  # Add other fields as needed

   class StudentMetadataViewSet(viewsets.ModelViewSet):
       queryset = StudentMetadata.objects.all()
       serializer_class = StudentMetadataSerializer
       filterset_class = StudentMetadataFilter  # Set the filter class here

   ```

5. **Accessing Filtered Data**: You can now access filtered data using query parameters in your API requests. For example:

   - To filter by CGPA range:
     ```
     GET /api/student-metadata/?cgpa_min=2.0&cgpa_max=3.5
     ```

   - To filter by username:
     ```
     GET /api/student-metadata/?user__username=john
     ```

### Example URL Queries

Here are some example queries you might use based on the setup above:

- **Filtering by CGPA**:
  ```
  GET /api/student-metadata/?cgpa_min=2.5&cgpa_max=3.8
  ```

- **Filtering by Username**:
  ```
  GET /api/student-metadata/?user__username=john
  ```

### Additional Features

- **Ordering**: You can also implement ordering by adding an `ordering_fields` attribute to your viewset:
  
  ```python
  class StudentMetadataViewSet(viewsets.ModelViewSet):
      ...
      ordering_fields = ['cgpa', 'user__username']  # Specify fields that can be ordered
      ordering = ['cgpa']  # Default ordering if needed
  ```

- **Searching**: If you want to implement search functionality, you can add `SearchFilter` and define searchable fields:
  
  ```python
  from rest_framework import filters

  class StudentMetadataViewSet(viewsets.ModelViewSet):
      ...
      search_fields = ['user__username', 'other_field']  # Specify searchable fields
  ```

### Conclusion

By following these steps, you can effectively implement filtering of records in your DRF API using query parameters. This setup will allow your frontend applications (like dashboards) to dynamically request data based on user-defined criteria, enhancing the user experience and providing relevant information efficiently. 

This approach also maintains a clean separation between different aspects of your application, making it easier to manage updates and changes independently across different models and their associated metadata.

Citations:
[1] https://forum.djangoproject.com/t/parsing-and-validating-query-params-from-get-request/24308
[2] https://djangocentral.com/capturing-query-parameters-of-requestget-in-django/
[3] https://stackoverflow.com/questions/48299466/django-rest-framework-passing-parameters-with-get-request-classed-based-views
[4] https://www.youtube.com/watch?v=f_d1fQUHvVI
[5] https://corgibytes.com/blog/2022/06/14/model-relationships-django-rest-framework/
[6] https://www.django-rest-framework.org/api-guide/generic-views/
[7] https://tech.serhatteker.com/post/2021-11/django-rest-query-part-1/
[8] https://www.reddit.com/r/django/comments/12rspek/in_drf_do_you_validate_your_query_params_if_so_how/