# Errors

The GraphQL endpoint typically returns `200 OK` if the query ran through the schema.

Validation errors are typically returned as data and the exact types can be introspected on the appropriate return types.

Other GraphQL errors show up at the top level in an `errors` attribute.
