
### PUSH TIME COOKBOOK USING CHEF COURIER ####
# Author: Bryan Phillips

## Add these step in your Chef Courier instance and assign to 1 to n nodes as needed.

#STEP 1:
{
  "linux": [
    "if ! command -v chef-client >/dev/null 2>&1; then curl -L https://omnitruck.chef.io/install.sh | sudo bash -s -- -P chef-workstation; fi"
  ]
}

#STEP 2:
{
  "linux": [
    "sudo rm -rf /tmp/time-cookbook /tmp/cookbook-lock",
    "git clone https://github.com/bassslap/time-cookbook.git /tmp/time-cookbook",
    "cd /tmp/time-cookbook && echo 'yes' | /opt/chef-workstation/bin/chef install Policyfile.rb --chef-license accept",
    "cd /tmp/time-cookbook && /opt/chef-workstation/bin/chef export Policyfile.rb /tmp/cookbook-lock --force --chef-license accept"
  ]
}

#STEP 3:
{
  "linux": [
    "echo '{\"time\":{\"timezone\":\"America/New_York\",\"ntp_servers\":[\"0.pool.ntp.org\",\"1.pool.ntp.org\"]}}' > /tmp/attributes.json",
    "cd /tmp/cookbook-lock && sudo chef-client -z -j /tmp/attributes.json --chef-license accept-silent"
  ]
}
