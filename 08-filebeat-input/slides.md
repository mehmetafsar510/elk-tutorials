%title: ELK


# Filebeat : Input Logs


<br>


 log-type input pane

* doc: https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-input-log.html

* options: (multiple log blocks)
* enabled: enable
* paths: path (with or without \*)
* fields: additional fields (environment...)
* recursive_glob.enabled: "massive" recursive (8 levels) thanks to \*\*
* include_lines
* exclude_lines
* json: other video
* exclude_files: excluded files
* ignore_older: ignore files modified more than x (dhs) ago
* fence rules
* symlinks: follow symbolic links
* tags
* index: if elasticsearch output 

-----------------------------------------------------------------------------------------


```
filebeat.inputs:
- type: log
  enabled: true
  paths:
    - /var/log/nginx/access*.log
  exclude_lines: ["^127.0.0.1"]
  exclude_files: [".gz$"]
  ignore_older: 24h
  tags: ["back"]
  fields:
    env: prod
    owner: xavki
```
