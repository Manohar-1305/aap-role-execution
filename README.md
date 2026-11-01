1. OpenShift token – HashiCorp Vault
Store the OpenShift service-account token in Vault KV v2.

For example:
Secret engine: secret
Secret path: openshift/sno
Key: token


Configure AAP to retrieve this secret from Vault using AppRole authentication.

The retrieved token should be injected into the execution environment as:
OPENSHIFT_TOKEN


Your existing playbook variable remains unchanged:
openshift_token: "{{ lookup('env', 'OPENSHIFT_TOKEN') }}"


You won't need to manually enter the OpenShift token for every job.
