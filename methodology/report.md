---
description: Preparing report documents and data
---

# Report

* [ ] create client report document
* [ ] create logbook document
* [ ] create data repository

{% tabs %}
{% tab title="Report" %}
A draft document for the client report, which should contain these sections at a minimum:

* executive summary
* technical summary
* vulnerabilities organized by risk
* remediation recommendations
* appendix for evidence
{% endtab %}

{% tab title="Logbook" %}
The logbook will be a document used to notate all activities during the pen test, such as scans, queries, activities, etc.  The logbook helps supply raw material for the final report as well as acts as a useful reference during the pen test to backtrack for new ideas and to update notes afterwards with new or updated tactics.
{% endtab %}

{% tab title="Data Repository" %}
Configure a repository that you will use to sync data such as nmap scan output files, data captures, screenshots, keys, logs, custom exploit code, etc from your virtual machine. In a worst case scenario if your VM crashes you can easily rebuild and download the repo to pick up where you left off. This data will also serve as raw material for your final report.  Options include using a private git repo, shared folders, cloud storage, etc. 
{% endtab %}
{% endtabs %}



