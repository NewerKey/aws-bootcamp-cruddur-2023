# Architecture
### Conceptual Design
![Logical Design](https://github.com/NewerKey/aws-bootcamp-cruddur-2023/blob/main/_docs/assets/%5BConceptual%20Design%5DCruddur.jpeg)

[Lucid Chart Share Link](https://lucid.app/lucidchart/invitations/accept/inv_73db15dd-e4e5-41e3-a891-dffecd693ffe)

### Cloud Infrastructure (Logical Design)
![Conceptual Design](https://github.com/NewerKey/aws-bootcamp-cruddur-2023/blob/main/_docs/assets/%5BLogical%20Design%5DCloud%20Infrastructure.jpeg)

- [Lucid Chart Share Link](https://lucid.app/lucidchart/4ad90d64-4352-4900-a864-eaa6e8afe428/edit?invitationId=inv_5f18e875-62c4-457f-a42f-8672a509b06c)

# Billing

###  Create an AWS Budget

[aws budgets create-budget](https://docs.aws.amazon.com/cli/latest/reference/budgets/create-budget.html)

You can get your AWS Account ID via CLI
```sh
aws sts get-caller-identity --query Account --output text
```

- Create Budget via CLI using settings in `.\aws\json\budget.json`

```sh
aws budgets create-budget \
    --account-id AccountID \
    --budget file://aws/json/budget.json \
    --notifications-with-subscribers file://aws/json/budget-notifications-with-subscribers.json
```


# Security Considerations

### IAM_User Management 
- Go to (IAM Users Console](https://us-east-1.console.aws.amazon.com/console/home?region=us-east-1#) create a new user
- `Enable console access` for the user
- Create a new `Admin` Group and apply `AdministratorAccess`, `Billing` policies.
- Create the user and click into the user
- Click on `Security Credentials` and `Create Access Key`
- Choose AWS CLI Access
- Download the CSV with the credentials

This is the tutorial article I wrote whiles setting my IAM User [Article](https://newerkey.hashnode.dev/create-and-manage-an-iam-useraws)

### Set Env Vars

Set these credentials for your current terminal or add to a `.env` file without export
```
export AWS_ACCESS_KEY_ID=""
export AWS_SECRET_ACCESS_KEY=""
export AWS_DEFAULT_REGION=""
```
