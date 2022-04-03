# ELK


# Filebeat : Input Logs


<br>


 log-type input pane

* doc: https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-input-log.html

* options: (multiple log blocks)
* enabled: enable
* paths: path (with or without \*)
* fields: additional fields (environment...)(Optional fields that you can specify to add additional information to the output. For example, you might add fields that you can use for filtering log data. Fields can be scalar values, arrays, dictionaries, or any nested combination of these.)

* recursive_glob.enabled: "massive" recursive (8 levels) thanks to \*\*

* include_lines(A list of regular expressions to match the lines that you want Filebeat to include. Filebeat exports only the lines that match a regular expression in the list. By default, all lines are exported. Empty lines are ignored.)

* exclude_lines(A list of regular expressions to match the lines that you want Filebeat to exclude. Filebeat drops any lines that match a regular expression in the list. By default, no lines are dropped. Empty lines are ignored.)

* json: other video
* exclude_files: excluded files(A list of regular expressions to match the files that you want Filebeat to ignore. By default no files are excluded.)

* ignore_older: ignore files modified more than x (dhs) ago (If this option is enabled, Filebeat ignores any files that were modified before the specified timespan. Configuring ignore_older can be especially useful if you keep log files for a long time. For example, if you want to start Filebeat, but only want to send the newest files and files from last week, you can configure this option.)

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
