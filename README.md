# Openshift Rawdog cartridge

An Openshift cartridge for the [Rawdog feed aggregator](http://offog.org/code/rawdog/).  It can be configured to fetch feeds and generate HTML, but it won't serve the generated content - use another cartridge for that.

## Installation

 1. Install these cartridges:
     - http://cartreflect-claytondev.rhcloud.com/reflect?github=33d/openshift-cartridge-rawdog 
     - cron

 2. Copy `.template/.rawdog/config.erb` to your repo at `.rawdog/config.erb`, and edit accordingly.

 3. Copy `.template/.openshift/cron/hourly/rawdog-update` to your repo, at `.openshift/cron/hourly`.

 4. Serve the generated `rawdog.html` somehow, along with the style sheet in the [Rawdog download](http://offog.org/files/rawdog-2.21.tar.gz).

You can use the `RAWDOG_CONFIG` environment variable to change the configuration directory, for example (you need to ssh to the app to get its home directory):

    $ rhc env set RAWDOG_CONFIG='(app-home)/app-root/runtime/repo/rawdog' --app my-app
