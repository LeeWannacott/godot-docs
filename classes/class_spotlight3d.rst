:github_url: hide

.. DO NOT EDIT THIS FILE!!!
.. Generated automatically from Godot engine sources.
.. Generator: https://github.com/godotengine/godot/tree/master/doc/tools/make_rst.py.
.. XML source: https://github.com/godotengine/godot/tree/master/doc/classes/SpotLight3D.xml.

.. _class_SpotLight3D:

SpotLight3D
===========

**Inherits:** :ref:`Light3D<class_Light3D>` **<** :ref:`VisualInstance3D<class_VisualInstance3D>` **<** :ref:`Node3D<class_Node3D>` **<** :ref:`Node<class_Node>` **<** :ref:`Object<class_Object>`

A spotlight, such as a reflector spotlight or a lantern.

.. rst-class:: classref-introduction-group

Description
-----------

A Spotlight is a type of :ref:`Light3D<class_Light3D>` node that emits lights in a specific direction, in the shape of a cone. The light is attenuated through the distance. This attenuation can be configured by changing the energy, radius and attenuation parameters of :ref:`Light3D<class_Light3D>`.

\ **Note:** When using the Mobile rendering method, only 8 spot lights can be displayed on each mesh resource. Attempting to display more than 8 spot lights on a single mesh resource will result in spot lights flickering in and out as the camera moves. When using the Compatibility rendering method, only 8 spot lights can be displayed on each mesh resource by default, but this can be increased by adjusting :ref:`ProjectSettings.rendering/limits/opengl/max_lights_per_object<class_ProjectSettings_property_rendering/limits/opengl/max_lights_per_object>`.

\ **Note:** When using the Mobile or Compatibility rendering methods, spot lights will only correctly affect meshes whose visibility AABB intersects with the light's AABB. If using a shader to deform the mesh in a way that makes it go outside its AABB, :ref:`GeometryInstance3D.extra_cull_margin<class_GeometryInstance3D_property_extra_cull_margin>` must be increased on the mesh. Otherwise, the light may not be visible on the mesh.

.. rst-class:: classref-introduction-group

Tutorials
---------

- :doc:`3D lights and shadows <../tutorials/3d/lights_and_shadows>`

- `Third Person Shooter Demo <https://godotengine.org/asset-library/asset/678>`__

.. rst-class:: classref-reftable-group

Properties
----------

.. table::
   :widths: auto

   +---------------------------+----------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
   | :ref:`float<class_float>` | shadow_bias                                                                      | ``0.03`` (overrides :ref:`Light3D<class_Light3D_property_shadow_bias>`)       |
   +---------------------------+----------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
   | :ref:`float<class_float>` | shadow_normal_bias                                                               | ``1.0`` (overrides :ref:`Light3D<class_Light3D_property_shadow_normal_bias>`) |
   +---------------------------+----------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
   | :ref:`float<class_float>` | :ref:`spot_angle<class_SpotLight3D_property_spot_angle>`                         | ``45.0``                                                                      |
   +---------------------------+----------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
   | :ref:`float<class_float>` | :ref:`spot_angle_attenuation<class_SpotLight3D_property_spot_angle_attenuation>` | ``1.0``                                                                       |
   +---------------------------+----------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
   | :ref:`float<class_float>` | :ref:`spot_attenuation<class_SpotLight3D_property_spot_attenuation>`             | ``1.0``                                                                       |
   +---------------------------+----------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
   | :ref:`float<class_float>` | :ref:`spot_range<class_SpotLight3D_property_spot_range>`                         | ``5.0``                                                                       |
   +---------------------------+----------------------------------------------------------------------------------+-------------------------------------------------------------------------------+

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Property Descriptions
---------------------

.. _class_SpotLight3D_property_spot_angle:

.. rst-class:: classref-property

:ref:`float<class_float>` **spot_angle** = ``45.0``

.. rst-class:: classref-property-setget

- void **set_param** **(** :ref:`float<class_float>` value **)**
- :ref:`float<class_float>` **get_param** **(** **)**

The spotlight's angle in degrees.

\ **Note:** :ref:`spot_angle<class_SpotLight3D_property_spot_angle>` is not affected by :ref:`Node3D.scale<class_Node3D_property_scale>` (the light's scale or its parent's scale).

.. rst-class:: classref-item-separator

----

.. _class_SpotLight3D_property_spot_angle_attenuation:

.. rst-class:: classref-property

:ref:`float<class_float>` **spot_angle_attenuation** = ``1.0``

.. rst-class:: classref-property-setget

- void **set_param** **(** :ref:`float<class_float>` value **)**
- :ref:`float<class_float>` **get_param** **(** **)**

The spotlight's *angular* attenuation curve. See also :ref:`spot_attenuation<class_SpotLight3D_property_spot_attenuation>`.

.. rst-class:: classref-item-separator

----

.. _class_SpotLight3D_property_spot_attenuation:

.. rst-class:: classref-property

:ref:`float<class_float>` **spot_attenuation** = ``1.0``

.. rst-class:: classref-property-setget

- void **set_param** **(** :ref:`float<class_float>` value **)**
- :ref:`float<class_float>` **get_param** **(** **)**

The spotlight's light energy (drop-off) attenuation curve. A number of presets are available in the **Inspector** by right-clicking the curve. Zero and negative values are allowed but can produce unusual effects. See also :ref:`spot_angle_attenuation<class_SpotLight3D_property_spot_angle_attenuation>`.

\ **Note:** Very high :ref:`spot_attenuation<class_SpotLight3D_property_spot_attenuation>` values (typically above 10) can impact performance negatively if the light is made to use a larger :ref:`spot_range<class_SpotLight3D_property_spot_range>` to compensate. This is because culling opportunities will become less common and shading costs will be increased (as the light will cover more pixels on screen while resulting in the same amount of brightness). To improve performance, use the lowest :ref:`spot_attenuation<class_SpotLight3D_property_spot_attenuation>` value possible for the visuals you're trying to achieve.

.. rst-class:: classref-item-separator

----

.. _class_SpotLight3D_property_spot_range:

.. rst-class:: classref-property

:ref:`float<class_float>` **spot_range** = ``5.0``

.. rst-class:: classref-property-setget

- void **set_param** **(** :ref:`float<class_float>` value **)**
- :ref:`float<class_float>` **get_param** **(** **)**

The maximal range that can be reached by the spotlight. Note that the effectively lit area may appear to be smaller depending on the :ref:`spot_attenuation<class_SpotLight3D_property_spot_attenuation>` in use. No matter the :ref:`spot_attenuation<class_SpotLight3D_property_spot_attenuation>` in use, the light will never reach anything outside this range.

\ **Note:** :ref:`spot_range<class_SpotLight3D_property_spot_range>` is not affected by :ref:`Node3D.scale<class_Node3D_property_scale>` (the light's scale or its parent's scale).

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
.. |bitfield| replace:: :abbr:`BitField (This value is an integer composed as a bitmask of the following flags.)`
