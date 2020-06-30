[![Community Project header](https://github.com/newrelic/opensource-website/raw/master/src/images/categories/Community_Project.png)](https://opensource.newrelic.com/oss-category/#community-project)

# New Relic Ansible Collection - newrelic.newrelic_agents

This repo collects the Ansible roles for installing the [New Relic Java agent](https://docs.newrelic.com/docs/agents/java-agent/getting-started/introduction-new-relic-java) and the [New Relic Infrastructure agent](https://docs.newrelic.com/docs/infrastructure/new-relic-infrastructure/get-started/introduction-new-relic-infrastructure). Other roles may be added in the future.

## Installation

To install the collection, use the `ansible-galaxy` command:

```shell
$ ansible-galaxy collection install newrelic.newrelic_agents
```

## Example usage

The following examples are strictly for reference purposes, and are drawn from the individual roles' examples. See the [Infrastructure agent role repo](https://github.com/newrelic/infrastructure-agent-ansible) and the [Java agent role repo](https://github.com/newrelic/newrelic-java-agent-ansible-role) for full documentation.

*Note: When using these roles from this collection, rather than directly, you must either add the `collections` keyword to your playbooks as shown below, or use the fully qualified collection name, for example `newrelic.newrelic_agents.newrelic_java_agent`.*

```yaml
---
- hosts: java_servers

  collections:
    - newrelic.newrelic_agents

  vars:
    nr_java_agent_config:
      license_key: YOUR_LICENSE_KEY
      # etc.
  
  include_role:
    name: newrelic_java_agent
```

```yaml
---
- hosts: infrastructure_hosts

  collections: 
    - newrelic.newrelic_agents
  
  roles:
    - name: newrelic-infra
      vars:
        nrinfragent_config:
          license_key: YOUR_LICENSE_KEY
          # etc.
```

## Contributing
We encourage your contributions to improve the New Relic Ansible collection! Keep in mind when you submit your pull request, you'll need to sign the CLA via the click-through using CLA-Assistant. You only have to sign the CLA one time per project.
If you have any questions, or to execute our corporate CLA, required if your contribution is on behalf of a company,  please drop us an email at opensource@newrelic.com.

## License
The New Relic Ansible collection is licensed under the [Apache 2.0](http://apache.org/licenses/LICENSE-2.0.txt) License.
