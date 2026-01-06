# Timezone and NTP Configuration Test from Chef 360 Courier

InSpec profile to verify timezone and NTP server configuration on Linux systems.

### CLI from Chef 360 Courier workstation
```bash
chef-courier-cli scheduler jobs update-job --jobId JOB_ID --body "$(jq -c '.item' job.json)"
chef-courier-cli scheduler jobs activated-job --jobId JOB_ID
```

