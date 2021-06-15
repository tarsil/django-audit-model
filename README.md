# Django Model Audit

## How to use

Add `django_model_audit` into any place of your project and simply import the models.

## Creation only

* created_at = models.DateTimeField(null=False, blank=False, auto_now_add=True)
* created_by = models.ForeignKey(settings.AUTH_USER_MODEL, related_name='created_%(class)s_set',
                                   null=False, blank=True, on_delete=models.SET_NULL)

# Update

* updated_by = models.ForeignKey(settings.AUTH_USER_MODEL, related_name='modified_%(class)s_set',
                                    null=False, blank=True, on_delete=models.SET_NULL)
* updated_at = models.DateTimeField(null=False, blank=False, auto_now=True)
