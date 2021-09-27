# Associate Cloud Engineer

- [Certification Exam](https://cloud.google.com/certification/cloud-engineer)
- [Certification Challenge](https://events.withgoogle.com/latam-professional-cloud-architect-enablement/foundation-training/#content)
- [Exam Guide](https://cloud.google.com/certification/guides/cloud-engineer/)
- [Sample Questions](https://docs.google.com/forms/d/e/1FAIpQLSfexWKtXT2OSFJ-obA4iT3GmzgiOCGvjrT9OfxilWC1yPtmfQ/viewform)


-----
# [IAM](https://cloud.google.com/iam/docs)

## [Roles](https://cloud.google.com/iam/docs/understanding-roles)

- **Basic roles**, which include the Owner, Editor, and Viewer roles that existed prior to the introduction of IAM.
- **Predefined roles**, which provide granular access for a specific service and are managed by Google Cloud.
- **Custom roles**, which provide granular access according to a user-specified list of permissions.

### [Basic roles](https://cloud.google.com/iam/docs/understanding-roles#basic)

Have Owner, Editor and Viewer, they were originally know as primite roles.

Owner > Editor > Viewer

Owner roles includes the permissions in the Editor role, the Editor role includes the permissions in the Viewer role.

- Viewer (roles/viewer): Can only viewing resources
- Editor (roles/editor): Can modify resources, can create and delete most Google Cloud Services.
- Owner  (roles/owner):  Can manage roles and permissions, can set up billing for a project with they has a project owner. If they are a owner for some service, they can't do that.

### [Predefined roles](https://cloud.google.com/iam/docs/understanding-roles#predefined_roles)

IAM have roles that give granular access to specific Google Cloud resources and prevent unwanted access to other resources. These roles are created and maintained by Google.

Ex:

- roles/actions.Admin: Access to edit and deploy an action
- roles/actions.Viewer: Access to view an action
- roles/notebooks.admin: Full access to Notebooks, all resources.
- roles/appengine.deployer: Read-only access to all application configuration and settings.


### [Custom roles](https://cloud.google.com/iam/docs/understanding-roles#custom_roles)

You can create a custom IAM role with one or more permissions and then grant that custom role to users who are part of your organization.

# [Billing](https://cloud.google.com/billing/docs)

## [Budgets](https://cloud.google.com/billing/docs/how-to/budgets)

You can create a budgets that follow Monthly, Quarterly, Yearly or Custom range rules.

# BigQuery

## [bq cli](https://cloud.google.com/bigquery/docs/reference/bq-cli-reference)

# [Biqtable](https://cloud.google.com/bigtable/docs/overview)

Cloud Bigtable is a sparsely populated table that can scale to billions of rows and thousands of columns, enabling you to store terabytes or even petabytes of data. A single value in each row is indexed; this value is known as the row key. Bigtable is ideal for storing very large amounts of single-keyed data with very low latency. It supports high read and write throughput at low latency, and it is an ideal data source for MapReduce operations.

## [Schema design for time series data](https://cloud.google.com/bigtable/docs/schema-design-time-series)

# Compute Engine

## [Instance Groups](https://cloud.google.com/compute/docs/instance-groups/#managed_instance_groups_and_autoscaling)

An instance group is a collection of virtual machine (VM) instances that you can manage as a single entity.

You can scale than automaticly




# Stackdriver

# Disk Compute Engine

# Cloud Datastore - Document Store






