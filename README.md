# TFS2017-TFS2015-build-agent-tasks-backport

For on-premises TFS environments, there are a number of OSS build tasks for the TFS build agent bundled with TFS 2017 release that were not made available for TFS 2015. [See Microsoft vsts-task repo](https://github.com/Microsoft/vsts-tasks)

Due to some limitations in the TFS2015 environment not all agent build tasks are compatible if built straight from the repo.  This project aims to address the compatibility issues with work-arounds and backport some useful tasks to work with TFS 2015 on-premesis installations.  

Further objective is to build and package these ported build agent tasks as easy to install visx extensions for TFS and distribute on the tfs marketplace.

## Identified useful agent tasks absent from TFS 2015 release

* CopyFilesOverSSH
* FTPUpload
* SSH

## Building

* Install [Node.js](http://nodejs.org)
* Open command window and navigate to local repo
* Run `npm install`
* Run `node make.js build`


## License

Copyright (c) 2016 Brian Waplington

Copyright (c) 2016 BW Soft, Inc.

[MIT License](https://raw.githubusercontent.com/bwsoftinc/TFS2017-TFS2015-build-agent-tasks-backport/master/LICENSE)
