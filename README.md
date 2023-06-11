# postfix_ses

An ansible galaxy role to configure [AWS SES](https://aws.amazon.com/ses/) as the relay host for a send-only Postfix mail server.

## Requirements

Ubuntu

## Role Variables

These variables must be provided:

`postfix_ses_postmaster_email` the email address for the postmaster of the server.
`postfix_ses_identity` an SES identity in form of an email or domain
`postfix_ses_mailname` host that emails will come from in headers
`postfix_ses_canonical_sender_email` all emails will come from this address, it should be set up as verified at SES.
`postfix_ses_host` hostname of ses service
`postfix_ses_username` username for ses service
`postfix_ses_password` password for ses service

## Dependencies

You need an AWS SES service configured.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: thermistor.postfix_ses
           postfix_ses_postmaster_email: postmaster@example.com
           postfix_ses_identity: example.com
           postfix_ses_mailname: example.com
           postfix_ses_canonical_sender_email: server1@example.com
           postfix_ses_host: email-smtp.us-west-1.amazonaws.com
           postfix_ses_username: example-username
           postfix_ses_password: example-secret


## License

Licensed under the MIT License. See the LICENSE file for details.

