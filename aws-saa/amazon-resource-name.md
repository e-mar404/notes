# Amazon Resource Names (ARN)

ARNs uniquely identify resources within any aws account. This way you are able
to reference specific resources which can have very similar names either from
your own account of from other accounts.

## Usage in Identity Policies

Usually used in IAM [[identity-policies]] to specify resources attached to
an [[identity-policies#Statement]].

## Format

```
arn:partition:service:region:account-id:resource-id
arn:partition:service:region:account-id:resource-type/resource-id
arn:partition:service:region:account-id:resource-type:resource-id
```

It is very important to pay attention to what the arn references. For instance
this arn `arn:aws:s3:::catgifs` refers to the actual s3 bucket called `catgifs`.
Whereas this one `arn:aws:s3:::catgifs/*` refers to all the keys inside the
bucket. There is no overlap between the 2 so in order to access the bucket and
everything within it then you would need both arns. Different actions require
act on different resources to you might need both to be able do all actions on
the bucket and the objects on that bucket.
