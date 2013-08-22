# textmate-django.tmbundle

Combination bundle for Django's Python and HTML grammars.

## Grammars
The existing Django support bundles frustrate me.  Hopefully this one does a better job staying current and providing utility instead of stumbling blocks.

### Python (Django)
Provides:

* ``support.other.django.module`` scope to imported django module paths (borrowed from old grammar, but fixed to make sure it highlights all ``django*`` modules).
* ``support.attribute.django.view.*`` scopes to the common class-based view configuration attributes.  For example, ``model = MyModel`` will receive a ``support.attribute.django.view.generic``, while attributes specific to specialized generic views such as ``success_url = reverse('somename')`` will receive a ``support.attribute.django.view.edit``.
* ``support.function.django.view`` scope to a (currently meager) list of Django support functions such as ``get_object_or_404``.  These are less valuable for class-based views, but the list needs some expanding at any rate.
* ``support.function.django.model`` scope to Django support functions that relate to models, managers, and querysets, such as ``get_object()``, ``iterator()``, ``count()``, etc.  These also need some expansion.
* ``meta.reference.django.model`` scope to model names that are clearly in the queryset idiom of ``MyModel.objects.filter( ... )``.  While this doesn't automatically do anything by default, you may target this meta attribute in a theme customization to embolden, italicize, or colorize the model names as they appear in blocks of code.

#### TODOs

* Make a comprehensive list of settings names (the list borred from old grammar is—wait for it... old), scope them appropriately, according to versions and deprecation thresholds
* Expand list of support functions found by ``support.function.django.view``
* Expand list of support functions found by ``support.function.django.model``


### HTML (Django)
Provides:

* Code folding patterns for Django tags
* ``entity.name.tag`` scope to all template tag names (built-in and user-defined alike)
* ``support.other.django.template.tag.block.builtin`` scope to recognized built-in template-tags
* ``meta.verbatim.django.template`` over the content of ``{% verbatim %}...{% endverbatim %}`` blocks.  Themes can target this for custom styles.
* ``meta.spaceless.django.template`` for ``{% spaceless %}...{% endspaceless %}`` blocks.  Themes can target this for custom styles.
* ``meta.scope.django.template.tag.block-body.{name}`` scope in the body of all ``{% block ... %}...{% endblock %}`` tags, where ``{name}`` is the block's declared name.  Themes can target this for custom styles on a per-block-name basis.
* ``invalid.illegal.spacing`` to tag and variable references that include too much or too little space around their ``{{``, ``}}``, ``{%`` and ``%}`` operators.
* ``support.function.python`` scope on common methods called on template variables, such as ``keys``, ``items``, ``count``, ``all``, ``field``, ``label_tag``, ``auto_id``, ``errors``, etc.
* Strings are properly scoped
* Complex tags that use special keywords are recognized, such as logic operators (``and``, ``or``, ``not``, ``in``) and flag-like operators (``reversed``, ``noop``, ``only``, ``with``, ``by``, ``as``)
* Applies proper scope to Django 1.5-style constants ``True``, ``False``, and ``None``.
* Recognition of filter syntax
* Tags and variable references are properly applied when used inside of quoted HTML attribute values.

#### TODOs
TBD
