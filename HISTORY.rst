.. :changelog:

History
-------
0.3.5 (2023-01-19)
~~~~~~~~~~~~~~~~~~
* Support Django >= 4.2
* Remove NullBooleanField

0.3.4 (2019-02-25)
~~~~~~~~~~~~~~~~~~

* Added ``EnforceValidationFieldMixin.capture_failed_field``, ``FormSerializerFieldMixin.capture_failed_field``,
  and ``FormSerializerBase.capture_failed_fields`` to capture the optional fields that failed.

0.3.3 (2019-02-21)
~~~~~~~~~~~~~~~~~~

* Fixing invalid data being copied over in ``FormSerializer`` when fail mode is not ``fail``

0.3.2 (2018-11-21)
~~~~~~~~~~~~~~~~~~

* Fixing ``DoubleAsStrJsonEncoder`` by subclassing from DRF which supports datetimes, etc

0.3.1 (2018-11-07)
~~~~~~~~~~~~~~~~~~

* Fixing ``SwappingSerializerMixin`` by supporting ``ListSerializer``

0.3.0 (2018-11-05)
~~~~~~~~~~~~~~~~~~

* Added ``SwappingSerializerMixin``.
  Allows to declaratively swap fields any field instances in child serializers.
* Added ``DoubleAsStrJsonEncoder`` for handicapped API clients.

0.2.3 (2017-10-18)
~~~~~~~~~~~~~~~~~~

* Fixed how choices are normalized in ``SerializerForm`` to ``[(key, key)]``
  vs previously ``[(key, value)]`` to match DRF's handling of choices unlike Django forms.
* Added support for ``Form.all_fields`` and ``Form.all_base_fields``
  in ``SerializerForm`` which supports custom form classes which implement such API.
* Added support for ``FormSerializer.Meta.exclude`` which allows to specify fields to exclude.

0.2.2 (2017-05-09)
~~~~~~~~~~~~~~~~~~

* Added ``rounding`` parameter to ``RoundedDecimalField`` which allows to define rounding direction
  when rounding value.

0.2.1 (2017-04-27)
~~~~~~~~~~~~~~~~~~

* Fixed bugs in ``RoundedDecimalField``

0.2.0 (2017-04-25)
~~~~~~~~~~~~~~~~~~

* Added ``RoundedDecimalField`` for rounding off decimal to specified ``decimal_places``
  instead of validing that higher precision is not allowed
* Added ``URLField`` for automatic mapping between django forms and DRF serializers

0.1.6 (2016-02-29)
~~~~~~~~~~~~~~~~~~

* Fixed a bug in ``SerializerForm`` in which form cleaned data was replaced with serializer data
  instead of updating it.

0.1.5 (2015-07-15)
~~~~~~~~~~~~~~~~~~

* Fixed a bug in ``EnforceValidationFieldMixin`` that it was overwriting ``to_internal_value`` instead of ``run_validation``

0.1.4 (2015-07-13)
~~~~~~~~~~~~~~~~~~

* Test coverage is now at 100%!

0.1.3 (2015-07-10)
~~~~~~~~~~~~~~~~~~

* Fixed bugs in ``AllowBlankNullFieldMixin``
* All DRF fields not subclass both ``AllowBlankNullFieldMixin`` and ``EmptyStringFieldMixin``

0.1.2 (2015-07-02)
~~~~~~~~~~~~~~~~~~

* Added custom ``to_representation()`` to ``EmptyStringFieldMixin`` which allows to pass empty string or ``None`` values.
  This is especially useful for fields like ``IntegerField`` which would blow up when passing empty string value for non-required fields.

0.1.1 (2015-06-25)
~~~~~~~~~~~~~~~~~~

* Fixed a bug in ``FormSerializer`` which did not honor ``field_mapping`` in any of the subclasses

0.1.0 (2015-06-15)
~~~~~~~~~~~~~~~~~~

* First release on PyPI.
