
# Firehose-to-LogDNA

This is a Nozzle to send firehose events from CloudFoundry to LogDNA.

Fork From: https://github.com/cloudfoundry-community/firehose-to-syslog

# Usage

Currently the Nozzle only runs as an app in Cloud Foundry.

1. Download the latest release of Firehose-to-LogDNA.
    ```
    git clone https://github.com/logdna/logdna-cloudfoundry.git
    cd firehose-to-syslog
    ```

1. Utilize the CF cli to authenticate with your PCF instance.
    ```
    cf login -a https://api.[your cf system domain] -u [your id] --skip-ssl-validation
    ```

1. Push firehose-to-logdna.
    ```
    cf push firehose-to-logdna --no-start
    ```

1. Set environment variables with cf cli.
    ```
    cf set-env firehose-to-logdna API_ENDPOINT https://api.[your cf system domain]
    cf set-env firehose-to-logdna DOPPLER_ENDPOINT wss://doppler.[your cf system domain]:443
    cf set-env firehose-to-logdna INGESTION_KEY [your LogDNA ingestion key]
    cf set-env firehose-to-logdna FIREHOSE_CLIENT_ID  [your doppler.firehose enabled client id]
    cf set-env firehose-to-logdna FIREHOSE_CLIENT_SECRET  [your doppler.firehose enabled client secret]
    cf set-env firehose-to-logdna SYSLOG_ENDPOINT  [your syslog endpoint] (Optional)
    ```

1. Push and run.
    ```
    cf push firehose-to-logdna
    ```
