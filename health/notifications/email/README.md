<!--startmeta
custom_edit_url: "https://github.com/netdata/netdata/edit/master/health/notifications/email/README.md"
meta_yaml: "https://github.com/netdata/netdata/edit/master/health/notifications/email/metadata.yaml"
sidebar_label: "Email"
learn_status: "Published"
learn_rel_path: "Alerting/Notifications/Agent Dispatched Notifications"
message: "DO NOT EDIT THIS FILE DIRECTLY, IT IS GENERATED BY THE NOTIFICATION'S metadata.yaml FILE"
endmeta-->

# Email

Send notifications via Email using Netdata's Agent alert notification feature, which supports dozens of endpoints, user roles, and more.



<img src="https://img.shields.io/badge/maintained%20by-Netdata-%2300ab44" />

## Setup

### Prerequisites

#### 

- A working sendmail command is required for email alerts to work. Almost all MTAs provide a sendmail interface. Netdata sends all emails as user netdata, so make sure your sendmail works for local users.
- Access to the terminal where Netdata Agent is running



### Configuration

#### File

The configuration file name for this integration is `health_alarm_notify.conf`.


You can edit the configuration file using the `edit-config` script from the
Netdata [config directory](https://github.com/netdata/netdata/blob/master/docs/configure/nodes.md#the-netdata-config-directory).

```bash
cd /etc/netdata 2>/dev/null || cd /opt/netdata/etc/netdata
sudo ./edit-config health_alarm_notify.conf
```
#### Options

The following options can be defined for this notification

<details><summary>Config Options</summary>

| Name | Description | Default | Required |
|:----|:-----------|:-------|:--------:|
| EMAIL_SENDER | You can change `EMAIL_SENDER` to the email address sending the notifications. |  | False |
| SEND_EMAIL | Set `SEND_EMAIL` to YES |  | True |
| DEFAULT_RECIPIENT_EMAIL | Set `DEFAULT_RECIPIENT_EMAIL` to the email address you want the email to be sent by default. You can define multiple email addresses like this: `alarms@example.com` `systems@example.com`. |  | True |

##### DEFAULT_RECIPIENT_EMAIL

All roles will default to this variable if left unconfigured.
The `DEFAULT_RECIPIENT_CUSTOM` can be edited in the following entries at the bottom of the same file:
```conf
role_recipients_email[sysadmin]="systems@example.com"
role_recipients_email[domainadmin]="domains@example.com"
role_recipients_email[dba]="databases@example.com systems@example.com"
role_recipients_email[webmaster]="marketing@example.com development@example.com"
role_recipients_email[proxyadmin]="proxy-admin@example.com"
role_recipients_email[sitemgr]="sites@example.com"
```


</details>

#### Examples

##### Basic Configuration



```yaml
#------------------------------------------------------------------------------
# email global notification options

EMAIL_SENDER="example@domain.com"
SEND_EMAIL="YES"
DEFAULT_RECIPIENT_EMAIL="recipient@example.com"

```


## Troubleshooting

### Test Notification

You can run the following command by hand, to test alerts configuration:

```bash
# become user netdata
sudo su -s /bin/bash netdata

# enable debugging info on the console
export NETDATA_ALARM_NOTIFY_DEBUG=1

# send test alarms to sysadmin
/usr/libexec/netdata/plugins.d/alarm-notify.sh test

# send test alarms to any role
/usr/libexec/netdata/plugins.d/alarm-notify.sh test "ROLE"
```

Note that this will test _all_ alert mechanisms for the selected role.


