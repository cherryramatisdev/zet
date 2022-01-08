# how to declare react hook form with independent components

**Reference**: <https://react-hook-form.com/advanced-usage#WizardFormFunnel>

- To apply these, we use context API instead of state machine to manipulate the data state and use errors independent.

- Doubt:
	- Today the sub form can't access errors message, maybe every sub form can be it's own form? maybe we can use the `register` method that reference specifies? don't know at all
	- Once I solve that, it's just matter of managing the step with the `onSubmit` method and do the API request.
