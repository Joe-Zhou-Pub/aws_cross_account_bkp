# aws_cross_account_bkp
Backup AWS RDS to a totally separated account, so that even the production environment is totally destroied by ransomware or disaster. We still can recover from separated locked account from the other coast.

The script replicates the snapshots of the RDS with KMS encryption. First check the SQS to see if there is new auto-snapshot of the RDS, then create a Celery task and sent it to the queue to run asynchrously, so that the program can control multiple RDS backups. 
