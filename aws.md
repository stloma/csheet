# AWS cheatsheet

- [Initialize](#initialize)
- [s3](#s3)
- [lambda](#lambda)

## Initialize

Keys | Description
:--|:--
aws configure | configuration walk-through

## s3 (assume prefix of aws s3 for all commands)

Keys | Description
:--|:--
ls | list storage buckets
sync | syncs directories and s3 buckets
sync --dryrun | displays what would be performed
sync --size-only | ignores time stampes, compare files only based on size

## lambda (assume prefix of aws lambda for all commands)

Keys | Description
:--|:--
update-function-code --function-name \<function-name> --zip-file fileb://\<filename>.zip
