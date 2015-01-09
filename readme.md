# Ansible provisioning Elasticsearch Cluster

Install an Elasticsearch cluster on the machines in the hosts file, also installs the `marvel` and `cloud-aws` plugins. The production cluster is separate from the marvel monitoring cluster.

```bash
ansible-playbook -i hosts provisioning/site.yml
```

## Run an Ansible Ad-hoc command

```bash
ansible es1.appcraft.nl -i hosts -u root -m shell -a '/sbin/shutdown -r now'
```

# Elasticsearch

Sense is available at: `http://es1.appcraft.nl:9200/_plugin/marvel/sense/index.html`.

Marvel is available at: `http://es-mon1.appcraft.nl:9200/_plugin/marvel/kibana/index.html`.

## Cluster health

```bash
curl http://es1.appcraft.nl:9200/_cluster/health?pretty
```

## Sense

```bash
POST /twitter

PUT /twitter/tweet/1
{
  "name": "Sander",
  "body": "Hello World!"
}
```
