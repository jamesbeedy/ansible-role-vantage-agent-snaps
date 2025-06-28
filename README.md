vantage_agent_snaps
===================

Ansible role for installing and configuring vantage agents using snaps.

- [Overview](#overview)
- [Requirements](#requirements)
- [Role Variables](#role-variables)
- [Dependencies](#dependencies)
- [Example Playbook](#example-playbook)
- [License](#license)
- [Author Information](#author-information)
- [More Information](#more-information)

Overview
--------
This role installs and configures the `vantage-agent` and `jobbergate-agent` using snaps. It ensures both agents are installed, configured with OIDC credentials, and running as services. This is useful for environments that leverage Vantage Compute's agent-based architecture for cluster management and job orchestration.

Requirements
------------
- Ansible 2.9+
- Snapd must be available on the target hosts

Role Variables
--------------
The following variables must be set in your playbook or inventory:

- `oidc_client_id`: OIDC client ID for agent authentication
- `oidc_client_secret`: OIDC client secret for agent authentication
- `cluster_name`: (required for vantage-agent) Name of the cluster

Example:
```yaml
vars:
  oidc_client_id: "your-client-id"
  oidc_client_secret: "your-client-secret"
  cluster_name: "your-cluster-name"
```

Example Playbook
----------------
```yaml 
  hosts: "{{ hosts }}"
  become: true
  vars:
    oidc_client_id: "your-client-id"
    oidc_client_secret: "your-client-secret"
    cluster_name: "your-cluster-name"
  roles:
    - role: vantage_agent_snaps
```

License
-------
Apache v2 (see [LICENSE](../LICENSE))

Author Information
------------------
James Beedy <james@vantagecompute.ai>

More Information
----------------
For more details, documentation, and support, visit the [Vantage Compute website](https://vantagecompute.ai).
