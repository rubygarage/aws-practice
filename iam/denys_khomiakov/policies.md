# Policies

`Policy` - is an authorization file that describes which type of access to services the `AWS identity` has.
By default all actions for all types of identities are denied. Only root user can perform any actions for its account. To give different kinds of access you have to assign policy to identity. There is an ability to chose policy from `AWS managed list` or create custom policy you need.

To create policy:
> `Services -> IAM -> Policies (Left menu) -> Create policy`

Then you can specify policy content through `visual editor` or using `JSON`.
