# AWS Automation Script

This script is designed to automate various tasks related to AWS using the Boto3 library. It provides the following functionalities:

## Command-line Arguments

The script accepts the following command-line arguments:

- `--secuity_group_id` (`-sgi`): VPC ID.
- `--subnet_group_name` (`-sgn`): Subnet group name.
- `--DBInstanceIdentifier` (`-dbi`): DB instance identifier.
- `--snapshot_identifier` (`-si`): Snapshot identifier.
- `--create_RDS_instance` (`-crds`): Create an RDS instance.
- `--modify_rds_storge` (`-mrds`): Modify RDS storage.
- `--snapshot_rds_storge` (`-srds`): Create a manual snapshot of an RDS instance.
- `--region` (`-r`): AWS region.
- `--list_dynamodb_table` (`-ldt`): List DynamoDB tables.

## Functions

The script provides the following functions:

1. `create_db_instance(rds_client, ec2_client, secuity_group_id, subnet_group_name, DBInstanceIdentifier)`: Creates an RDS instance with the specified parameters.
2. `modify_rds_storge(rds_client, DBInstanceIdentifier)`: Modifies the storage of an existing RDS instance.
3. `create_manual_snapshot(rds_client, DBInstanceIdentifier, snapshot_identifier)`: Creates a manual snapshot of an RDS instance.
4. `list_dynamodb_table(region)`: Lists all DynamoDB tables in the specified region.
5. `main()`: The main function that orchestrates the execution of the script.

## Usage

To use the script, provide the required command-line arguments based on the desired functionality. For example:

- To create an RDS instance: `python script.py --create_RDS_instance --secuity_group_id=<security_group_id> --subnet_group_name=<subnet_group_name> --DBInstanceIdentifier=<DB_instance_identifier> --region=<AWS_region>`
- To modify RDS storage: `python script.py --modify_rds_storge --DBInstanceIdentifier=<DB_instance_identifier> --region=<AWS_region>`
- To create a manual snapshot of an RDS instance: `python script.py --snapshot_rds_storge --DBInstanceIdentifier=<DB_instance_identifier> --snapshot_identifier=<snapshot_identifier> --region=<AWS_region>`
- To list DynamoDB tables: `python script.py --list_dynamodb_table --region=<AWS_region>`

Make sure to set the necessary environment variables in a `.env` file.

Note: Replace `<security_group_id>`, `<subnet_group_name>`, `<DB_instance_identifier>`, `<snapshot_identifier>`, and `<AWS_region>` with the appropriate values.

