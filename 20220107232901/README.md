# how to declare react hook form with independent components

**Reference**: <https://react-hook-form.com/advanced-usage#WizardFormFunnel>

To handle this we must declare each component as it's own form with it's
own submit function, so yup dependency can error check just these
fields, so the best way I found today is declare independent `useForm`
per component

**Result code**: <https://github.com/lami-health/website/pull/512>
