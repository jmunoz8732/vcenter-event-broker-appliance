---
layout: function
id: functions
type: knative
title: Prebuilt Functions
description: Community-sourced and validated prebuilt functions for Knative with VEBA.
permalink: /examples-knative
images:
  powercli: /assets/img/languages/powercli.png
  python: /assets/img/languages/python.png
  go: /assets/img/languages/go.png
  powershell: /assets/img/languages/powershell.png
examples:
  - title: Echo Cloud Event for Knative
    usecases:
    - item: other
    id: kn-ps-echo-function
    description: Function that helps users understand the structure and data of a given vCenter Event using the Knative event processor which will be useful when creating brand new Functions.
    links:
    - language: powershell
      url: "/tree/master/examples/knative/powershell/kn-ps-echo"
    - language: python
      url: "/tree/master/examples/knative/python/kn-py-echo"
    - language: go
      url: "/tree/master/examples/knative/go/kn-go-echo"
  - title: Slack Notification
    usecases:
    - item: integration
    - item: notification
    id: kn-ps-slack-function
    description: Function to send a Slack notification.
    links:
    - language: powershell
      url: "/tree/master/examples/knative/powershell/kn-ps-slack"
    - language: python
      url: "/tree/master/examples/knative/python/kn-py-slack"
  - title: Email Notification
    usecases:
    - item: notification
    id: kn-ps-email-function
    description: Powershell function to send an Email.
    links:
    - language: powershell
      url: "/tree/master/examples/knative/powershell/kn-ps-email"
  - title: vSphere Tagging
    usecases:
    - item: automation
    id: kn-pcli-tag-function
    description: Automatically tag a VM upon a vCenter event (ex. a VM can be tagged during a poweron event).
    links:
    - language: powercli
      url: "/tree/master/examples/knative/powercli/kn-pcli-tag"
  - title: vSphere to NSX-T Tag Synchronization
    usecases:
    - item: automation
    id: kn-pcli-nsx-tag-sync
    description: Automatically synchronize VM tags to NSX-T.
    links:
    - language: powercli
      url: "/tree/master/examples/knative/powercli/kn-pcli-nsx-tag-sync"
  - title: vSphere Custom Attributes
    usecases:
    - item: automation
    id: kn-py-vm-attr-function
    description: Add Custom Attribute to VM upon a vCenter event.
    links:
    - language: python
      url: "/tree/master/examples/knative/python/kn-py-vm-attr"
  - title: Enhancing vSphere Alarm Actions
    usecases:
    - item: integration
    - item: notification
    id: kn-ps-slack-vsphere-alarm-function
    description: Function to send a Slack notification triggered by a vSphere Alarm.
    links:
    - language: powershell
      url: "/tree/master/examples/knative/powershell/kn-ps-slack-vsphere-alarm"
  - title: Telegram Notification
    usecases:
    - item: automation
    - item: integration
    - item: notification
    id: kn-pcli-telegram-function
    description: Function to send a Telegram notification triggered by a vMotion of VM.
    links:
    - language: powercli
      url: "/tree/master/examples/knative/powercli/kn-pcli-telegram"
  - title: SMS Notification
    usecases:
    - item: integration
    - item: notification
    id: kn-ps-twillio-sms-function
    description: Function to send an SMS message using Twillio triggered by a VM Snapshot.
    links:
    - language: powershell
      url: "/tree/master/examples/knative/powershell/kn-ps-twillio-sms"
  - title: VMware Horizon Notification
    usecases:
    - item: integration
    - item: notification
    id: kn-ps-horizon-slack-function
    description: Function to send a Slack notification triggered by a VMware Horizon Event.
    links:
    - language: powershell
      url: "/tree/master/examples/knative/powershell/kn-ps-horizon-slack-function"
  - title: VMware Cloud Gateway Notification (Slack)
    usecases:
    - item: integration
    - item: notification
    id: kn-ps-ngw-slack-function
    description: Function to send a Slack notification triggered by a VMware Cloud Notification Gateway SDDC Event.
    links:
    - language: powershell
      url: "/tree/master/examples/knative/powershell/kn-ps-ngw-slack-function"
  - title: Custom Webhook Function
    usecases:
    - item: integration
    id: kn-ps-webhook-function
    description: Function to ingest a non-CloudEvent using a custom incoming webhook
    links:
    - language: powershell
      url: "/tree/master/examples/knative/powershell/kn-ps-webhook-function"
  - title: VMware Cloud Gateway Notification (Teams)
    usecases:
    - item: integration
    - item: notification
    id: kn-ps-ngw-teams-function
    description: Function to send a Microsoft Teams notification triggered by a VMware Cloud Notification Gateway SDDC Event.
    links:
    - language: powershell
      url: "/tree/master/examples/knative/powershell/kn-ps-ngw-teams-function"
  - title: Schedule VM Snapshot Retention Management
    usecases:
    - item: automation
    - item: remediation
    id: kn-pcli-snapshot-cron-function
    description: Function to manage VM snapshots on a scheduled job (cron)
    links:
    - language: powercli
      url: "/tree/master/examples/knative/powercli/kn-pcli-snapshot-cron"
  - title: Alert on vSphere Inventory Resource Deletion
    usecases:
    - item: notification
    id: kn-ps-vsphere-inv-slack-function
    description: Function to send Slack notification when a specific vSphere inventory resource has been deleted
    links:
    - language: powershell
      url: "/tree/master/examples/knative/powershell/kn-ps-vsphere-inv-slack"
---

A complete and updated list of ready to use functions curated by the VMware Event Broker community is listed below. 

# Get started with our prebuilt functions

These functions are prebuilt, available in ready to deploy container and `function.yaml` files for you to deploy as is. Should you need to modify the functions to fit your needs, the `README.md` files provided within each function folder will provide all the information you need to customize, build and deploy the function on your VMware Event Broker appliance. 

> **Note:** These functions are provided and tested to be used with the VMware Event Broker Appliance deployed with [Knative](/kb/install-knative) as the event stream processor. 


 <div class="examples wd-100">
    <h2>Functions</h2>
    {% for ex in page.examples %}
    <div id="{{ ex.id }}" class="row title">
      <h3>{{ex.title}}</h3>
      <div class="language">
      {% for link in ex.links %}
        <a href="{{ link.url | prepend: site.gh_repo}}" target="_blank" class="col-md-2 pr-0">
            <img src="{{ '/assets/img/languages/' | append: link.language | append: '.png' | relative_url}}" alt="{{ link.language }}">
            <span class="m-0">{{ link.language }}</span>
        </a>
      {% endfor %}
      </div>
    </div>
    {{ ex.description | markdownify }}
    <div class="usecases">
      {% for usecase in ex.usecases %}
      <span class="{{usecase.item}}">{{usecase.item}}</span>
      {% endfor %}
    </div>
    
    {% endfor %}
</div>

## Contributions

These functions serve as an easy way to use the appliance and as an inspiration for how to write functions in different languages. If you have an idea for a function and are looking to write your own, start with our documentation [here](/kb/contribute-functions). 

Check our [contributing guidelines](\community#contributing) and join [Team #VEBA](/#team-veba) by submitting a pull request for your function to be showcased on this list. 