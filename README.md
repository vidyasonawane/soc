CNCF + Summer of Code
=====================

The Cloud Native Computing Foundation participates in [Google Summer of Code](https://summerofcode.withgoogle.com/) (GSoC). CNCF is a great place to spend a summer learning, coding, participating and contributing. We are an exciting open source foundation with a vibrant community of projects, and we look forward to your application and your project ideas!

Organization Admins
-------------------

If you need help with anything CNCF + Summer of code related, you can file an issue or contact one of the admins below:

-	Chris Aniszczyk ([@caniszczyk](https://github.com/caniszczyk)\): https://twitter.com/cra
-	Ihor Dvoretskyi ([@idvoretskyi](https://github.com/idvoretskyi)\): https://twitter.com/idvoretskyi
-	Nikhita Raghunath ([@nikhita](https://github.com/nikhita)\): https://twitter.com/TheNikhita

Communication
-------------

It's best if you use a public communication channel whenever possible; however, if you need to communicate in private, please feel free to send the admins a note via soc@cncf.io (please use the public channels for any project-related discussion).

You can join the CNCF slack [here](https://slack.cncf.io/).

Current Year
------------

CNCF is applying as a mentoring organization for Google Summer of Code 2019.

### Timeline

Please, check out the official [GSoC program timeline for 2019](https://developers.google.com/open-source/gsoc/timeline).

### Students

The list of official project ideas will be published below.

You can also take a look at the list of project ideas published for GSoC [2017](/2017.md) and [2018](/2018.md)\.

### Mentors

Add your ideas to the list below.

Project Ideas
-------------

Please, submit your ideas below using the [template](/PROJECT_IDEA_TEMPLATE.md). **IMPORTANT**: The deadline to submit a project idea is February 6 20:00 UTC.

### Kubernetes

Please visit the [Kubernetes GSoC page](https://git.k8s.io/community/mentoring/google-summer-of-code.md) for general information. For any questions or comments, please reach out to us on the #gsoc-apps channel on the [Kubernetes slack](http://slack.k8s.io/).

#### Integrate kube-batch with pytorch-operator/mxnet-operator

-	Description: [kube-batch](https://github.com/kubernetes-sigs/kube-batch) is a batch scheduler for kubernetes by features for batch workload, e.g. coscheduling/gang-scheduling, faire-sharing; the train job of MxNet and Pytorch have requirements to those features. This idea is to integrate kube-batch to support gang-scheduling/coscheduling and other batch features in related operators.
-	Recommended Skills: golang, kubernetes, kubeflow
-	Mentor(s): Klaus Ma (@k82cn)
-	Issue: https://github.com/kubeflow/mxnet-operator/issues/16 , https://github.com/kubeflow/pytorch-operator/issues/129

#### Implement volume snapshotting support into the external Manila provisioner

-	Description: The external OpenStack Manila provisioner lack ability to take a snapshot of the volumes and turn the snapshots to persistent volumes using container orchestrator API. The goal is to implement the missing feature in the Manila (CSI) provisioner.
-	Recommended Skills: Golang, Kubernetes, Ceph, OpenStack
-	Mentor(s): Tomas Smetana (@tsmetana)
-	Issue: https://github.com/kubernetes/cloud-provider-openstack/issues/453

#### Enable full e2e tests for external Azure cloud provider

-	Description: The external Azure cloud provider has added its initial e2e tests, but it’s still not running the full e2e tests today. The goal is to add the missing tests and publish them on the testgrid.
-	Recommended Skills: Golang, Kubernetes, Azure
-	Mentor(s): Pengfei Ni (@feiskyer)
-	Issue: https://github.com/kubernetes/cloud-provider-azure/issues/4

#### CSI drivers for AzureDisk and AzureFile

-	Description: External drivers for AzureDisk and AzureFile would be implemented as new CSI drivers. The goal is mirror the current functions from in-tree drivers and setup e2e tests as well as documentation for them.
-	Recommended Skills: Golang, Kubernetes, Azure
-	Mentor(s): Andy Zhang (@andyzhangx)
-	Issue: https://github.com/kubernetes/org/issues/344

### Prometheus

Prometheus is an open-source systems monitoring and alerting toolkit: https://prometheus.io/

Prometheus ideas:

#### Benchmarks for TSDB

-	Description: The TSDB module used in Prometheus doesn’t have proper benchmarks yet, which means we cannot see the potential impact of the changes we are introducing. The idea is to build some automated benchmarking which can be added to the CI pipeline.
-	Recommended Skills: CI, Golang, Kubernetes
-	Mentor(s): Krasi Georgiev (@krasi-georgiev)
-	Issue: https://github.com/prometheus/tsdb/issues/235

#### Continue the work on Prombench

-	Description: Since we finished Prombench there have been few requests to add scalability tests, add more tests with the race enabled and there are few pending issues to be fixed.
-	Recommended Skills: CI, Golang, Kubernetes, Grafana
-	Mentor(s): Krasi Georgiev (@krasi-georgiev)
-	Issue: https://github.com/prometheus/prombench/issues - the High priority ones should be addressed first.

### Open Policy Agent (OPA)

OPA is a domain-agnostic policy engine that embodies "policy as code": https://www.openpolicyagent.org/

#### IntelliJ plugin to experiment with and visualize policy evaluation

-   Description: OPA features a high-level declarative language that lets you express policies like "user X can perform operation Y on resource Z" or "all images deployed in Kubernetes must come from an internal registry and be scanned for vulnerabilities". The language supports many features: unit testing, dry running, tracing, etc. While users can access these features via the command-line, IDE integrations greatly improve the policy authoring experience. The idea is to port functionality that we have inside of [VS Code](https://github.com/tsandall/vscode-opa) to IntelliJ. This would significantly improve the authoring experience for people that use IntelliJ on a day-to-day basis.
-   Recommended Skills: Java, IntelliJ (not required, but nice to have)
-   Mentor(s): Torin Sandall (@tsandall)
-   Issue: https://github.com/open-policy-agent/opa/issues/1085

#### Interactive website detailing OPA integrations
- Description: OPA has been integrated with 20+ cloud-native systems to provide rich, context-aware policy support, e.g. Kubernetes, Istio, Envoy, Linkerd, Terraform, Ceph, Minio.  Today there is no authoritative guide for users to understand what those integrations are, how they work, or how to get started.  This project involves designing and implementing an interactive web portal that helps users understand the integrations available with OPA.  It will be data-driven, so that new integrations can easily be added to the portal, and each entry will include code-snippets, videos, blog posts, github-repos, tutorials, reviews, and overall status.
- Recommended Skills: Frontend HTML/CSS/JavaScript, Backend Node/Python/Go/etc.
- Mentor(s): Tim Hinrichs (@timothyhinrichs) and Torin Sandall (@tsandall)
- Issue: https://github.com/open-policy-agent/opa/issues/1194

#### Integration with IPTables
- Description: One common use of policy is to set up IP packet filter rules in the Linux kernel.  The policy dictates what to do with different kinds of packets.  There have been several requests in the past to use OPA policies to control IPTables, but no one has come forth with an integration.  This project involves designing the layout of IPTable rules using OPA's policy language, implementing the algorithms that generate IPTables from that layout, and writing the code that populates the generated IPTables rules into Linux.
- Recommended Skills: Go and Linux
- Mentor(s): Tim Hinrichs (@timothyhinrichs) and Torin Sandall (@tsandall)
- Issue: https://github.com/open-policy-agent/opa/issues/1195
